# Constraints

**Purpose**: Verify that the features provided in the dataset adhere to the constraints specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following check is performed for every feature in the dataset.

* Check that at least one of the [function](#function) attributes of the Holding spatial object is provided using the [EconomicActivityNACEValue](http://inspire.ec.europa.eu/codelist/EconomicActivityNACEValue) code list for the [activity](#activity) attribute of the Function data type.


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-AF](./README.md#ref_TG_DS_AF) 5.3.2.1.1.

**Test type**: Automated

**Notes** 

Verify that the OCL constraints that are specified in the UML model of the application schema are met, i.e. validate features against the constraints. For unmet constraints report [constraintViolation](#constraintViolation).

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
constraintViolation <a name="constraintViolation"/>  |  XML document '$filename', $featureType '$gmlid': The constraint '$constraint' is violated.

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                   |  XPath expression                 |Multiplicity       |Voidable
------------------------------ | --------------------------------- | ------------------|----------
function <a name="function"></a> | //schema-element(af:Holding)/act-core:function | 1..\* | No
activity <a name="activity"></a> | //schema-element(af:Holding)/act-core:function/act-core:Function/act-core:activity/@xlink:href | 1..\* | No