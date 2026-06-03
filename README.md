# njkk
{ pkgs }: let   generated = import ./generated.nix;    nix-index-database =     (pkgs.fetchurl {       url = generated.url + pkgs.stdenv.system;       hash = generated.hashes.${pkgs.stdenv.system};     }).overrideAttrs       {         __structuredAttrs = true;         unsafeDiscardReferences.out = true;       };    nix-index-small-database 
