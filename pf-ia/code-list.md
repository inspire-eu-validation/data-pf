# Code lists

**Purpose**: Verify that code lists extensions can be accessed.

**Prerequisites**

**Test method**

* Verify that any code list extensions are publicly accessible via HTTP, i.e. inspect extensible code list values property elements. If a reference (@xlink:href) has a value that does not start with http://inspire.ec.europa.eu/codelist/, verify that a HTTP GET request to the URI retrieves a document. Otherwise report [brokenLink](#brokenLink).

This data theme currently has the following empty code lists:

* [InstallationTypeValue](#InstallationTypeValue): http://inspire.ec.europa.eu/codelist/InstallationTypeValue
* [InstallationPartTypeValue](#InstallationPartTypeValue): http://inspire.ec.europa.eu/codelist/InstallationPartTypeValue
* [RiverBasinDistrictValue](#RiverBasinDistrictValue): http://inspire.ec.europa.eu/codelist/RiverBasinDistrictValue
* [TypeOfProductionBuildingValue](#TypeOfProductionBuildingValue): http://inspire.ec.europa.eu/codelist/TypeOfProductionBuildingValue


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (3)

**Test type**: Automated

**Notes**

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
brokenLink <a name="brokenLink"/>  |  XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that cannot be retrieved using HTTP. Every code list value must be made available in an online registry. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression      |Multiplicity   |Voidable
---------------------------------------------------------- | -----------------------|---------------|---------------------------------
InstallationTypeValue <a name ="InstallationTypeValue"></a> | //schema-element(pf:ProductionInstallation)/pf:type/@xlink:href <br> //schema-element(pf:ProductionFacility)/pf:groupedInstallation/pf:ProductionInstallation/pf:type/@xlink:href  | 1 | Yes
InstallationPartTypeValue <a name="InstallationPartTypeValue"></a> | //schema-element(pf:ProductionInstallationPart)/pf:type/@xlink:href <br> //schema-element(pf:ProductionInstallation)/pf:groupedInstallationPart/pf:ProductionInstallationPart/pf:type/@xlink:href <br> //schema-element(pf:ProductionFacility)/pf:groupedInstallation/pf:ProductionInstallation/pf:groupedInstallationPart/pf:ProductionInstallationPart/pf:type/@xlink:href | 1 | Yes
RiverBasinDistrictValue <a name ="RiverBasinDistrictValue"></a> | //schema-element(pf:ProductionFacility)/pf:riverBasinDistrict/@xlink:href  | 0..1 | No
TypeOfProductionBuildingValue <a name="TypeOfProductionBuildingValue"></a> | //schema-element(pf:ProductionBuilding)/pf:typeOfBuilding <br> //schema-element(pf:ProductionFacility)/pf:groupedBuilding/pf:ProductionBuilding/pf:typeOfBuilding | 0..\* | Yes