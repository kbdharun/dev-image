# dev-image

[![Image](https://github.com/kbdharun/dev-image/actions/workflows/image.yml/badge.svg)](https://github.com/kbdharun/dev-image/actions/workflows/image.yml)
![GitHub License](https://img.shields.io/github/license/kbdharun/dev-image)


This repository contains all my development packages preinstalled inside a Container image built using [Vib](https://github.com/Vanilla-OS/Vib).

## Using the Container Image with Distrobox

Type the following command to create a container of this image in [Distrobox](https://github.com/89luca89/distrobox):

```sh
distrobox create -n dev -i ghcr.io/kbdharun/dev-image:main
```

> [!TIP]
> To create a rootful container, add the `--root` flag to the above command (i.e. `distrobox create -n dev -i ghcr.io/kbdharun/dev-image:main --root`).

Type the following command to enter the container:

```sh
distrobox enter dev
```

## Verify the Container Image using Cosign

To verify the container image using [`cosign`](https://github.com/sigstore/cosign) (download the `cosign.pub` file from [here](https://github.com/kbdharun/dev-image/blob/main/cosign.pub) and execute the following command):

```zsh
cosign verify --key cosign.pub ghcr.io/kbdharun/dev-image:main
```

## Verify Image Build Provenance Attestation

All the image builds/pushes are attested for provenance and integrity using [`actions/attest-build-provenance`](https://github.com/actions/attest-build-provenance). They can be verified by having the latest version of [GitHub CLI](https://github.com/cli/cli/releases/latest) installed in your system. Then, execute the following command:

```sh
gh attestation verify oci://ghcr.io/kbdharun/dev-image:main --owner kbdharun
```
