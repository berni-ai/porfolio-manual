## 🚦 Data Got Messy? TRACE It Back to Clarity
A practical 5-step framework to clean complex data.

## 🧱 The CLEAN Framework

| Step | Description |
|------|-------------|
| **T – Tag issues** | Eyeball for obvious issues: missing values, inconsistencies, outliers, and variations of duplicate|
| **R – Review structure** | Understand what each row represents, explore schema, and map columns to business context |
| **A – Amend selectively** | Clean new columns without overwriting the original source—preserve raw data integrity |
| **C – Check for conflicts** | Surface unsolvable issues like nulls, timestamp anomalies, and business logic violations |
| **E – Establish documentation** | Log all identified issues and evaluate their magnitude.|

## 🧼 How Real Data Analysts Clean Data on the Job

Real analysts don’t chase perfection. We aim for clarity, consistency, and insight *good enough to analyze, share, and iterate on.*

---

## 📦 Project Context: The Gamezone Dataset

**Gamezone** is a fictional yet business-relevant company that sells new and refurbished gaming products across multiple platforms.

- 🌍 Global reach since 2018  
- 🕹 Omnichannel presence: website, mobile app, and diverse marketing campaigns  
- 🎯 Dataset includes user journeys, purchases, product metadata, shipping details, and engagement metrics

## 🧪 Overview
Real analysts don’t chase perfection—we aim for clarity, consistency, and insight. Here’s how we clean data before deeper analysis:

1. **Eyeball for Obvious Issues**
   - Look for missing values
   - Identify duplicate variants (exact, fuzzy, structural)
   - Spot nonsensical or out-of-range entries

2. **Inspect Distinct Values**
   - Check for inconsistent categories (e.g. `"XBOX"` vs `"Xbox"`)
   - Identify near-duplicates and format mismatches

3. **Log the Issues**
   - Use a structured issue log to track problems and resolutions
   - Helps surface major issues and prioritise which to fix first

   **📋 Sample Issue Log Format**

   | Table  | Column       | Issue                        | Row Count | Solvable? | Resolution                 |
   |--------|--------------|------------------------------|-----------|-----------|----------------------------|
   | orders | ship_date    | Missing values               | 627       | No        | Flag as incomplete         |
   | orders | purchase_ts  | Ship date before purchase    | 48        | Yes       | Flag for review            |
   | orders | country_code | Inconsistent format          | 2,194     | Yes       | Standardise to ISO format  |

---

## 🧩 Step 1: Handling Specific Issues

1. **Missing Values**  
   Avoid imputation unless justified—it can introduce bias.

2. **Outliers**  
   Investigate before removing. Outliers might reflect real user behavior or valid edge cases.

3. **Business Logic Violations**  
   Example: Shipping before purchase. Flag and surface these in your insights—they often require stakeholder input.

4. **Nulls Without Source of Truth**  
   Document clearly and exclude from any critical analysis that requires certainty.

5. **Duplicates**  
   Identify and handle all variants—exact, fuzzy, structural—especially across integrated systems.

---

## 🧼 Step 2: Cleaning Etiquette

- **Replicate Before You Modify**  
  Always create a copy of the original dataset before applying changes.

- **Use Suffixes**  
  Label transformed columns with `_cleaned` or similar. Never overwrite raw columns.

- **Document Thoughtfully**  
  Maintain detailed logs or comments. They reflect analytical rigor and support team visibility.

---

## 💡 Analyst Mindset Tips

Good analysts focus on clarity—not perfection. Here are a few mindset principles that guide scalable, thoughtful work:

- Don’t chase perfection—**chase clarity**
- Prioritise **traceability** and **repeatability**
- Surface **uncertainty** in your insights
- Show your **thought process** through logs and notebooks

---

## 📌 Rule of Thumb

> If fewer than ~20% of rows are affected by an unsolvable issue:  
> **Document it, flag it, and proceed confidently.**

---

