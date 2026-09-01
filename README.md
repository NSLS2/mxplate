# mxplate
X-ray crystallographic fragment screening LIMS

## Overview
This is a python application for creating a local sqlite db file in a beamline project directory that captures information about crystal plates, fragment/compound library plates, and harvest information such as soak time, puck ID, and puck position. It is designed to be run through the [NSLS2 jupyter hub ](https://jupyter.nsls2.bnl.gov), but can also be run from a local notebook server. The final database will contain a relational database schema that maps a library compound ID to a diffraction dataset name. The general workflow is:

```
1. Image plates
2. Import completed imaging csv files
3. Create library plate to xtal well mapping
4. Perform Echo transfer
5. Generate harvest csv file
6. Load harvest csv file in shifter
7. Harvest plate
8. Import completed harvest csv file
9. Generate beamline spreadsheet
```

Supported library plates:
```
384-well (Echo LDV/PP)
1536-well (Echo)
```

Supported crystal plates:
```
3-well SWISSCI MRC low profile (preferred default)
3-well SWISSCI MRC
2-well SWISSCI MRC
3-well Intelliplate
2-well Intelliplate
```

## Setup
Prior to project initialization NSLS-II fragment lab staff will copy the template database init notebook to the project directory and edit cells according to user project requirements.

## Usage
Your local contact will provide you with your project directory. Multiple users can have read access to the experiment notebook, but only one user at a time should attempt to import or edit imaging/harvesting files. Users will log in to [NSLS-II jupyter hub](https://jupyter.nsls2.bnl.gov) and follow the instructions for each notebook widget in the experiment run notebook.

