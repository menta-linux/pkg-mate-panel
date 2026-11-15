# pkg-mate-panel (Menta Linux)

Debian packaging of mate-panel 1.29.2 (from debian-mate-team/mate-panel on Salsa, 1.27.1-6).

- Configured with `--enable-wayland --with-in-process-applets=all`: clock, fish,
  notification-area and wncklet (window list, workspace switcher, window menu,
  show desktop) are loaded in-process from `/usr/lib/*/mate-panel/lib*-applet.so`;
  no `/usr/libexec/mate-panel` helpers or D-Bus factory services are shipped.
- The library soname moved to `libmate-panel-applet-4.so.2`, so the package is now
  `libmate-panel-applet-4-2`. Applets built against `.so.1` must be rebuilt.
- Build-depends on mate-desktop >= 1.29.1 (Menta `pkg-mate-desktop`) and
  libxfce4windowing >= 4.20.2.
- Versioning: `<upstream>-<rev>mentaN`; bump with `dch -i`.
- CI builds on push to `master`; tag `menta/<version>` publishes a GitHub release.
