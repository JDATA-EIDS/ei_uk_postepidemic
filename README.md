# Equine Influenza (UK 2020–2024) – Data Repository

Data associated with the study of the epidemiology of H3N8 equine influenza (EI) virus infections in the United Kingdom (UK) since the 2019 European epidemic.

This repository provides de-identified data accompanying the publication:

> Whitlock F., Grewar J., Newton R. (2025). *What happened after the epidemic? Equine influenza surveillance sheds light on sources and seasonal risk in the United Kingdom.*\
> Department of Veterinary Medicine, University of Cambridge, and jDATA (Pty) Ltd, South Africa.

## Overview

These datasets represent the collated surveillance, case, movement and risk information used to analyse equine influenza (EI) activity in the United Kingdom from 2020 to 2024.\
Each file represents a thematic component of the dataset, linked primarily via the variable `outbreakid` and/or `caselogid`.

All data are de-identified and aggregated to preserve confidentiality of participating premises.

## File Descriptions

| File | Description |
|------------------------|------------------------------------------------|
| **alltestdata.csv** | Laboratory test-level dataset at case level containing confirmed EI case test results, test methods, and associated outbreak identifiers. |
| **casedata.csv** | Case-level metadata describing individual cases, including breed, age, sex, vaccination status, and premises details. Aggregation data at holding level is included such as census and total vaccinated and or clinically affected by EI on the affected premises. |
| **location.csv** | Location reference data at outbreak (holding) level, including regional identifiers and region names (UK). |
| **movementdata.csv** | Movement data at outbreak (holding) level, including recent arrivals, departures, temporal and other epidemiologic variables associated with tracing. |
| **riskdata.csv** | Risk exposure data at outbreak (holding) level. |

## Data Linkages

The principal linking field across all datasets is **`outbreakid`** and **`caselogid`**.

## Licence

Data are provided under a **GNU GENERAL PUBLIC LICENSE** — reuse permitted with appropriate attribution.

## Data descriptions and types

### `alltestdata.csv`

**Number of rows:** 218\
**Number of columns:** 9

| Column | Type | Description |
|---------------------|-------------------|--------------------------------|
| `outbreakid` | integer | Unique identifier linking this record to a confirmed outbreak |
| `caselogid` | integer | Unique identifier linking this record to a confirmed case |
| `sampdate` | character | Date sample was collected |
| `testinglab` | integer | Laboratory identifier code |
| `test` | character | Type of diagnostic test performed |
| `testtarget` | character | Disease tested for |
| `resultcat` | character | Result category |
| `characteristicvalue` | integer | Numeric test result or Ct value where applicable |

------------------------------------------------------------------------

## `casedata.csv`

**Number of rows:** 149\
**Number of columns:** 23

| Column | Type | Description |
|---------------------|-------------------|--------------------------------|
| `outbreakid` | integer | Unique identifier linking this record to a confirmed outbreak |
| `caselogid` | integer | Unique identifier linking this record to a confirmed case |
| `casedate` | date | Initial date of case onset or diagnosis |
| `casedateupdate` | date | Associated final case date based on case data |
| `accuracy` | character | Level of accuracy of `casedateupdate` |
| `census` | integer | Number of equids on the outbreak premises |
| `numberclinical` | integer | Number of clinically affected equids on the outbreak premises |
| `numbervaccinated` | integer | Number of vaccinated equids on the outbreak premises |
| `breedgen` | character | General breed group (e.g., native, sport horse) |
| `breed` | character | Specific breed (e.g., Cob, Irish Sport Horse) |
| `sexgen` | character | Sex category |
| `age` | numeric | Horse age in years |
| `premisestype` | character | Type of premises (e.g., livery, private, training) |
| `vaccstatus` | character | Vaccination status (e.g., vaccinated, unvaccinated) |
| `vaccdate` | date | Date of last vaccination |
| `vaccclass` | character | Class of vaccination (e.g., booster, V2) |
| `vaccinfo` | character | Vaccine brand or additional information |
| `dayssincevaccination` | integer | Days between vaccination and updated case date |
| `earliestsample` | date | Date of earliest laboratory sample |
| `premisescategory` | character | Categorisation of outbreak premises (e.g., competition yard, stud) |

------------------------------------------------------------------------

## `location.csv`

**Number of rows:** 126\
**Number of columns:** 3

| Column | Type | Description |
|---------------|---------------|------------------------------------------|
| `outbreakid` | integer | Unique identifier linking this record to a confirmed outbreak |
| `regiongid` | integer | Geographic region or polygon identifier |
| `regionname` | character | Name of county or region |

------------------------------------------------------------------------

## `movementdata.csv`

**Number of rows:** 116\
**Number of columns:** 9

| Column | Type | Description |
|---------------------|-------------------|--------------------------------|
| `outbreakid` | integer | Unique identifier linking this record to a confirmed outbreak |
| `movementcategorydirection` | character | Direction of movement (incoming/outgoing) |
| `movementcategoryanimalclass` | character | Animal class associated with movement |
| `movementcategorytime` | character | Permanent or Temporary movement |
| `timeperiod` | character | Time frame relative to outbreak (e.g., \< 1 week) |
| `associatedholdingtype` | character | Type of associated holding or source premises |
| `movementquantityactual` | integer | Number of animals moved where known |
| `quantity` | character | Reported or categorical quantity class |

------------------------------------------------------------------------

## `riskdata.csv`

**Number of rows:** 353\
**Number of columns:** 4

| Column | Type | Description |
|---------------------|-------------------|--------------------------------|
| `outbreakid` | integer | Unique identifier linking this record to a confirmed outbreak |
| `riskclass` | character | Category of risk (e.g., biosecurity, management, grazing) |
| `risksubclass` | character | Subclassification of risk class |
| `quantity` | character | Associated risk quantity or level |
