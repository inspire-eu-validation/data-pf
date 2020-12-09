# Constraints

**Purpose**: Verify that the features provided in the dataset adhere to the constraints specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following check is performed for every feature in the dataset.

* Check that the [geometry](#geometry) is provided for the ProductionBuilding feature type if the [building](#building) property is empty. (i.e. Geometry must be provided only in case that not linkage with a building schema entity was stablished).


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-PF](./README.md#ref_TG_DS_PF) 5.3.2.1.1.

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
geometry <a name="geometry"></a> | //schema-element(pf:ProductionBuilding)/pf:geometry <br> //schema-element(pf:ProductionFacility)/pf:groupedBuilding/pf:ProductionBuilding/pf:geometry | 0..1 | Yes
building <a name="building"></a> | //schema-element(pf:ProductionBuilding)/pf:building <br> //schema-element(pf:ProductionFacility)/pf:groupedBuilding/pf:ProductionBuilding/pf:building | 0..\* | Yes