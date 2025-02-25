# cameracarder

## installation

`brew install dericed/cameracarder/cameracarder`

## description

This script requires an Excel report from Treesize that includes the columns `Name` and `Folder Path`. `Size` and `Last Modified` are also recommended.

## how to use

`find_cards /path/to/treesize/report.xlsx`

This step will create 5 outputs alongside `report.xlsx`.

- `report.csv` this is a temporary output that is simply a csv version of the input `report.xslx` file.
- `report_MEDIA_FILES.csv` this is a summarization of the media files from the `report.csv` that includes files with `mov`, `mp4`, `mts` or `mxf` extensions.
- `report_LIKELY_SERVICE_FILES.csv` this lists files that use filenaming patterns that match those used by `AFP`, `AP`, `Reuters` or `Storyful`.
- `report_DUPLICATES` this report lists files with duplicate filenames and filesizes
- `report_MEDIA_CARDS.csv` this report summarizes `report_MEDIA_FILES.csv` to list folders that might include collections of camera card files.

## structure of report_MEDIA_CARDS.csv

This table includes a column called `is_it_a_card` which includes a value between 0 and 4. One point is given for the following qualities of a folder:
- Similar file names, in that many of the files match the same naming pattern with only numeric incrementation changing the filenames from file to file.
- Modification date range is less than 48 hours.
- The alphabetical first and last file of the folder share the same filename when numbers are excluded.
- There is more than one media file in that folder.'
