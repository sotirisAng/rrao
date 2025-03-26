# **RRAO**

RRAO: An Ontology for the Representation of Knowledge for Reoffending Risk Assessment

## **Overview**

The **Reoffending Risk Assessment Ontology (RRAO)** is a formal and reusable ontology designed to model knowledge related to **reoffending risk and recidivism**. Developed as part of the **FAIR-PReSONS project**, RRAO enables unbiased representation of data concerning criminal offenses, penalties, judicial decisions, and socio-demographic factors influencing reoffending.

This ontology supports **semantic integration** of heterogeneous legal and correctional datasets.

---

## **Ontology Documentation**

For a full ontology documentation, see [https://w3id.org/rrao](https://w3id.org/rrao).

---

## **Key Features**
![RRAO 1.1 classes.drawio.png](images/RRAO%201.1%20classes.drawio.png)
 
- Alignment with international standard **International Classification of Crime for Statistical Purposes ([ICCS](https://www.unodc.org/unodc/en/data-and-analysis/statistics/iccs.html))**.
- Extending [ODRL](https://www.w3.org/ns/odrl/2/) and linking to [EuroVoc](https://eur-lex.europa.eu/browse/eurovoc.html)

---

## **LLM Assisted Development**
LLMs were utilized for scaffolding a kick-off ontology and leveraged in the step for bias assessment. LLM models (Gemini, Claude 3.5 and GPT4-ο) were prompt with the zero-shot method. Examples of the prompts and responses can be found on the **[LLM experiments](LLM%20experiments)** directory.

## **SPARQL Query Example**
What are the demographic and socio-economic characteristics of an imprisoned person?
```sparql
PREFIX rrao: <http://w3id.org/rrao#>
SELECT DISTINCT ?age ?sex ?educationLevel
?reportedOccupation ?occupationCategory ?maritalStatus
WHERE {
    ?person a rrao:imprisoned .
    ?person rrao:generalRegisterNumber "123" ;
    rrao:ageGroup ?age ;
    rrao:sex ?sex ;
    rrao:levelOfEducation ?educationLevel ;
    rrao:reportedOccupation ?reportedOccupation ;
    rrao:reportedOccupationCategory ?occupationCategory;
    rrao:maritalStatus ?maritalStatus .
}
```

SPARQL examples can be found in the [queries](queries) directory.

---

## **Ontology Versions**
**Latest version**: [v1.1](rrao_v1.1.owl)

**Updates on latest version:**

* The 'Detention Record' class was introduced to enable reification, allowing for more precise representation of detention events. This is particularly useful for cases where a person has been detained in multiple correctional facilities due to different convictions. By linking penalties to specific detention records and correctional institutions, the new class ensures a more structured and accurate representation of an individual's custodial history. 

* The 'Sentenced' class was renamed to 'Person with Custodial History' to reduce stereotyping.

* New properties such as ageEnteringPrison, ageExitingPrison, resultsFromMultipleCrimes, siblings, vocationalQualifications, and dateOfRiskAssessment were added to the ontology.

* Tranlsations of terms were added in Greek, Bulgarian and Portuguese.

Previous versions can be found in the [versions](versions) directory.

## **License**
This ontology is released under the **Creative Commons 0  (CC0)** license.

---

## **Contact & Support** 
📧 **Email**: [sotiris@aegean.gr](mailto:sotiris@aegean.gr)

📌 **Project Page**: [https://fair-presons.aegean.gr/](https://fair-presons.aegean.gr/)

