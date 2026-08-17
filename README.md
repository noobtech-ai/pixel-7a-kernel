# Pixel 7a — 6.1.145 R8 + R11 Performance Builder

This is a one-click GitHub Actions builder prepared for the requested target:

- Pixel 7a (`lynx`)
- Android 14 GKI
- Linux 6.1.145
- WildKernels R8 build system
- KernelSU-Next
- SUSFS
- R8 experimental performance patch set enabled
- R11-style HZ=300
- BBRv3
- Forced TCP_NODELAY patch excluded
- NoMount / PathHide intentionally excluded from this first build

## Very simple setup

1. Create a new EMPTY GitHub repository.
2. Upload the `.github` folder from this package.
3. Open the repository's **Actions** tab.
4. Select **Pixel 7a 6.1.145 R8 Performance Build**.
5. Press **Run workflow**.
6. Wait for it to finish.
7. Open the completed run and download:
   `6.1.145-android14-2025-09-R8-R11-Performance-AnyKernel3`

You do NOT need to install Linux or compile anything locally.

## Important

This workflow builds the kernel using the official WildKernels R8 build system and
its 6.1.145 Android 14 target. It enables the R8 performance action that is disabled
by default. The forced TCP_NODELAY patch is removed before the performance action runs.

The first build deliberately does not add NoMount/PathHide. Test the performance
kernel first.

Do not flash a 6.1.174 kernel onto a 6.1.145 installation. Keep your working R8
kernel/boot image available so you can recover if the experimental build does not boot.
