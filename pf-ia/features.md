# Feature references

**Purpose**: Verify that referenced features can be retrieved.

**Prerequisites**

**Test method**

* Verify that any feature reference in an association role is publicly accessible via HTTP, i.e. inspect all relevant properties. If a reference (@xlink:href) has a value that starts with "#", verify that an element with a `gml:id` attribute with the referenced identifier exists in the same document. If the reference starts with "http", verify that a HTTP GET request to the URI retrieves an XML document. Otherwise report [brokenLink](#brokenLink).

This data theme currently has the following association role:

* [ProductionFacility.groupedBuilding](#groupedBuilding): ProductionBuilding
* [ProductionFacility.groupedPlot](#groupedPlot): ProductionPlot 
* [ProductionFacility.hostingSite](#hostingSite): ProductionSite 
* [ProductionFacility.groupedInstallation](#groupedInstallation): ProductionInstallation
* [ProductionInstallation.groupedInstallationPart](#groupedInstallationPart): ProductionInstallationPart
* [ProductionBuilding.building](#building): AbstractBuilding


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)

**Test type**: Automated

**Notes**

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
brokenLink <a name="brokenLink"/>  |  XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that cannot be retrieved using HTTP. Every code list value must be made available in an online registry. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                         |  XPath expression    | Multiplicity    | Voidable
------------------------------------ | ---------------------|-----------------|------------
ProductionFacility.groupedBuilding <a name ="groupedBuilding"></a>	| //schema-element(pf:ProductionFacility)/pf:groupedBuilding/@xlink:href | 0..\* | Yes
ProductionFacility.groupedPlot <a name ="groupedPlot"></a>	| //schema-element(pf:ProductionFacility)/pf:groupedPlot/@xlink:href | 0..\* | Yes
ProductionFacility.hostingSite <a name ="hostingSite"></a>	| //schema-element(pf:ProductionFacility)/pf:hostingSite/@xlink:href | 0..1 | Yes
ProductionFacility.groupedInstallation <a name ="groupedInstallation"></a>	| //schema-element(pf:ProductionFacility)/pf:groupedInstallation/@xlink:href | 0..\* | Yes
ProductionInstallation.groupedInstallationPart <a name ="groupedInstallationPart"></a>	| //schema-element(pf:ProductionInstallation)/pf:groupedInstallationPart/@xlink:href <br> //schema-element(pf:ProductionFacility)/pf:groupedInstallation/pf:ProductionInstallation/pf:groupedInstallationPart/@xlink:href | 0..\* | Yes
ProductionBuilding.building <a name="building"></a> | //schema-element(pf:ProductionBuilding)/pf:building <br> //schema-element(pf:ProductionFacility)/pf:groupedBuilding/pf:ProductionBuilding/pf:building | 0..\* | Yes