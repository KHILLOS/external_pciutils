# Modification Map: external/pciutils

## Source: BlissOS android-x86 reference (external/pciutils)
- BlissOS reference: android-x86/external/pciutils (pciutils v3.13.0 with mods)
- UPSTREAM commits:
  - 5aeb22b (Port pciutils v3.15.0 to Android 17: re-express 8 BlissOS mods on upstream base)
  - bbb5185 (Android.bp: add Soong build for pciutils - KhillOS port)
  - b424ac8 (Released as v3.15.0 - upstream tag)
- Upstream base: pciutils v3.15.0 (git.kernel.org)

## Modifications Applied to UPSTREAM/external_pciutils (khillos-17 branch)

### 1. Android.bp Build System (UPDATED from commit 5aeb22b)
**Ported BlissOS modifications to pciutils v3.15.0 base:**
- `cc_genrule` libpci_config and libpci_includes → replaced with simpler `genrule` pciutils_config_h
- `cc_library_static` libpci with updated source list (v3.15.0 files)
- `cc_binary` lspci with v3.15.0 source list
- `genrule` pci_ids_uncompressed for pci.ids deployment
- License module: external_pciutils_license (GPL-2.0-or-later, COPYING)
- Added vendor_available, host_supported, product_available, ramdisk_available, vendor_ramdisk_available, recovery_available
- Added min_sdk_version: 29, apex_available, native_bridge_supported

### 2. Source Code Updates (From BlissOS commits)
**Files updated in commit 5aeb22b (v3.15.0 port):**
- All source files updated to pciutils v3.15.0 upstream
- 8 BlissOS modifications re-expressed on upstream base
- Version bump: v3.13.0 → v3.15.0

### 3. AOSP 17 Compliance Metadata Files (NEW)
**Files:** `METADATA`, `MODULE_LICENSE_GPL2`, `OWNERS`, `NOTICE`
- METADATA: Package metadata per AOSP external_updater format
- NOTICE: Comprehensive GPL-2.0-or-later notice with copyright
- MODULE_LICENSE_GPL2: SPDX identifier for Soong license module
- OWNERS: Standard AOSP OWNERS file

### 4. SPDX Headers (ADDED to 5 missing files)
**Files:** example.c, compat/getopt.h, compat/getopt.c, lib/i386-io-openbsd.h, lib/win32-helpers.h
- Added SPDX-License-Identifier: GPL-2.0-or-later to files missing it

## Summary
- **Total files modified:** 5 source files (SPDX) + Android.bp + 4 metadata = 10
- **Source files:** 5 files with SPDX headers added (others already had them)
- **Build system:** Android.bp updated for v3.15.0 with AOSP 17 conventions
- **Logic/behavior changes:** pciutils v3.13.0 → v3.15.0 with 8 BlissOS mods re-expressed
- **AOSP 17 compliance:** All required metadata files added
