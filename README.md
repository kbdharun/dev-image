# dev-image

This repository contains all my development packages preinstalled inside a Container image built using [Vib](https://github.com/Vanilla-OS/Vib).

To verify the container image using [`cosign`](https://github.com/sigstore/cosign) (download the `cosign.pub` file from [here](https://github.com/kbdharun/dev-image/blob/main/cosign.pub) and execute the following command):

```zsh
cosign verify --key cosign.pub ghcr.io/kbdharun/dev-image:main
```
