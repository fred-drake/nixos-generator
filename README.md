# NixOS Generator

My simple flake which will generate a very minimal NixOS system.  It boils down to:

- A `root` user, with the password `nixos`
- SSH enabled
- My public keys pushed, for password-less SSH

The goal is to have a dirt-simple yet complete installation.  I can then execute [nixos-anywhere](https://github.com/nix-community/nixos-anywhere) to declaratively build the subsequent system.

# Running the flake

Currently the only configuration is to create a qcow2 image for Proxmox / QEMU virtual machines:

```bash
nix build .#qcow
```

This will create a `result` link to a store that contains the `nixos.qcow2` image.

