# Introduction

Finding ICD-10-CM codes is kind of annoying. This repo shows you where the
simple text file versions are found. 

# Download

There are copies of the files in this repo, but they can also be found on the website of the
[CDC](https://ftp.cdc.gov/pub/Health_Statistics/NCHS/Publications/ICD10CM/2024-Update/).

1. Download "icd10cm-Codes-Descriptions-April-2024.zip"
1. Unzip and the two relevant files are named icd10cm-codes-April-2024.txt and 
icd10cm-order-April-2024.txt
1. These are fixed width files hence each field takes up the same amount of 
characters
1. See the descriptions in the section below for the widths

# Fixed Width Files

## Codes File

| Position | Length | Contents                                             |
|----------|--------|------------------------------------------------------|
| 1        | 7      | ICD-10-CM or ICD-10-PCS code. Dots are not included. |
| 8        | 1      | Blank                                                |
| 9        | To end | Long description                                     |

## Order File

| Position | Length | Contents                                                                                                                                         |
|----------|--------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 1        | 5      | Order number, right justified, zero filled.                                                                                                      |
| 6        | 1      | Blank                                                                                                                                            |
| 7        | 7      | ICD-10-CM or ICD-10-PCS code. Dots are not included.                                                                                             |
| 14       | 1      | Blank                                                                                                                                            |
| 15       | 1      | 0 if the code is a “header” –not valid for HIPAA-covered transactions.<br/>1 if the code is valid for submission for HIPAA-covered transactions. |
| 16       | 1      | Blank                                                                                                                                            |
| 17       | 60     | Short description                                                                                                                                |
| 77       | 1      | Blank                                                                                                                                            |
| 78       | To end | Long description                                                                                                                                 |

# Usage

Load in a fixed width file in whichever language you wish. For Python pandas,

```
pd.read_fwf()
```

# Authors
- Dan Weiss (2024)