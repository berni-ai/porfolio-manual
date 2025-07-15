## 🧹 CLEANUP: Real-World Data Cleaning Framework

> How do you clean data without compromising source integrity?

Use this practical framework to assess, clean, and deliver datasets confidently for reporting, analysis, or modeling.

---

## ✅ CLEANUP Framework

| Step | Description |
|------|-------------|
| **C – Conceptualise** | Understand the data and its features. Ask clarifying questions and confirm how best to interpret business logic. |
| **L – Locate solvable issues** | Scan for solvable issues such as inconsistencies in format, duplicate variations, and invalid categories. |
| **E – Examine** | Identify and investigate anomalies that conflict with business logic, such as broken joins or timestamp irregularities. |
| **A – Augment** | Clean without overwriting original columns—preserve source integrity. Add new columns and track all transformations. |
| **N – Note and document** | Log and evaluate magnitue of issues found and fixes applied. Track unresolved questions and downstream impact. |
| **U – Update stakeholders** | Share findings with relevant parties—align on unresolved logic gaps and validate business assumptions. |
| **P – Prepare next steps** | Check if the cleaning done is sufficient to support meaningful and reliable analysis. |

This method helps protects raw data lineage, encourage critical thinking about business logic and promotes transparency and reproducibility.

---
## 📦 Project Context: The Gamezone Dataset

**Gamezone** is a fictional yet business-relevant company that sells new and refurbished gaming products across multiple platforms.

- 🌍 Global reach since 2018  
- 🕹 Omnichannel presence: website, mobile app, and diverse marketing campaigns  
- 🎯 Dataset includes user journeys, purchases, product metadata, shipping details, and engagement metrics

---

## 🔍TRA = Discovery Steps
1. **Missing Values & Inconsistences**  
- Avoid imputation unless justified—it can introduce bias.
- Check for inconsistent categories (e.g. `"XBOX"` vs `"Xbox"`)
- Identify near-duplicates and format mismatches
- Spot nonsensical entries.
2. **Outliers**  
- Investigate before removing. Outliers might reflect real user behavior or valid edge cases.
3. **Business Logic Violations**  
- Example: Shipping before purchase. Flag and surface these in your insights—they often require stakeholder input.
4. **Nulls Without Source of Truth**  
- Document clearly and exclude from any critical analysis that requires certainty.
5. **Duplicates**  
- Identify and handle all variations of duplicates — exact, fuzzy (near-duplicates) and structural, especially across integrated systems.

---

## 🧠 CE = Validation Steps
1. **Replicate Before You Modify**  
- Always create a copy of the original dataset before applying changes.

2. **Use Suffixes**  
- Label transformed columns with `_cleaned` or similar. Never overwrite raw columns.

3. **Log the Issues**  
- Maintain detailed logs or comments. They reflect analytical rigor and support team visibility.
  
   **📋 Sample Issue Log Format**

   | Table  | Column       | Issue                        | Row Count | Solvable? | Resolution                 |
   |--------|--------------|------------------------------|-----------|-----------|----------------------------|
   | orders | ship_date    | Missing values               | 627       | No        | Flag as incomplete         |
   | orders | purchase_ts  | Ship date before purchase    | 48        | Yes       | Flag for review            |
   | orders | country_code | Inconsistent format          | 2,194     | Yes       | Standardise to ISO format  |

---
## 📌 Rule of Thumb

> If fewer than ~20% of rows are affected by an unsolvable issue. **Document it, flag it, and analyse.**

---

## 💡 Analyst Mindset Tips

Good analysts focus on clarity—not perfection. Here are a few mindset principles that guide scalable, thoughtful work:

- Don’t chase perfection—**chase clarity**
- Prioritise **traceability** and **repeatability**
- Surface **uncertainty** in your insights
- Show your **thought process** through logs and notebooks

---

## 🧠 Final Thoughts

Before jumping into analysis, ask yourself. **What story does this data help me tell?**
Ensure you have conceptualised the data to be able to identify the key metrics and dimensions that support real business questions.

---
