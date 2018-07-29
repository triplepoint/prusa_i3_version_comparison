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
Complete Kits - Original Prusa i3 MK2 | 2018.07.28 | prusai3_mk2_stl.zip  | b1fb2f1724811baa4ab9f41d3ad5e7a7  | [59ded0560a96768a8f3cf4f666997bd75d1851a7](https://github.com/prusa3d/Original-Prusa-i3/tree/59ded0560a96768a8f3cf4f666997bd75d1851a7) | Identical *.stl files, however the released zipfile only contains the `./Printed-Parts/stl` subdirectory from the git repository.  The commit is significantly behind the `HEAD` of the `MK2` branch, and is an anonymous commit with no tag.  It's unclear what relevance the changes to the `MK2` branch since this commit have.
Complete Kits - Original Prusa i3 MK2S | 2018.07.28 | Original-Prusa-i3-MK2S.zip  | 8fcfacd8c158dbee0f7ce369f973c585  | [2f8c2ae17dc6fd653629e85a30fbf4cb65b8f7a3](https://github.com/prusa3d/Original-Prusa-i3/tree/2f8c2ae17dc6fd653629e85a30fbf4cb65b8f7a3) HEAD of the `MK2S` branch | Complete packaging of the git repo.
Complete Kits - Original Prusa i3 MK3 | 2018.07.28 | Original-Prusa-i3-MK3.zip  | 0cc62627c3ec0f7ceb1b20e34d1d4ea4  | [ad994c49ac9211c01122046ce410f98257c35ddf](https://github.com/prusa3d/Original-Prusa-i3/tree/ad994c49ac9211c01122046ce410f98257c35ddf) HEAD of the `MK3` branch | Complete packaging of the git repo.

## Upgrade Zip Files
Website Description | Downloaded | ZipFile | Zipfile MD5 Hash | Closest GIT commit | Notes
--- | --- | --- | --- | --- | ---
Upgrades - Original Prusa i3 MK2S -> MK2.5 upgrade | 2018.07.28 | mk25_upgrade_stl.zip | b83599a0727c96ca4c9c13e961c7e076 | [ae00eba29b9b54ca09ff344f08086e2d67345241](https://github.com/prusa3d/Original-Prusa-i3/tree/ae00eba29b9b54ca09ff344f08086e2d67345241) HEAD of the `MK2.5` branch, and [ad994c49ac9211c01122046ce410f98257c35ddf](https://github.com/prusa3d/Original-Prusa-i3/tree/ad994c49ac9211c01122046ce410f98257c35ddf) HEAD of the `MK3` branch | The files present in both the zipfile and the git `MK2.5` commit are identical.  However the zipfile only contains the `Printed-Parts\stl` subdirectory from the git repo, and reorganizes them in 2 different subdirectories.  Furthermore there are 6 additional files in the zipfile that appear to be from a second git commit in the MK3 branch: `extruder-body.stl`, `extruder-cover.stl`, `extruder-idler-plug.stl`, `extruder-idler.stl`, `filament-sensor-cover.stl`, and `nozzle-fan.stl`.
Upgrades - Original Prusa i3 MK2 -> MK2S upgrade | 2018.07.28 | mk2s_upgrade_stl.zip | bcb3408ac3b02f34caf7306d04e1f72f | [2f8c2ae17dc6fd653629e85a30fbf4cb65b8f7a3](https://github.com/prusa3d/Original-Prusa-i3/tree/2f8c2ae17dc6fd653629e85a30fbf4cb65b8f7a3) HEAD of the `MK2S` branch | The files in the zipfile appear to be a subset of the files in the `Printed-Parts/stl` directory in the git repo: `cable-holder.stl`, `extruder-body.stl`, `RAMBo_hinges.stl`, `RAMBo-base.stl`, `RAMBo-doors.stl`, `x-carriage.stl`, `Y-distance.stl`.


# Complete File Sets for Upgraded Printers
We'd like to know, for a given printer upgrade scenario, which files represent the final collection of printed parts in the printer.  This can be determined by taking a complete release package and replacing the appropriate files with new files from the upgrade packages.

Ignoring the MK3, we'll look at 3 different upgrade scenarios involving the MK2, MK2S, and MK2.5.  Each one corresponds to a branch named `upgrades/*` on this repository, where the best attempt at a complete set of the most recently-available files are contained in a `release_files` subdirectory.

Note that only the `*.stl` files were committed in these branches, though the MK2 and MK2S complete zipfiles also included the `*.scad` files.

Also, note that the filenames in the various repositories were changed to make it easier to compare branches.  See the end notes for details on how these names changed.

Scenario | Branch Name | Notes
--- | --- | ---
MK2 -> MK2S | [`mk2_mk2s`](https://github.com/triplepoint/prusa_i3_version_comparison/tree/upgrade/mk2_mk2s/release_files) | Note this starts from the zipfile MK2 files, not the head of the MK2 branch in the git repository.
MK2S -> MK2.5 | [`mk2s_mk25`](https://github.com/triplepoint/prusa_i3_version_comparison/tree/upgrade/mk2s_mk25/release_files) |
MK2 -> MK2S -> MK2.5 | [`mk2_mk2s_mk25`](https://github.com/triplepoint/prusa_i3_version_comparison/tree/upgrade/mk2_mk2s_mk25/release_files) |

Of note, the upgrade path from the `MK2 -> MK2S` does not end up with the same `*.stl` files as the `MK2S` kit files, though no attempt was made here to characterize the differences.

Similarly, the `MK2 -> MK2S -> MK2.5` upgrade results in different files from the `MK2S -> MK2.5` upgrade.  Again, it's not clear how big the differences are.

# Reprinting Parts
Finally, we'd like to answer the question "for the MK2, MK2S, or MK2.5, what is the most recent set of printable parts?".  Summarizing the results above, we can say:

Printer   | Most Recent Parts
--- | ---
MK2 |  This is an open question.  [The git repository saw major changes between the commit which the release zipfile was made from and the `MK2` branch HEAD](https://github.com/prusa3d/Original-Prusa-i3/compare/59ded0560a96768a8f3cf4f666997bd75d1851a7...MK2).  The git commit messages are not clear and don't explain all of the changes.
MK2S  | The files in the zipfile are the latest versions from the git repo, so unless there are unreleased versions internal to Prusa Research, [the zip file](https://www.prusa3d.com/prusa-i3-printable-parts/) is the best version.
MK2.5 | The parts you end up with if you upgrade a MK2 to a MK2S and then a MK2.5 are different from the parts you end up with converting a MK2S to a MK2.5.  The [MK2S -> MK2.5 branch in this repository](https://github.com/triplepoint/prusa_i3_version_comparison/tree/upgrade/mk2s_mk25/release_files) should be the most up to date files we know.


# End Notes
## Normalization of Package Filenames
All files in the release and upgrade branches were normalized by running the following commands before committing them:

``` bash
chmod 644 release_files/*.stl
rename -e 's/-/_/g' release_files/*.stl
rename -e 'y/A-Z/a-z/' release_files/*.stl
mv release_files/lcd_supporta.stl release_files/lcd_support_a.stl
mv release_files/lcd_supportb.stl release_files/lcd_support_b.stl
mv release_files/lcd_cover*.stl release_files/lcd_cover.stl
mv release_files/nozzle_fan.stl release_files/fan_nozzle.stl
mv "release_files/spool holdahmk3.stl" release_files/spool_holder.stl
```
