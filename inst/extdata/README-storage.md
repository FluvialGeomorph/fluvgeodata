# Fixture storage and open-source migration

Accepted direction, 2026-09-07: preserve existing File GDB fixtures as historical
evidence. New qualified migration fixtures use Reach–Survey–Event folders with
GeoPackage vectors/tables, external GeoTIFF terrain and explicit metadata links.
The folder, not one GeoPackage, is the complete delivery unit.

Some Esri GeoPackage raster-tile support exists; faithful analytical terrain
coverage and metadata interoperability must not be inferred from display success.
See the [cross-repository decision](https://github.com/FluvialGeomorph/FG-architecture/blob/main/dev/decisions/adr-0004-folder-based-spatial-deliverables.md)
and [folder requirements](https://github.com/FluvialGeomorph/FGDB/blob/main/dev/schemas/local-project-folder-requirements.md).

Fixture additions must retain provenance, source checksums, explicit event/shared
terrain associations, original and interpreted CRS, vertical reference/units,
grid/pixel/NoData information and any required companion files. Unknown metadata
stays unknown. Include relocation, missing-file and conflicting-metadata cases
alongside successful conversions. Tests work in temporary copies, not these archives.

The earlier Cole Creek raster-GeoPackage probe in fluvgeo is experimental evidence,
not the selected delivery profile. No fixtures have been converted by this record.

The user reaffirmed this choice on 2026-09-08 after the
[completed ArcGIS experiment](https://github.com/FluvialGeomorph/FGDB/blob/df01025/dev/experiments/geopackage-raster/FINAL-FINDINGS.md):
numerical GeoPackage reads worked, but the tested ArcGIS creation route changed
terrain to Byte/PNG imagery. Retain originals and add separately qualified
folder/GeoTIFF fixtures; successful raster display is not fixture acceptance.
