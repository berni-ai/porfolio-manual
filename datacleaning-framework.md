## 🧹 CLEANUP Framework

| Step | Description |
|------|-------------|
| **C – Context** | Understanding the data and features. What does each row represent? Clarify schema, field relationships, and stakeholder expectations before jumping into cleaning. |
| **L – Locate Solvable Issues** | Eyeball for fixable problems like missing values, duplicate variations, inconsistent formats, and statistical outliers. |
| **E – Examine** | Identify anomalies that conflict with business logic: nulls in required fields, time zone drifts, broken joins, and timestamp irregularities. |
| **A – Augment** | Clean or enrich without overwriting original columns—preserve source integrity. Add new columns and track transformations. |
| **N – Note and Document** | Log all issues found and fixes applied. Track assumptions, unresolved questions, and potential impacts downstream. |
| **U – Update Stakeholders** | Summarize findings and share with relevant stakeholders—align on unresolved gaps and get clarity on business logic when needed. |
| **P – Prepare Next Steps** | Final checks on structure, completeness, and readiness. Validate that the dataset supports reporting or modeling goals. |

---

## 💡 Why CLEANUP?

- ✅ Preserves original data lineage
- ✅ Encourages critical thinking about business logic
- ✅ Promotes scalable, reproducible data workflows

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
