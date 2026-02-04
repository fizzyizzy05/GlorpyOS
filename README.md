# GlorpyOS &nbsp; [![bluebuild build badge](https://github.com/fizzyizzy05/glorpyos/actions/workflows/build.yml/badge.svg)](https://github.com/fizzyizzy05/glorpyos/actions/workflows/build.yml)

> [!INFO]  
> This is a meme image based on Bazzite GNOME. Do not actually use this. The following is good faith humour and is not meant to be degrading towards other projects and people, and should not be taken as such. 

Only the BEST Linux distribution for the ABSOLUTE BEST of GAMERS. GlorpyOS is so smooth and reliable and snappy it's incredible. 

## Installation

To rebase an existing atomic Fedora installation to the latest build:

- First rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  rpm-ostree rebase ostree-unverified-registry:ghcr.io/fizzyizzy05/glorpyos:latest
  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- Then rebase to the signed image, like so:
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/fizzyizzy05/glorpyos:latest
  ```
- Reboot again to complete the installation
  ```
  systemctl reboot
  ```

The `latest` tag will automatically point to the latest build. That build will still always use the Fedora version specified in `recipe.yml`, so you won't get accidentally updated to the next major version.

## ISO

If build on Fedora Atomic, you can generate an offline ISO with the instructions available [here](https://blue-build.org/learn/universal-blue/#fresh-install-from-an-iso). These ISOs cannot unfortunately be distributed on GitHub for free due to large sizes, so for public projects something else has to be used for hosting.

## Verification

These images are signed with [Sigstore](https://www.sigstore.dev/)'s [cosign](https://github.com/sigstore/cosign). You can verify the signature by downloading the `cosign.pub` file from this repo and running the following command:

```bash
cosign verify --key cosign.pub ghcr.io/fizzyizzy05/glorpyos
```
