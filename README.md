# Data Modelling Project

<div align="center">

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Modeling](https://img.shields.io/badge/Data_Modeling-Star_Schema-blue?style=for-the-badge&logo=databricks&logoColor=white)
![ETL](https://img.shields.io/badge/ETL-Power_Query-orange?style=for-the-badge)
![DAX](https://img.shields.io/badge/DAX-Optimized-brightgreen?style=for-the-badge)

</div>

---

This project takes 20+ highly fragmented, unstandardized Excel and CSV source tables and engineers them into a clean, high-performance Star/Galaxy Schema within Power BI. The goal of this project was to 

establish a robust, single-source-of-truth semantic model designed for fast querying and enterprise-level scalability.

📌 The Challenge: Messy, Siloed Sheets (Almost a nightmare dataset at begining)

The Source: 20+ flat, disconnected tables format (.xlsx and .csv).

<img width="1277" height="752" alt="image" src="https://github.com/user-attachments/assets/b6f3573d-3e85-4418-b84c-ece373afc471" />


This data model suffers from several critical architectural flaws that severely limit its analytical usability, performance, and overall data integrity. First, it contains multiple completely disconnected 
"island" tables, leaving vital operational, reference, and target data entirely unlinked from the core schema, which makes holistic reporting impossible. Crucially, the model relies on highly problematic many-to-
many relationships between major dimension and fact tables, introducing a severe risk of double-counting, incorrect metric aggregations, and ambiguous filtering paths. This structural instability is further 
compounded by risky bidirectional cross-filtering across core transactional entities, which complicates calculations and degrades query speed. Finally, key master dimensions are heavily fragmented and scattered 
across multiple over-normalized tables, creating unnecessary complexity and performance overhead instead of consolidating attributes into clean, high-performance lookup dimensions.
So, overall this data model makes no sense for reporting as it is imported direct from the excel files or csv without transforming and modelling it correctly.


Core Issues:

1. Highly fragmented and scattered tables of a single entity (of facts and dimensions).

2. Highly redundant data across sheets.

3. Presence purposeless tables in the model.

4. Unnecessary "many-to-many" and bidirectional relationships which make no sense.
   

🛠️ The Solution: Data Architecture Strategy

🗺️ First i created a project plan, the steps i shall take during the whole project is divided among the four phases:

1. Prepare and Explore: Start with exploring the tables, preparing workspace, Understanding the business and data, Spot dimensions and facts.

2. Dimensions : Building dimensions, group tables for one entity, clean them to the standards, and repeating it for all dimensions.
 
3. Facts : Build facts by picking up an event, read its grains, build the fact from the detail, connect each dimension, and test it so the numbers never break

4. Polish : and in the last phase i recheck the standards, build the date dimension, build some important measures, implement security, and validate the model.

📜 Rule for every phase:

Created some strict rules that i should follow at every phase while creating the model

1. Build a Star Schema, fact table in the middle and never connect fact with facts.

2. Always understand the grains before making any changes, like merging and appending so the data donot loose it creditbility.

3. Every columns should earn its place, which means i should keep only the columns that are useful for reporting and remove useless columns taking space meaninglessly.

4. Protect the numbers, know your totals and recheck after every stage.

5. Follow standards that are defined for the project.

🛡️ Standards for the Project

1. Language : English

2. Naming Convention for tables and columns : snake_case

3. Prefixes : fact_for fact tables, dim_for dimension tables

4. Suffixes : For Keys : Surrogate keys - _key
                         Keys from the source - _id

5. Friendly names: Name columns and table humans friendly not cyptic codes, or shortcut, technical name.


## 🏁 Conclusion & Business Impact

By systematically executing the 4-phase architecture strategy and enforcing strict structural rules and standardization, this project successfully transformed a highly fragmented, 20+ tables spreadsheet mess into a high-performance, enterprise-grade semantic model, containing facts, dimensions, factless fact, shared dimensions, flaged dimension, and extracted dimensions, collectively forming a "Galaxy Schema".

<img width="1917" height="831" alt="image" src="https://github.com/user-attachments/assets/894ba040-1a7e-4020-b974-a793e00fd67e" />


### Key Achievements:
* **True Single Source of Truth:** Eliminated data silos by consolidating scattered sheets into a flawless Star/Galaxy Schema, ensuring seamless, cross-functional reporting across all business units.
* **Guaranteed Data Integrity:** By respecting table grains and strictly managing cardinality (eliminating many-to-many traps and ambiguous bidirectional filters), the model's calculations are 100% accurate and mathematically reliable.
* **Enhanced Model Usability:** Applying standardized `snake_case` naming conventions, descriptive prefixes (`fact_`/`dim_`), and clear key suffixes (`_key`/`_id`) ensures that any analyst or stakeholder can immediately navigate the model and build reports without confusion.
* **Optimized Performance:** Purging unnecessary columns ("making every column earn its place") and structuring optimal query paths dramatically reduced the memory footprint, ensuring lightning-fast DAX calculation speeds.

**The Ultimate Takeaway:** This project proves that great analytics do not start with visuals—they start with a rock-solid data foundation. The resulting semantic model is highly scalable, incredibly fast, and fully prepared to power executive-level dashboards and drive data-driven business decisions.

