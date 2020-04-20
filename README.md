# makefake

Create fake pacman packages to satisfy dependencies that should be optdepends in the first place!

This script generates a PKGBUILD for an almost empty package, then builds and installs it with makepkg. Run `./makefake --help` for usage, or just run `./makefake --version 1.2.3 legitpackage` for the most common scenario. Your fake package can provide multiple packages, just add more package names.

Note that `IgnorePkg` in `/etc/pacman.conf` achieves similar results - this script should be used only if that solution doesn't satisfy you for some reason. In my case that's because I sync `/etc/pacman.conf` between all my computers and cannot install certain packages on one of them due to odd constraints on that machine. Just faking some packages is easier this way.

**DON'T REPORT BUGS IN ARCH PACKAGES IF YOU HAVE FAKED ANY DEPENDENCIES IN THEIR PACTREE. DON'T FAKE BASE OR BASE-DEVEL PACKAGES.** If you want to fake install `gtk3`, sure, you can do that, but don't be surprised when all Gtk+3 apps stop working. This is a dangerous tool - use it wisely and sparingly.
