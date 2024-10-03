# Installation

!!! Note
    If you are using [Overleaf](https://www.overleaf.com/), you do not need to have a local installation of LaTeX.

There are two main ways to install LaTeX on your system:

1. **[TeX Live](https://www.tug.org/texlive/)**: A comprehensive distribution of LaTeX for Windows, macOS, and Linux.
2. **[MiKTeX](https://miktex.org/)**: A distribution of LaTeX for Windows.

[Tectonic](https://tectonic-typesetting.github.io/en-US/) is also and option but not recommended for beginners.

!!! Note
    TeX Live is recommended for most users.

Both distributions provide a package manager to install and update packages. They also provide a GUI for managing the
installation. They additionally both provide TeXworks, a simple LaTeX editor which is discussed in more detail in the
[Editors](editors.md) section.

## [TeX Live](https://www.tug.org/texlive/)

TeX Live is a comprehensive distribution of LaTeX for Windows, macOS, and Linux maintained by the TeX Users Group (TUG).
It is available for free from the [TeX Live website](https://www.tug.org/texlive/).

They provide a [detailed installation guide](https://www.tug.org/texlive/doc/texlive-en/texlive-en.html) 
for all operating systems. And offer a [quick installation guide](https://www.tug.org/texlive/quickinstall.html).

TeX Live is provided as a single installer for most operating systems and as an 
[ISO](https://www.tug.org/texlive/acquire-iso.html) image.

Due to the size and volume of packages in modern LaTeX distributions, using the installer can be time-consuming as it
downloads all the packages from the internet. The ISO image is recommended for users with slow or unreliable internet.

!!! Note
    The ISO image is a large file (approximately 5.6 GB) but the installation will be quicker as most packages will be
    installed from the image.

!!! Note
    The installer takes between 30 minutes and 2 hour+ to complete depending on your internet connection and the mirror 
    quality.

Once installed TeX Live has  a package manager called `tlmgr` (with a gui available) which can be used to install and 
update packages.

TeX Live is frozen and updated annually and a new version must be installed each year if you want the latest packages.

TeX Live often provides the most stable experience for users and is recommended for most users.

## [MiKTeX](https://miktex.org/)

MiKTeX is a distribution of LaTeX for Windows maintained by Christian Schenk. It is available for free from the 
[MiKTeX website](https://miktex.org/). They provide a [detailed installation guide](https://miktex.org/howto/install-miktex)
for all operating systems.

MiKTeX is provided as a single installer for Windows and as a portable version for USB sticks. The installer is 
recommended for most users. The portable version is recommended for users who do not have administrator rights on their
computer. The portable version can be installed on a USB stick and run from there.

A package manager called `mpm` which can be used to install and update packages. MiKTeX is updated regularly
and packages are updated as needed.

MikTeX differs from TeX Live in that it installs packages on the fly as they are needed. This can be useful for users
who do not want to download the entire distribution at once. However, it can be slower than TeX Live for users with
slow or unreliable internet connections. It can also be less stable than TeX Live as packages are updated more
frequently, which can lead to compatibility issues.

