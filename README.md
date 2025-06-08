*_*OOSEXGANG FLASHER*_* BY SHIMOKU

A simple and universal hybrid ROM flasher

This script is functionally similar to other flashers, but much easier to configure. Supports compressed and raw image formats, device validation, and slot-based flashing. Designed to be used in recovery.

Features:
- Device codename check using:
  support_devices="redwood marble psyche"
  
- Image format support:
  Raw (.img)
  Zstandard (.img.zst)
  Gzip (.img.gz)

  Default configuration:
    compressor="zstd"
    file_type="zst"

  Switch to gzip:
    compressor="gzip"
    file_type="gz"

- Minimal configuration required:
    support_devices="redwood"
    rom="HelloUI"

- Slot-based flashing:
  Rename files like:
    boot_a.img.zst
    vendor_a.img.zst
    dtbo_a.img.zst
    vbmeta_a.img.zst
    super.img.zst
    cust.img.zst


- Automatically detects current slot (_a or _b) based on file names in the archive
- cust.img flashing is supported
- Non-A/B devices are not supported

- Do not add _a or _b suffix for:
    super.img
    cust.img

- All firmware files must use the same format as defined in:
    compressor="zstd"
    file_type="zst"

To flash additional images like cust add name in META-INF/list
  META-INF/list

Example:
  boot
  dtbo
  vendor_boot
  super
  cust

ROM Archive Structure Example:

META-INF/zstd or META-INF/gzip
META-INF/list
boot_a.img.zst
vendor_a.img.zst
super.img.zst
cust.img.zst

Notes

- The ROM ZIP must include the correct binary in META-INF/zstd or META-INF/gzip
- Partitions listed in META-INF/list will be flashed automatically
- Sparse images are not supported in this script
