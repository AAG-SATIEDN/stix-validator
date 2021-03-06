# STIX Document Validator (sdv)
A python tool used to validate STIX v1.1 instance documents. For more information about the
Structured Threat Information eXpression, see http://stix.mitre.org.

## Dependencies
The STIX Document Validator has the following dependencies:
* Python v2.7 http://python.org/download
* lxml >= v3.2.0 http://lxml.de/index.html#download
  * libxml2 >= v2.9.1 http://www.xmlsoft.org/downloads.html
* xlrd >= v0.9.2 https://pypi.python.org/pypi/xlrd

**NOTE:** Older versions of libxml2 do not work properly and may result in undesirable behavior.
To see what version of libxml2 you have installed, execute the `xml2-config --version` command
and make sure you are running at least v2.9.1.

For a Windows installer of lxml, we recommend looking here: http://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml

## Use
The STIX Document Validator can validate a STIX v1.1 instance document against STIX v1.1 schemas
found locally or referenced remotely through the schemaLocation attribute. It can also perform
some 'best practice' guidance checks and STIX Profile validation and conversion to XSLT/Schematron.

**NOTE:** The STIX Profile validation and conversion capabilities should be considered **experimental.**

**Validate using local schemas**  
`python sdv.py --input-file <stix_document.xml> --schema-dir schema`

**Validate using schemaLocation**  
`python sdv.py --input-file <stix_document.xml> --use-schemaloc`

**Validate a directory of STIX documents**  
`python sdv.py --input-dir <stix_dir> --schema-dir schema`

**Check "best practice" guidance**  
`python sdv.py --input-file <stix_document.xml> --schema-dir schema --best-practices`

**Validate using STIX Profile**  
`python sdv.py --input-file <stix_document.xml> --schema-dir schema --profile <stix_profile.xlsx>`

**Translate STIX Profile to XSLT/Schematron**  
`python sdv.py --profile <stix_profile.xlsx> --xslt-out <stix_profile.xslt> --schematron-out <stix_profile.sch>`

## All STIX Documents?
The STIX Document Validator bundles a schema directory with it, which includes all STIX v1.1 
schema files. If an instance document uses constructs or languages defined by other schemas
a user must point the STIX Document Validator at those schemas in order to validate.

## Terms
BY USING THE STIX DOCUMENT VALIDATOR, YOU SIGNIFY YOUR ACCEPTANCE OF THE 
TERMS AND CONDITIONS OF USE.  IF YOU DO NOT AGREE TO THESE TERMS, DO NOT USE 
THE STIX DOCUMENT VALIDATOR.

For more information, please refer to the LICENSE.txt file
