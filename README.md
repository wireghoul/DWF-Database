# DWF-Database
This repository contains DWF assignments, one CSV file per year (it may be sharded in future if we have enough CVE assignments every year), one row per assignment. 

## DWF Database Format

### DWF_ID

The CVE ID assigned for this issue.

This field is mandatory.

### DATE_ASSIGNED

The date this CVE was assigned privately or publicly. 

This field is mandatory.

### DATE_PUBLIC

The date this CVE was made public. 

This field is optional but strongly reccomended as part of the CNA feedback process. 

### REQUESTER

The email address of the assigner or an email contact for the CNA/organization they work for.

This field is optional as some researchers prefer to stay anonymous. 

### ASSIGNER

The email address of the assigner or an email contact for the CNA/organization they work for.

This field is optional but strongly reccomended as part of the CNA feedback process. 

### REPLACED_BY

A list of one or more CVE's that have replaced this entry and what the relationship is (e.g. a CVE split may break a single existing CVE into multiple CVEs). The format is RELATION:CVE, if there are multiple entries they are comma separated (the entire field is quoted). Valid relationships are currently:

* DUPLICATE_OF
* SPLIT_TO
* SPLIT_FROM
* MERGED_TO
* MERGED_FROM
* REJECT

This field is only used if the CVE is split/merged/found to be a duplicate or rejected.

### VERSION

Version of the entry, numeric, sequential (in case it is updated more than once in a single day for example), starts at 1.

This field is mandatory.

### LAST_UPDATE

The date (YYYY-MM-DD) this entry was last updated.

This field is mandatory if the entry is updated (e.g. version is 2 or more).

### STATE

The state of this CVE, valid states include:

* RESERVED
* PUBLIC
* CONFRIMED
* REJECTED
* REPLACED (see REPLACED_BY field for more details)

### TITLE

This is a short title for the issue, e.g. "Product Name v1.2.3 buffer overflow flaw in foo()".

This field is optional but strongly reccomended as part of the CNA feedback process. 
