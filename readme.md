# BIM Tools Material Library Ontology (BTMLO)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

## Authors
- Creator: Bangalu Apollos Yohanna https://dc.rwth-aachen.de/en/apollos-bangalu-2/
- Contributor: Univ.-Prof. Dr.Jakob Beetz Jakob Beetz https://dc.rwth-aachen.de/en/jakob-beetz-2/

## 📝 Description

The BIM Tools Material Library Ontology (BTMLO) is a comprehensive semantic framework developed as part of PhD research to standardize the representation of building materials and products within Building Information Modeling (BIM) tools. This ontology aligns with the Industry Foundation Class (IFC) schema IFC4 ADD2_TC1, enabling semantic interoperability within the BIM domain. It used for research purposes only. Do not use for commercial purposes. It is in beta.

### 🎓 Academic Context
This is a PhD research work by Bangalu Apollos Yohanna, under the supervision of Professor Jakob Beetz. Any use or modification of this ontology must include appropriate academic citations.

## 🌟 Features

- Comprehensive material classification system
- Detailed property framework aligned with IFC4
- Semantic relationships between materials and properties
- Support for complex material compositions
- Standardized property definitions
- Interoperability with BIM tools

## 📋 Prerequisites

- OWL 2 compatible tools
- RDF/XML parser support
- Basic understanding of:
  - Semantic Web technologies
  - BIM concepts
  - IFC standards

## 🛠️ Implementation

### Core Components

#### 1. Material Categories
```turtle
:MaterialCategory rdf:type owl:Class ;
    rdfs:comment "Represents different categories of building materials" ;
    rdfs:label "Material Category" .
```

#### 2. Property Framework
```turtle
:MaterialProperty rdf:type owl:Class ;
    rdfs:subClassOf :Property ;
    rdfs:comment "Represents material properties with values and units" .
```

#### 3. Classification System
```turtle
:ClassificationSystem rdf:type owl:Class ;
    rdfs:subClassOf :ExternalReferenceDatabase .
```

### Key Relationships

- hasMaterialProperty
- hasCategory
- correlatesWith
- influencesProperty

## 📥 Installation

1. Clone the repository:
```bash
git clone https://github.com/apollosbangalu/BimToolsOntology.git
```

2. Import the ontology using your preferred ontology editor (e.g., Protégé):
```
File -> Open -> the ontology file path
```

## 💻 Usage

### Loading the Ontology

```python
from rdflib import Graph
g = Graph()
g.parse("ontology filename", format="turtle")
```

### Querying Material Properties

```sparql
PREFIX btml: <http://www.BimToolsMaterialLibrary.com/BimBuildingMaterialsOntology#>

SELECT ?material ?property ?value
WHERE {
    ?material a btml:BuildingMaterial ;
             btml:hasMaterialProperty ?property .
    ?property btml:hasValue ?value .
}
```

### Adding New Materials

```turtle
:NewMaterial rdf:type :BuildingMaterial ;
    :hasCategory :Concrete ;
    :hasMaterialProperty [
        a :MechanicalProperty ;
        :hasValue "30.0"^^xsd:double ;
        :hasUnit :MPa
    ] .
```

## 🔍 Ontology Structure

### Main Classes
- BuildingMaterial
- MaterialCategory
- MaterialProperty
- MaterialDefinition
- ClassificationSystem

### Property Types
1. **Physical Properties**
   - Density
   - Porosity
   - Thermal conductivity

2. **Mechanical Properties**
   - Strength
   - Elasticity
   - Poisson's ratio

3. **Behavioral Properties**
   - Fire resistance
   - Weathering characteristics
   - Durability parameters

## 🤝 Integration with BIM Tools

### IFC Alignment
The ontology maintains alignment with IFC4 ADD2_TC1 for:
- Material definitions
- Property sets
- Classification references

### Data Exchange
Supports:
- IFC import/export
- Property mapping
- Classification system integration

## 🔬 Research Context

This ontology is part of ongoing PhD research focusing on semantic interoperability in BIM. When using this work, please:
1. Cite appropriately
2. Maintain academic integrity
3. Document modifications
4. Share improvements

## 📖 Citation

```bibtex
@phdthesis{yohanna2024btmlo,
    author = {Yohanna, Bangalu Apollos},
    title = {BIM Tools Material Library Ontology: A Semantic Framework for Building Material Representation},
    school = {RWTH Aachen},
    year = {2024},
    note = {Under supervision of Univ.-Prof. Dr.Jakob Beetz Jakob Beetz}
}
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request
6. Ensure academic contribution acknowledgment

## 📝 License

This work is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).

## ✉️ Contact

- **PhD Researcher:** Bangalu Apollos Yohanna https://dc.rwth-aachen.de/en/apollos-bangalu-2/
- **Supervisor:** Univ.-Prof. Dr.Jakob Beetz Jakob Beetz https://dc.rwth-aachen.de/en/jakob-beetz-2/

## 🔄 Version History

- 0.1: Initial release with core framework
- Future releases planned for extended functionality

## 🙏 Acknowledgments

- Research Supervisor: Professor Jakob Beetz
- Partners and Contributors
- The authors would like to thank Silvio Peroni for developing LODE, a Live OWL Documentation Environment, which is used for representing the Cross Referencing Section of this document and Daniel Garijo for developing Widoco, the program used to create the template used in this documentation.

## ⚠️ Important Notes

1. This is an academic research project
2. Modifications must be documented
3. Academic citation is required
4. Commercial use must comply with CC BY 4.0
