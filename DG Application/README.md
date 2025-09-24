# Privacy and Anonymization in Healthcare AI Chatbots

## 🏥 Project Overview

This repository contains an academic project that addresses the critical challenge of **privacy and anonymization** in AI-powered healthcare applications. The project is based on a scenario where a healthcare provider plans to deploy an AI chatbot, raising concerns about handling sensitive patient data, complying with privacy laws, and preventing re-identification.

The analysis provides a comprehensive framework for identifying privacy risks, ensuring compliance with **GDPR**, and implementing robust anonymization techniques. A practical demonstration is provided using the "Medical Student Mental Health" dataset to showcase the application of these techniques in a real-world context.

---

## 🔑 Key Concepts & Techniques

This project explores essential concepts in data privacy and demonstrates their practical application.

### 1. Privacy Risks
The primary risk addressed is the **re-identification** of individuals by combining **Quasi-Identifiers (QIs)**—attributes that are not unique on their own but can single out an individual when combined. For the dataset used, the identified QIs are:
* Age Group 
* Curriculum Year
* Sex 
* Mother Tongue

### 2. Legal & Ethical Compliance
The analysis is grounded in the principles of the **General Data Protection Regulation (GDPR)**. A key focus is the legal distinction between:
* **Anonymous Data**: Data that can no longer be linked to an individual and falls outside the scope of GDPR.
* **Pseudonymized Data**: Data where identifiers are replaced (e.g., via tokenization), but re-identification is still possible. This data remains personal data under GDPR.

### 3. Anonymization Techniques Implemented
The following techniques were applied to the dataset to protect privacy:

* **Tokenization**: The original `id` column was replaced with a randomly generated, non-identifying token, breaking the direct link to the original person while allowing for internal data linkage.
* **Generalization**: Quasi-identifiers like `age` and `glang` (mother tongue) were grouped into broader, less specific categories (e.g., `17-20` age group) to make individuals less distinct.
* **Suppression**: Records belonging to small, high-risk groups that did not meet privacy thresholds were suppressed (set to `NaN`) to prevent singling out individuals.
* **k-Anonymity & l-Diversity**: These principles were used as thresholds to ensure data privacy.
    * **k-Anonymity** guarantees that each record is indistinguishable from at least `k-1` other records based on its QIs.
    * **l-Diversity** ensures that for each group of records with identical QIs, there are at least `l` different values for sensitive attributes (like `health` status).

---

## 📊 Dataset & Implementation

The project uses the **Medical Student Mental Health dataset**  to demonstrate a practical anonymization workflow. The implementation successfully applies tokenization, generalization, and suppression to meet pre-defined `k` and `l` values, thereby reducing the risk of re-identification.

The presentation also discusses advanced techniques, such as the use of **Large Language Models (LLMs)** like Llama-3, which have shown a 99.24% success rate in automatically removing Protected Health Information (PHI) from clinical texts.

## 🎯 Conclusion & Recommendations

The analysis concludes that a careful balance must be struck between **privacy protection and data utility**. While anonymization is essential for GDPR compliance, overly aggressive techniques can degrade data quality and render it unusable for research.

**Key Recommendations:**
1.  **Use Layered Protections**: Combine technical anonymization with strong organizational safeguards like access controls, encryption, and consent management.
2.  **Continuously Monitor**: Regularly assess how anonymization impacts analytical accuracy to ensure the data remains valuable for its intended purpose.

---

## 🚀 How to Use This Repository

This repository serves as an educational resource for anyone interested in data privacy, ethical AI, and healthcare data governance. It is particularly useful for:
* **Students** learning about privacy-enhancing technologies (PETs).
* **Researchers** who need to anonymize sensitive datasets.
* **Professionals** developing AI systems that handle personal data.

Feel free to explore the presentation, read the analysis report, and examine the code to understand the theory and practice of data anonymization.
