# ------------------------------------------------------------------------------
# *_*OOSEXGANG FLASHER*_*
# ------------------------------------------------------------------------------

# This script is a simple and universal firmware flasher. It's functionally
# similar to other flashers, but easier to configure.

# Key features:

# - Supports device codename checking. You can define supported devices via:
#     support_devices="redwood marble psyche"

# - Supports 3 types of image files: raw (.img), zst (.img.zst), and gz (.img.gz)
#   By default, the script uses:
#     compressor="zstd"
#     file_type="zst"
#
#   To switch to gzip, for example:
#     compressor="gzip"
#     file_type="gz"

# - Extremely easy to configure. You only need to change two lines:
#     support_devices="redwood"
#     rom="HelloUI"

# - To specify the slot for each firmware image, simply rename the file:
#     boot_a.img.zst or boot_b.img.zst
#     boot_a.img.gz or boot_b.img.gz
#     For raw: boot_a.img

# - Supports flashing cust.img (if present)
# - Does not support non-A/B devices

# - Important: 
#     - Do not include slot suffix (_a/_b) in filenames for:
#         - super.img
#         - cust.img
#     - All firmware partitions (including super and cust) must use the same format:
#         compressor="zstd"
#         file_type="zst"

# - And of course, to flash your own additional image, 
#   just add its name to the META-INF/list file inside the ROM zip.
