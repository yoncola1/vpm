# vpm package manager for vomP

`vpm` installs packages from Alpine repositories on vomP/musl systems.

## Quick install

1. Create a file named `vpm`.
2. Paste the contents of the `code` file into `vpm`.
3. Run: `sudo chmod +x ./vpm`.

## v0.3 fixes

This version tries to make simple packages work without manual rescue steps:

- installs direct Alpine dependencies before the requested package;
- upgrades `musl` first when the host runtime is too old for Alpine edge packages;
- runs APK `.pre-install` and `.post-install` scripts when present;
- applies post-install runtime fixes for musl loader/libc symlinks;
- installs `ncurses-terminfo-base` automatically for terminal programs such as `nano`, `fastfetch`, `htop`, `vim`, and `neovim`;
- records installed file lists so `vpm remove` can clean files more reliably.
