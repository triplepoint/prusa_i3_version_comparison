# Introduction
This repository is an attempt to track the latest versions of 3d printable parts for the Prusa I3 MK2, MK2S, and MK2.5 printers.  

Prusa publishes a [Github repository](https://github.com/prusa3d/Original-Prusa-i3) with a few different collections of model files for the different printer versions.

In addition, [Prusa publishes printable parts](https://www.prusa3d.com/prusa-i3-printable-parts/) on their website as downloadable zip archives.

Prusa is doing a pretty good job of version control for the MK3, and keeping the changes to the parts pushed to the github repository.  They've even taken to embedding revision numbers directly into the part models themselves.

What isn't being clearly documented, however, is which releases map to which git commits.  Furthermore, the older variants of the Prusa i3 prior to the MK3 have no release version on the parts, and knowing what the "most recent release" is of these parts is difficult.

Finally, it's not clear whether the parts that are shipped with kits or pre-assembled printers are unmodified versions of any of the files available online.

# Mapping Downloaded files to Git Commits
## Complete Kit Zip Files
 Website Description | Downloaded | ZipFile | Zipfile MD5 Hash | Closest GIT commit | Notes
--- | --- | --- | --- | --- | ---
Complete Kits - Original Prusa i3 MK2 | 2018.07.28 | prusai3_mk2_stl.zip  | b1fb2f1724811baa4ab9f41d3ad5e7a7  | [59ded0560a96768a8f3cf4f666997bd75d1851a7](https://github.com/prusa3d/Original-Prusa-i3/tree/59ded0560a96768a8f3cf4f666997bd75d1851a7) | Identical *.stl files, however the released zipfile only contains the `./Printed-Parts/stl` subdirectory from the git repository.  The commit is significantly behind the `HEAD` of the `MK2` branch, and has no tag.
Complete Kits - Original Prusa i3 MK2S | 2018.07.28 | Original-Prusa-i3-MK2S.zip  | 8fcfacd8c158dbee0f7ce369f973c585  | [2f8c2ae17dc6fd653629e85a30fbf4cb65b8f7a3](https://github.com/prusa3d/Original-Prusa-i3/tree/2f8c2ae17dc6fd653629e85a30fbf4cb65b8f7a3) HEAD of the `MK2S` branch | Complete packaging of the git repo.
Complete Kits - Original Prusa i3 MK3 | 2018.07.28 | Original-Prusa-i3-MK3.zip  | 0cc62627c3ec0f7ceb1b20e34d1d4ea4  | [ad994c49ac9211c01122046ce410f98257c35ddf](https://github.com/prusa3d/Original-Prusa-i3/tree/ad994c49ac9211c01122046ce410f98257c35ddf) HEAD of the `MK3` branch | Complete packaging of the git repo.

## Upgrade Zip Files
Website Description | Downloaded | ZipFile | Zipfile MD5 Hash | Closest GIT commit | Notes
--- | --- | --- | --- | --- | ---
Upgrades - Original Prusa i3 MK2S -> MK2.5 upgrade | 2018.07.28 | mk25_upgrade_stl.zip | b83599a0727c96ca4c9c13e961c7e076 | [ae00eba29b9b54ca09ff344f08086e2d67345241](https://github.com/prusa3d/Original-Prusa-i3/tree/ae00eba29b9b54ca09ff344f08086e2d67345241) HEAD of the `MK2.5` branch, and [ad994c49ac9211c01122046ce410f98257c35ddf](https://github.com/prusa3d/Original-Prusa-i3/tree/ad994c49ac9211c01122046ce410f98257c35ddf) HEAD of the `MK3` branch | The files present in both the zipfile and the git `MK2.5` commit are identical.  However the zipfile only contains the `Printed-Parts\stl` subdirectory from the git repo, and reorganizes them in 2 different subdirectories.  Furthermore there are 6 files that appear to be from a second git commit in the MK3 branch: `extruder-body.stl`, `extruder-cover.stl`, `extruder-idler-plug.stl`, `extruder-idler.stl`, `filament-sensor-cover.stl`, and `nozzle-fan.stl`.
Upgrades - Original Prusa i3 MK2 -> MK2S upgrade | 2018.07.28 | mk2s_upgrade_stl.zip | bcb3408ac3b02f34caf7306d04e1f72f | [2f8c2ae17dc6fd653629e85a30fbf4cb65b8f7a3](https://github.com/prusa3d/Original-Prusa-i3/tree/2f8c2ae17dc6fd653629e85a30fbf4cb65b8f7a3) HEAD of the `MK2S` branch | The files in the zipfile appear to be a subset of the files in the `Printed-Parts/stl` directory in the git repo: `cable-holder.stl`, `extruder-body.stl`, `RAMBo_hinges.stl`, `RAMBo-base.stl`, `RAMBo-doors.stl`, `x-carriage.stl`, `Y-distance.stl`


# Complete File Sets for Upgraded Printers
In order to determine the most up-to-date set of files for an upgraded printer, it's necessary to take the complete release packages and replace the appropriate files from the upgrade packages.

Ignoring the Mk3 (for which the most up to date parts are clearly identifiable), we'll look at 3 different upgrade scenarios.  Each one corresponds to a branch on this repository, where the best attempt at a complete set of the most recently-available files are contained in a `release_files` subdirectory.

Scenario | branch Name | Notes
--- | --- | ---
MK2 -> MK2S | [`mk2_mk2s`](https://github.com/triplepoint/prusa_i3_version_comparison/tree/upgrade/mk2_mk2s/release_files) | TODO
MK2S -> MK2.5 | [`mk2s_mk25`](https://github.com/triplepoint/prusa_i3_version_comparison/tree/upgrade/mk2s_mk25/release_files) | TODO
MK2 -> MK2S -> MK2.5 | [`mk2_mk2s_mk25`](https://github.com/triplepoint/prusa_i3_version_comparison/tree/upgrade/mk2_mk2s_mk25/release_files) | TODO
