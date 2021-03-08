# Code list values defined by Activity Complex application schema

**Purpose**: Verify whether all attributes, defined by the Activity Complex application schema, whose value type is a code list take the values set out therein

**Prerequisites**

**Test method**

When an attribute has a code list as its type, verify that the values comply with the definitions and include the values set out in Annex II, III and IV of the Implementing Rule. To pass this test verify that any instance of an attribute:

* takes only values explicitly specified in the INSPIRE code list register when the code list‘s extensibility is 'none'.
* takes only a value explicitly specified in the INSPIRE code list register or shall take a value that is narrower (i.e. more specific) than those explicitly specified in the application schema when the code list‘s extensibility is 'narrower'.
* takes values explicitly specified in the INSPIRE code list register when the code list‘s extensibility is 'open' or if a value is not one of the values listed in the code list register check that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule and that all extensions conform to the requirements (This last check is a manual test).



The following checks shall be manually performed for every feature in the dataset, for the 'open' codelists that are externally managed:

* Check that all the [activity](#activity) elements have a [valid value](#validValue1).

* Check that all the [input](#input) and [output](#output) elements have a [valid value](#validValue2).


| <a name="validValue1"></a> Valid values for xlink:href attribute of [activity](#activity) element are only the values defined by the following code list: | 
| ---- | 
| EconomicActivityValue: http://inspire.ec.europa.eu/codelist/EconomicActivityValue |

The allowed values for this code list comprise the values of the following code lists or other code lists specified by data providers:
* EU Economic Activity Classification [EconomicActivityNACEValue](http://inspire.ec.europa.eu/codelist/EconomicActivityNACEValue): Economic activities according to Eurostat NACE Classification values, as specified in Regulation (EC) No 1893/2006 of the European Parliament and of the Council.
* EU Waste Statistics Economic Activity Classification [EconomicActivityWasteStatisticsValue](http://inspire.ec.europa.eu/codelist/EconomicActivityWasteStatisticsValue): Classification of economic activities according to Section 8 of Annex I of Regulation (EC) No 2150/2002.
* EU Waste Recovery Disposal Classification [WasteRecoveryDisposalValue](http://inspire.ec.europa.eu/codelist/WasteRecoveryDisposalValue): Classification of waste recovery and disposal operations according to Annexes I and II of Directive 2008/98/EC of the European Parliament and of the Council.


| <a name="validValue2"></a> Valid values for xlink:href attribute of [input](#input) and [output](#output) elements are only the values defined by the following code list: | 
| ---- | 
| InputOutputValue: http://inspire.ec.europa.eu/codelist/InputOutputValue |

The allowed values for this code list comprise the values of the following code lists or other code lists specified by data providers:
* EU Product Classificatio [ProductCPAValue](http://inspire.ec.europa.eu/codelist/ProductCPAValue): Classification of Products by Economical Activity according to Regulation (EC) No 451/2008 of the European Parliament and of the Council.
* EU Waste Classification [WasteValue](http://inspire.ec.europa.eu/codelist/WasteValue): Classification of Wastes according to Decision 2000/532/EC.



**Reference(s)**: 

* [TG DS Base Models – Activity Complex](./README.md#ref_TG_DS_ACT-CORE) 4.2.3
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (1)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (3)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (1)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (2)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (3)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (4)

**Test type**: Manual

**Notes**


## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
checkManuallyCodeListValue <a name="checkManuallyCodeListValue"/> | XML document '$filename', $featureType '$gmlid': The property '$propertyName' has the following value '$value', please check manually that it is in accordance with the related externally governed codelist.


## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression				|Multiplicity       |Voidable
---------------------------------------------------------- | -------------------------------|-------------------|---------
activity <a name="activity"></a> | //schema-element(af:Holding)/act-core:function/act-core:Function/act-core:activity/@xlink:href | 1..\* | No
input <a name="input"></a> | //schema-element(af:Holding)/act-core:function/act-core:Function/act-core:input/@xlink:href | 0..\* | Yes
output <a name="output"></a> | //schema-element(af:Holding)/act-core:function/act-core:Function/act-core:output/@xlink:href | 0..\* | Yes