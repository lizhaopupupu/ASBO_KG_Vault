# Predictive models for intestinal obstruction: from clinical scores to artificial intelligence.

> PMC 开放获取全文（PMC13416215），对应文献笔记：[[42528989_Predictive models for intestinal obstruction from clinical]]

## Background and objective

Intestinal obstruction is a common surgical emergency in which delayed recognition of strangulation, ischemia, or failure of non-operative management can lead to bowel necrosis, sepsis, and death. Prediction models have been developed for several related but distinct tasks, including diagnosis of obstruction, prediction of urgent surgery, prediction of strangulation or irreversible ischemia, and prediction of failure of conservative treatment. This review critically summarizes these models and clarifies their clinical scope, validation status, and translational limitations.

## Methods

PubMed was searched for studies published from database inception to October 31, 2025, with the initial search performed during manuscript preparation on December 1, 2025 and the final update search conducted on June 18, 2026. Search terms were related to intestinal obstruction, small bowel obstruction, prediction model, nomogram, scoring system, artificial intelligence, machine learning, deep learning, and computed tomography. Eligible articles reported or discussed predictive, diagnostic, or decision-support models for intestinal obstruction. We excluded papers without model-related content, non-clinical mechanistic studies unless used to explain modeling rationale, case reports, and articles not providing sufficient methodological or performance information. Because the evidence was heterogeneous in population, endpoint, modality, and design, the review was synthesized narratively rather than meta-analyzed.

## Key findings

Conventional clinical scores remain attractive because they are transparent, inexpensive, and quickly calculable, but their performance varies across endpoints and settings. CT-integrated models improve anatomical and ischemic risk assessment but depend on imaging availability and reader expertise. Machine-learning and deep-learning models, including multimodal systems combining electronic health records and imaging, have reported high discrimination in selected datasets; however, many studies remain retrospective, single-center, and incompletely externally validated. Therefore, AUC values across studies should not be interpreted as directly comparable evidence of superiority.

## Conclusions

The field is moving from static, single-modality scores toward dynamic, multimodal decision-support systems. The most immediate research priorities are prospective multicenter validation, standardized endpoint definitions, calibration and decision-curve reporting, explainability, fairness assessment, privacy-preserving data sharing, and workflow integration in emergency surgical care.

## Introduction

Intestinal obstruction is a frequent cause of acute abdomen and emergency surgical consultation. The clinical challenge is not only to diagnose obstruction, but also to identify patients who require urgent intervention because of strangulation, irreversible ischemia, bowel necrosis, or likely failure of conservative treatment (1–6). Delayed surgery may increase morbidity and mortality, whereas unnecessary surgery exposes patients to avoidable complications. Risk stratification tools are therefore clinically important.

Prediction models for intestinal obstruction have expanded rapidly. Early models used readily available bedside variables, such as age, abdominal signs, ascites, and gastrointestinal decompression volume (7). Later models incorporated CT features and laboratory variables to improve the recognition of strangulation and ischemia (8–14). More recently, machine-learning and deep-learning approaches have been applied to abdominal radiographs, CT images, and electronic health-record data (15–21).

The novelty of this review is threefold. First, it separates prediction models according to clinical task, because models predicting surgery, strangulation, ischemia, non-operative treatment failure, or radiographic obstruction answer different clinical questions. Second, it proposes a three-generation conceptual framework that distinguishes bedside clinical scores, CT-integrated multidimensional models, and AI-enabled multimodal systems. Third, it evaluates reported performance in light of methodological heterogeneity, external validation, clinical workflow feasibility, explainability, and generalizability rather than ranking models by AUC alone.

This review is intended for emergency surgeons, gastrointestinal surgeons, radiologists, emergency physicians, and clinical AI researchers who need a practical and critical overview of prediction tools for intestinal obstruction.

## Focused review questions

Which predictive models have been developed for intestinal obstruction and what clinical endpoints do they target?

How have model inputs evolved from clinical variables to CT imaging and multimodal AI?

How should performance be interpreted given heterogeneity in population, endpoint, validation, and study design?

What methodological and translational steps are required before AI-based models can be used safely in routine emergency surgical workflows?

## Review methodology

## Search strategy and reporting framework

This review was designed as a narrative review with a semi-systematic PubMed-based search strategy. The report was revised with reference to the SANRA principles for narrative reviews and, where applicable, PRISMA concepts for transparent search reporting. PubMed was used as the primary bibliographic database. In addition, the reference lists of eligible articles and relevant reviews were manually screened to identify additional studies. The PRISMA-style flow diagram was used only to improve search transparency rather than to claim full compliance with PRISMA systematic-review methodology.

The initial literature search was performed during manuscript preparation on December 1, 2025, and an updated final PubMed search was conducted on June 18, 2026. To maintain a predefined and reproducible evidence window, eligible records were restricted to studies published from database inception to October 31, 2025. Reference lists of eligible articles and relevant reviews were also manually screened, and any additional studies were included only if they met the same eligibility criteria and publication cutoff. Recent methodological or background references outside this evidence window, if cited, were used only for contextual discussion and were not counted among the included prediction-model studies.

The following PubMed search string was used: (“intestinal obstruction”[Title/Abstract] OR “bowel obstruction”[Title/Abstract] OR “small bowel obstruction”[Title/Abstract] OR “adhesive small bowel obstruction”[Title/Abstract]) AND (“prediction model”[Title/Abstract] OR “predictive model”[Title/Abstract] OR “risk score”[Title/Abstract] OR “scoring system”[Title/Abstract] OR nomogram[Title/Abstract] OR “decision support”[Title/Abstract] OR diagnosis[Title/Abstract] OR prediction[Title/Abstract]) AND (“computed tomography”[Title/Abstract] OR CT[Title/Abstract] OR radiomics[Title/Abstract] OR “artificial intelligence”[Title/Abstract] OR “machine learning”[Title/Abstract] OR “deep learning”[Title/Abstract] OR CNN[Title/Abstract] OR “electronic health record”[Title/Abstract] OR EHR[Title/Abstract]).The PubMed search identified 2,537 records. No duplicate records were removed because only one bibliographic database was used. After title and abstract screening, 2,247 records were excluded because they were not relevant to intestinal obstruction, did not contain prediction-model, diagnostic-model, scoring-system, nomogram, CT-based, radiomics, machine-learning, or deep-learning content, or were case reports, technique-only papers, animal studies, or non-clinical studies. A total of 290 reports were sought for retrieval, of which 8 could not be retrieved. Therefore, 282 full-text reports were assessed for eligibility.

(“intestinal obstruction”[Title/Abstract] OR “bowel obstruction”[Title/Abstract] OR “small bowel obstruction”[Title/Abstract] OR “adhesive small bowel obstruction”[Title/Abstract]) AND (“prediction model”[Title/Abstract] OR “predictive model”[Title/Abstract] OR “risk score”[Title/Abstract] OR “scoring system”[Title/Abstract] OR nomogram[Title/Abstract] OR “decision support”[Title/Abstract] OR diagnosis[Title/Abstract] OR prediction[Title/Abstract]) AND (“computed tomography”[Title/Abstract] OR CT[Title/Abstract] OR radiomics[Title/Abstract] OR “artificial intelligence”[Title/Abstract] OR “machine learning”[Title/Abstract] OR “deep learning”[Title/Abstract] OR CNN[Title/Abstract] OR “electronic health record”[Title/Abstract] OR EHR[Title/Abstract]).

During full-text assessment, 172 reports were excluded for the following reasons: not related to intestinal obstruction, no prediction/model-related content, case report or technique-only article, animal or non-clinical study, insufficient methodological or performance information, or duplicate publication/overlapping data. Finally, 110 studies were included in the narrative synthesis. The study-selection process is shown in Figure 1.

PRISMA-style search-transparency flow diagram for the PubMed-based semi-systematic literature search and study selection. *PubMed was used as the primary bibliographic database. **Records were excluded after title and abstract screening because they were not relevant to intestinal obstruction, did not contain prediction-model, diagnostic-model, scoring-system, nomogram, CT-based, radiomics, machine-learning, or deep-learning content, or were case reports, technique-only papers, animal studies, or non-clinical studies.

## Eligibility criteria

Studies were eligible if they involved adult or mixed clinical populations with intestinal obstruction, especially small bowel obstruction or adhesive small bowel obstruction, and reported or discussed clinical scores, nomograms, CT-based models, radiomics, machine-learning, deep-learning, or multimodal prediction systems. Eligible outcomes included diagnosis of obstruction, need for urgent surgery, strangulation, bowel ischemia or necrosis, bowel resection, and failure of conservative management. We excluded case reports, technique-only articles, purely animal or cellular studies unless used only to explain pathophysiological rationale, duplicate or overlapping publications, and studies without sufficient methodological or performance information. The detailed inclusion and exclusion criteria are summarized in Table 1.

Eligibility criteria for study selection.

## Study selection, data extraction, and synthesis

Two reviewers independently screened titles and abstracts. Potentially eligible full texts were then assessed independently by the same reviewers. Disagreements were resolved through discussion, and when consensus could not be reached, a senior author adjudicated. Data extraction was performed using a predefined form and checked by a second reviewer.

For predictive-model studies, extracted information included population, study design, sample size, target outcome, input modality, modeling method, validation strategy, discrimination, calibration, and clinical-utility assessment. Because studies differed substantially in endpoint definition, case mix, imaging availability, and validation design, quantitative pooling was not performed. Instead, evidence was grouped by clinical task and model generation, with emphasis on methodological comparability and clinical applicability.

For representative original prediction-model studies, a simplified PROBAST-based assessment was performed to evaluate risk of bias and applicability (22). The assessment focused on the four PROBAST domains: participants, predictors, outcome, and analysis. Each domain was judged as low, high, or unclear risk of bias according to the information reported in the original articles. Applicability concerns were considered in relation to the target population, predictors, and clinical outcomes addressed in this review. Because this article was designed

……（全文较长，此处截取前 12000 字符）