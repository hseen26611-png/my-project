# TECNO BG7n — KernelSU + SUSFS build harness

This project uses the exact AOSP Android 12 / 5.10 GKI release that matches the stock BG7n kernel lineage:

- Kernel: 5.10.237
- GKI branch: `android12-5.10-2025-06`
- Release tag: `android12-5.10-2025-06_r3`
- Stock kernel suffix: `d09ef2e980e0`
- Compiler: Android Clang 12.0.5 / r416183b
- Target: ARM64
- Device: TECNO BG7n / MT6765

The workflow first integrates official KernelSU and then applies the SUSFS 2.2.0 Android 12 / 5.10 patch set.

## Important

This produces a **test kernel Image only**. It does not flash anything and it does not replace the stock boot image.

Do not flash the artifact until:
1. the build succeeds;
2. the resulting kernel is checked against the stock config/KMI;
3. the stock `boot.img` header/ramdisk/DTB layout is verified;
4. the Image is repacked into a copy of the original boot image;
5. a recovery/restore path is ready.

The original stock boot image must remain untouched.
