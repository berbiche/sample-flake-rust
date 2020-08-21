# Sample Rust project with nix Flakes

This is a stub repository to develop using Rust, nix and Flakes.

This is aimed to people with basic knowledge of Flakes and moderate knowledge of Nix.
See the [NixOS Wiki](https://nixos.wiki/wiki/Flakes) for more information about Flakes.
The relevant sections are `Basic project usage`, `Flake schema`

## Getting started

1. Install [direnv](https://github.com/direnv/direnv) on your system by following the instructions
provided on the project page.  
  **Important**: you can skip this step if you do not intend to use direnv as it's optional.

  `direnv` is a tool that setups your shell with the required environment variables (and tools in
  the case of Nix) to hack on!

2. Clone the project

    ``` console
    $ git clone git@github.com:berbiche/sample-flake-rust
    Cloning into 'sample-flake-rust'...
    direnv: error .envrc is blocked.
    ```

    If you have `direnv` installed and configured for your shell you will see the following error message:

    ```
    direnv: error /path/sample-flake-rust/.envrc is blocked.
    Run `direnv allow` to approve its content
    ```

3. If you installed `direnv` then allow `direnv` to setup your shell with the required dependencies to develop

    ``` console
    $ direnv allow
    direnv: loading /path/sample-flake-rust/.envrc
    direnv: using flake
    ```

## Development

Use `nix shell` to spawn a shell with `cargo` and all necessary dependencies.

Within this shell you can use `cargo` commands as you normally would.

If your project requires external dependencies (outside of `crates.io`) then use `nix run '.#my-package'`
to build and run your project.

## Commands cheatsheet

- `nix shell`: Spawns a shell with all the required development dependencies.

- `nix develop`: Spawns a shell with all the dependencies needed to build the Flake you specify.
  Defaults to the `defaultPackage` specified in `flake.nix`.

- `nix run`: Builds and runs the package specified. Defaults to the `defaultPackage` specified
  in `flake.nix`.

  Example: `nix run '.#hello'` will run the package `hello` specified in your `flake.nix`.

- `nix build`: Builds the package specified. Defaults

  Example: `nix build '.#hello'` will build the package `hello` specified in your `flake.nix`.
  The resulting build will be available at `./result/`

## Howtos

- Q: I build multiple binaries, how do I manage that?
- A: I don't have the answer yet

