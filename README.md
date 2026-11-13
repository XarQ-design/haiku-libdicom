# libdicom for Haiku

The [Haiku](https://www.haiku-os.org/) package of [libdicom](https://github.com/ImagingDataCommons/libdicom) 1.3.0, which
[XarQ](https://xarq.org) uses to open DICOM whole-slide images, through OpenSlide. HaikuPorts doesn't have it, so we build it
and publish it in XarQ's own package repository.

## Install

Add the XarQ repository once, then install it like any other package:

```
pkgman add-repo https://xarq.org/haiku/x86_64/current
pkgman install libdicom
```

For development, install `libdicom_devel` too. The packages are built on Haiku R1/beta6
(x86_64) and also work on newer nightlies.

## What's here

`media-libs/libdicom/` is a HaikuPorts recipe, in the same layout as the
[haikuports](https://github.com/haikuports/haikuports) tree. 

To build it yourself, copy that folder into your haikuports tree and run:

```
haikuporter -S --get-dependencies libdicom
```

Set `VENDOR="XarQ"` in `haikuports.conf` first if the package is going into the XarQ
repository: Haiku's repository tool only accepts packages whose vendor matches the
repository's.

## Releases

Each release has the built `.hpkg` files. The XarQ repository at
https://xarq.org/haiku picks them up automatically, through the workflow in
[XarQ-design/xarq](https://github.com/XarQ-design/xarq/blob/main/.github/workflows/haiku-repo.yml).

## Licence

libdicom is under the MIT licence; see the upstream project. The recipe is under the MIT
licence, like the HaikuPorts tree, and any patch is under libdicom's own licence.
