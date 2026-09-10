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

## NWO_Papillion structural evidence (user clarification, 2026-09-10)

`NWO_Papillion_ColeCreek_Stream.gdb` supplements the Cole Creek R1 Survey Event
archives with surviving parent-level project artifacts. Preserve it as source
evidence; it is not an example of the future standardized hierarchy format.

- Study Area name: **NWO_Papillion** (USACE district code plus Study Area name).
- `Papillion_HUC12`: the analyst selected these seven polygons to define the
  **Stream areas**, using the retained HUC12 names for Stream names. This project's
  choice supports familiar customer scale and naming; HUC12-based segmentation
  or naming is **not a general FluvialGeomorph requirement**.
- The user specifies that the **Study Area polygon is the dissolved union** of
  these edge-matching Stream areas, removing their internal shared boundaries.
- `Papillion_flowline`: manually developed Stream/Reach structure evidence. Its
  100 features have repeated labels/geometries and differing measure attributes;
  these are not automatically 100 Reaches or a uniquely resolved network.
- `ColeCreek_flowline_200`: five polygons labelled Cole Creek R1–R5. Their use as
  governed Reach AOIs has not been confirmed by the above clarification.

Spatial inspection places the retained 2006 Cole Creek R1 flowline wholly within
HUC12 102300060204, **Little Papillion Creek**. That parent association is an
inference from geometry, distinct from the user's confirmed project conventions.
The three retained R1 Survey Events remain 2006, 2010 and 2016. This does not
establish complete Reach or Survey Event coverage for the other Stream areas.

Future local storage must make hierarchy levels, identities, parentage and
boundary/naming rationale explicit instead of relying on layer names or expert
memory. The updated fluvgeo demonstration uses this interpretation without
repairing the archived flowlines or changing these source files.
