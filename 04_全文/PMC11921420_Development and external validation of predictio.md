# Development and external validation of prediction risk scores (STRISK and NOFA) to predict immediate surgical need in adhesive small bowel obstruction: an observational prospective multicentre study.

> PMC 开放获取全文（PMC11921420），对应文献笔记：[[40105480_Development and external validation of prediction risk sco]]

## Abstract

## Background

Adhesive small bowel obstruction (SBO) is a common cause of emergency admission. Identification of patients at high risk of strangulation or failure of non-operative treatment is difficult. In this multicentre prospective observational study, prediction models for strangulation and non-operative treatment failure in adhesive SBO were developed.

## Method

This study was carried out in three Finnish hospitals between June 2014 to May 2022. Patients with CT-confirmed adhesive SBO and prospective case report forms were included. The main outcomes were strangulation defined by operative finding of any intestinal ischaemia and failure of non-operative treatment within 30 days from admission. The model was developed using binary logistic regression, internally validated by bootstrapping and then externally validated.

## Results

Of 626 patients, 481 were included; 355 patients formed the model development group and 126 formed the external validation group. Strangulation occurred in 58 (16%) patients and non-operative treatment failed in 93 (31%) patients in development cohort. The following six variables were included in the risk model for strangulation and non-operative treatment failure: neutrophil–leucocyte ratio, number of previous SBOs, abdominal guarding, mesenteric changes and free abdominal fluid, closed loop sign, and faeces sign on CT. In the development cohort, the optimism corrected area under the receiver operator characteristics curve for the strangulation model was 0.860 (95% c.i. 0.808–0.917), and 0.751 (95% c.i. 0.694–0.816) for the non-operative treatment failure model respectively. At external validation, the models retained their discrimination and demonstrated stable calibration.

## Conclusion

A clinically relevant prediction model to predict strangulation and non-operative treatment failure in adhesive small bowel obstruction has been developed.

Small bowel obstruction is a leading cause of emergency surgery admission. Detecting patients at high risk of strangulation or failure of non-operative treatment is difficult. In this multicentre prospective observational study, we created prediction models for detection of strangulation and non-operative treatment failure in adhesive small bowel obstruction.

## Introduction

Small bowel obstruction (SBO) is a leading cause of emergency surgical admission1–4. Up to 60% of SBOs are due to peritoneal post-operative adhesions5. According to current Bologna guidelines, in the absence of concern about intestinal ischaemia (strangulation), adhesive SBO can be treated non-operatively with intravenous fluid administration, nasogastric (NG) tube insertion and oral water-soluble contrast (WSC) prescription2. If strangulation is suspected, immediate surgery is necessary2. However, detecting patients at high risk of strangulation or failure of non-operative treatment is difficult6,7. A recent national study (NASBO) from the UK concluded that timing of surgery could be one of the key modifiable factors to improve outcomes3. Several prediction models combining CT-scan findings, laboratory results, or clinical features to detect either strangulation or non-operative management failure have been generated8–13. However, they have usually had methodological issues that include small sample size, retrospective study design, and lack of calibration or external validation. At present, no prediction model appears to be widely used.

The overall mortality rate after laparotomy for adhesive SBO exceeds 7% and delay to emergency laparotomy more than 72 h after admission is associated with a higher 30-day postoperative mortality rate4 and longer hospital stay14. When non-operative management fails, the costs increase over seven-fold15. Well-performing prediction models that predict strangulation and non-operative treatment failure could help facilitate an earlier decision to operate and ultimately lead to better short- and long-term outcomes.

In this multicentre prospective observational study, two externally validated prediction models were developed: one for strangulation and the other for failure of non-operative management in adhesive SBO.

## Methods

The study was an observational prospective multicentre trial conducted in three hospitals in southern Finland: two university hospitals (Meilahti and Jorvi Hospitals, both part of Helsinki University Hospital) and one community hospital (Hyvinkää Hospital). The prediction models were developed using Meilahti hospital patient data and externally validated using Jorvi and Hyvinkää hospitals’ patient data. The study recruitment period was from 2 June 2014 to 31 March 2023 in Meilahti hospital and from 28 January 2018 to 31 March 2023 in Jorvi and Hyvinkää hospitals. The TRIPOD statement16 was applied for reporting this study and the checklist was completed (Supplemental material). Guidance regarding the development and validation of predictions models was also used17–19. The study has been registered in ClinicalTrials.gov (NCT03461744).

## Participants

Patients presenting to the surgical emergency department with CT-confirmed adhesive SBO with clinically relevant blood samples taken were included in the study. Patients under 18 years of age, pregnant patients, patients who had undergone abdominal surgery within 30 days, patients with inflammatory bowel disease, and patients with SBO caused by intraluminal obstruction, abdominal wall hernia, or peritoneal carcinomatosis were excluded. After inclusion to the trial no other trial interventions were performed and the patients were treated according to normal hospital protocols: if strangulation was suspected by the treating surgeon, emergency surgery was initiated. Otherwise, non-operative treatment was initiated. The non-operative treatment plan included intravenous hydration and NG-tube insertion, usually followed by WSC challenge after decompression. Any signs of strangulation during non-operative treatment were an indication for surgery. Urgent surgery was initiated if the SBO did not resolve, usually after WSC challenge. No informed consent was needed as this was an observational trial with no impact on patient care. The study protocol was approved by the Ethics Committee of Helsinki University Hospital on 26 March 2014, and by the Institutional Review Board of the Hospital District of Helsinki and Uusimaa. Patients were followed up from the medical records for 30 days from admission.

## Outcome

Primary outcomes for this study were strangulation defined by operative finding of any intestinal ischaemia (bowel necrosis or reversible ischaemia) and failure of non-operative treatment (need for surgery after initiation of non-operative management) within 30 days from admission.

## Predictors

The treating (on-call) physicians collected information about the patient history and symptoms, such as pain quality and severity, on a prospective case report form.

The following laboratory measurements were collected routinely from included patients: haemoglobin, leucocytes (white blood cell count), neutrophils, alanine aminotransferase, bilirubin, venous pH, venous base excess, lactate, creatinine kinase, fibrine D-dimer (FiDD), and sodium (Na).

The basic demographics of the patients including other diseases and medical conditions determined by the Elixhauser Co-morbidity index20 and previous abdominal operations were collected from medical records.

The CT scan images were re-analysed by two expert gastrointestinal radiologists (E.L. and H.P., radiology case report form presented in Supplemental material). The radiologists were not informed about the surgical findings.

In patients initiated on a non-operative treatment plan, the NG tube output in first 12 h was analysed using the nearest 12-hour mark value. Operative findings were analysed from patient records.

## Sample size

For the strangulation prediction model, full cohort was used for analyses. For the non-operative treatment failure prediction model, patients who underwent emergency surgery as initial treatment plan were excluded from analyses. It was estimated that at least 10 events were required for each predictor parameter, and the aim was to achieve 50 patients with strangulation in the development group. This dictated the eventual final sample size, which was not determined at the beginning of the study, as it depended on the strangulation rate in the final cohort.

## Missing data

Missing data were assumed to be missing at random and were imputed for the prediction model development using multiple imputation. Mice-package in R was used for imputation. Ten different imputed data sets were generated, and results reported are based on pooled analyses. The descriptive statistics were analysed before multiple imputation.

## Statistical analysis

Continuous variables are reported as means and standard deviations for normally distributed data and medians and interquartile ranges for data that are not normally distributed. Differences in variable distributions between cohorts, patients with or without strangulation, and patients with non-operative treatment failure or success were assessed using binary logistic regression, t-test or Mann–Whitney U-test for continuous variables and χ2 (2 × 2 tables with Yates’ continuity correction) or Fisher’s exact test for categorical variables.

Two-sided P < 0.050 was considered statistically significant. Data analysis was performed with SPSS® version 28.0 for Macintosh (IBM, Armonk, NY, USA) and R (R Core Team, Vienna, Austria). The rms package in R was used (R package version 6.2-0).

## Model development

Statistics-based variable selection (such as stepwise methods) leads easily to overfit where data set-specific noise is modelled in addition to the actual prediction problem, which potentially inflates the importance of certain predictor effects. To avoid this, variable selection was based on the combination of univariable analysis, previous literature, expert consensus, and clinical usefulness.

Continuous variables were not categorized. Possible non-linear associations were analysed with restricted cubic splines. The model was developed using binary logistic regression. Area under the receiver operator characteristics curve (AUROC) was used to assess model discrimination.

## Model validation

Internal validation was performed by bootstrapping with 1000 resamples where apparent performance of the bootstrap samples and performance in the original data set (test performance) was calculated. Optimism was calculated as an average of apparent performance subtracted by test performance. Optimism corrected AUROC, Nagelkerke R2, calibration intercept, and calibration slope are calculated as apparent performance subtracted by optimism. Calibration intercept is a measure of the difference between average predicted probability and average observed probability and has a target value of 0 (no difference between the average values). Calibration slope evaluates the spread of estimated probabilities, that is how extreme the predictions are, and has a target value of 1 (<1 indicates too extreme predictions often resulting from overfit, >1 indicates too modest predictions)21,22. Optimism-adjusted calibration slope was used as a uniform shrinkage factor and shrunken regression coefficients and refitted intercept are used in external validation.

External validation was performed by analysing model discrimination and calibration in the combined Jorvi and Hyvinkää cohort. Calibration plots were drawn, and the slope and intercept were used to assess the calibration.

## Results

## Participants

During the study period, a total of 626 patients were assessed for eligibility and 145 were excluded, leaving 481 patients in the analyses; 355 patients were identified in Meilahti hospital and formed the model development group; 126 patients were identified in Jorvi and Hyvinkää hospitals and formed the external validation group. Figure

……（全文较长，此处截取前 12000 字符）