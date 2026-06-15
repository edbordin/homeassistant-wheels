# Home Assistant Musl Wheels builder

https://peps.python.org/pep-0656/

## Platform tags

Compile utilities:

- build-base
- cmake
- git
- linux-headers
- autoconf
- automake
- cargo

### Python 3.13 / musllinux_1_2

Build with Alpine 3.22
Images: ghcr.io/edbordin/wheels/ARCH/musllinux_1_2/cp313:VERSION

Version of system builds:

- GCC 14.2.0
- Cython 3.2.2
- numpy 2.3.3
- scikit-build 0.18.1
- cffi 2.0.0

### Python 3.14 / musllinux_1_2

Build with Alpine 3.22
Images: ghcr.io/edbordin/wheels/ARCH/musllinux_1_2/cp314:VERSION

### Fork architecture scope

This fork builds the wheel builder images for:

- `armv7` (`linux/arm/v7`, musllinux platform `armv7l`)
- `armhf` (`linux/arm/v6`, musllinux platform `armv6l`)

GitHub Packages does not currently provide a native PyPI-compatible registry. Use
a static PEP 503-style index, for example GitHub Pages at
`https://edbordin.github.io/homeassistant-wheels`, for Python wheels. Builder
container images are published to GitHub Container Registry.

Version of system builds:

- GCC 14.2.0
- Cython 3.2.2
- numpy 2.3.3
- scikit-build 0.18.1
- cffi 2.0.0

## Misc

```sh

$ python3 -m builder \
    --index https://wheels.home-assistant.io \
    --requirement requirements_all.txt \
    --upload rsync \
    --remote user@server:/wheels
```

## Supported file transfer

- rsync

## Folder structure of index folder:

`/musllinux/*`
