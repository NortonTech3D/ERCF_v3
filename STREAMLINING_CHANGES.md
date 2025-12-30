# Repository Streamlining Changes

This document describes changes made to reduce redundancy and improve organization of the ERCF v3 repository.

## Summary

- **10 duplicate STL files removed** (~689KB saved)
- **11 README files standardized** (readme.md → README.md)
- **New shared directories created** for common parts
- **.gitignore improved** (removed redundant entries)

## File Location Changes

### Electronics Mount Hinges (Consolidated)

**Old Locations** (duplicates removed):
- `STLs/Electronics/EASY_BRD_Box/Mount_hinge_90_v03.stl` ❌
- `STLs/Electronics/EASY_BRD_Box/Mount_hinge_long_90_v01.stl` ❌
- `STLs/Electronics/ERB_Box/Mount_hinge_90_v03.stl` ❌
- `STLs/Electronics/ERB_Box/Mount_hinge_long_90_v01.stl` ❌
- `STLs/Electronics/MMBv1_Box/Mount_hinge_90_v03.stl` ❌
- `STLs/Electronics/MMBv1_Box/Mount_hinge_long_90_v01.stl` ❌
- `STLs/Electronics/MMBv2_Box/Mount_hinge_90_v03.stl` ❌
- `STLs/Electronics/MMBv2_Box/Mount_hinge_long_90_v01.stl` ❌

**New Location**:
- `STLs/Electronics/Common_Parts/Mount_hinge_90_v03.stl` ✅
- `STLs/Electronics/Common_Parts/Mount_hinge_long_90_v01.stl` ✅

**Action Required**: When building any electronics box, print the mount hinges from the `Common_Parts` directory.

### Encoder Slotted Wheel (Consolidated)

**Old Locations** (duplicates removed):
- `STLs/7._Encoder/623_Bearing/[o]_Encoder_Slotted_Wheel_8_tooth.stl` ❌
- `STLs/7._Encoder/v623zz_Bearing/[o]_Encoder_Slotted_Wheel_8_tooth.stl` ❌

**New Location**:
- `STLs/7._Encoder/[o]_Encoder_Slotted_Wheel_8_tooth.stl` ✅

**Action Required**: When building any encoder variant, print the slotted wheel from the parent `7._Encoder` directory. This file is shared by all bearing types (623, v623zz, and 625).

### Selector Door (Duplicate Removed)

**Old Location** (removed):
- `STLs/6._Selector/Selector_Door.stl` ❌

**Current Location**:
- `STLs/6._Selector/Selector_Door_Multicolor_Option/[mm]_Selector_Door.stl` ✅

**Action Required**: Use the selector door from the `Selector_Door_Multicolor_Option` directory. This is the same file that was previously duplicated in the parent directory.

## README Naming Standardization

All README files have been renamed to use consistent capitalization: `README.md`

**Files Renamed**:
- `Documentation/readme.md` → `Documentation/README.md`
- `PCBs/readme.md` → `PCBs/README.md`
- `Recommended_Options/readme.md` → `Recommended_Options/README.md`
- `STLs/9._LEDs/readme.md` → `STLs/9._LEDs/README.md`
- Various User_Mods readme.md files → README.md

## .gitignore Improvements

Removed redundant `.DS_Store` entries and added comprehensive OS and editor-specific file patterns.

## Intentional Duplicates (Not Changed)

The following files have the same name but are **intentionally different** for different variants:

- **User_Mods/kieraneglin/Thumper-Blocks/** - Different files for Rev_1, Rev_2, Rev_3 variants
- **User_Mods/Mneuhaus/** - Different encoder parts for different bearing types (diffuser is shared, but organized per bearing variant)

## Benefits

1. **Reduced Repository Size**: ~689KB of duplicate files removed
2. **Improved Organization**: Common parts in dedicated directories
3. **Better Consistency**: Standardized README naming
4. **Easier Maintenance**: Single source of truth for shared components
5. **Clearer Documentation**: Each shared component directory has its own README

## Questions?

If you have questions about these changes or need help finding a file, please open an issue on the GitHub repository.
