# Machine Learning Predicts the Need for Surgical Intervention in Adhesive Small Bowel Obstruction.

> PMC 开放获取全文（PMC11513430），对应文献笔记：[[39473722_Machine Learning Predicts the Need for Surgical Interventi]]

Corresponding author: Akihisa Matsuda, a-matsu@nms.ac.jp

## Objectives:

To explore the predictive performance on the need for surgical intervention in patients with adhesive small bowel obstruction (ASBO) using machine-learning (ML) algorithms and investigate the optimal timing for transition to surgery.

## Methods:

One hundred and six patients with ASBO who initially underwent long transnasal intestinal tube (LT) decompression were enrolled in this retrospective study. Traditional logistic regression analysis and ML algorithms were used to evaluate the risk of need for surgical intervention.

## Results:

Non-operative management (NOM) by LT decompression failed in 28 patients (26%). Multivariate logistic regression analysis identified a drainage volume ≥665 ml via LT on day 1, interval between ASBO diagnosis and LT intubation, and small bowel dilatation at 48 h after LT intubation to be independent predictors of transition to surgery (odds ratios 7.10, 1.42, and 19.81, respectively; 95% confidence intervals 1.63-30.94, 1.00-2.02, and 3.04-129.10; P-values 0.009, 0.047, and 0.002). The random forest algorithm showed the best predictive performance of five ML algorithms tested, with an area under the curve of 0.889, accuracy of 0.864, and precision of 0.667 in the test set. 97.4% of patients without transition to surgery (n=78) had passes of first flatus until three days.

## Conclusions:

This is the first study to demonstrate that ML algorithm can predict the need for surgery in patients with ASBO. The guideline recommended period for initial NOM of 72 h seems to be reasonable. These findings can be used to develop a framework for earlier clinical decision-making in these patients.

## Introduction

Postoperative complications are associated with increased morbidity and medical costs, and adhesive small bowel obstruction (ASBO) is a common complication after abdominal surgery and a common cause of surgical emergencies[1,2]. ASBO can cause considerable harm, requiring eight days of hospitalization on average with an in-hospital mortality rate of 3% per episode[3-6]. The management strategy for ASBO varies widely according to era, country, institution, and the personal preferences of surgeons. Immediate surgical intervention has traditionally been the mainstay of treatment for patients with ASBO[7,8]. However, previous studies have demonstrated that non-operative management (NOM) is effective in approximately 70% of these patients[6,9]. The 2018 Bologna guideline[10] strongly recommends initial NOM until 72 h for patients with ASBO, who had no signs that require emergent surgical exploration (i.e., to peritonitis, strangulation or bowel ischemia). NOM for ABSO consists of fasting, intravenous fluids, and gastrointestinal decompression using a nasogastric tube (NGT) and/or a long transnasal intestinal tube (LT). Approximately 30% of patients with ASBO who are initially treated by NOM, particularly an LT, ultimately require surgical intervention[11-13]. Delayed surgical intervention have been associated with increased morbidity, mortality, a prolonged hospital stay, and increased medical costs[14-17]. Furthermore, the 72-h period of NOM recommended by the guideline[10] is not evidence-based. Therefore, it is clinically important to be able to identify predictors of failure of LT decompression and the optimal timing for transition to surgery to minimize the risk of delayed surgery in patients who require it and avoid an unnecessary medical burden.

The recent advent of machine learning (ML) has led to innovations in various fields. The methodology used in ML allows predictions to be made based on existing data. Moreover, the accuracy of prediction is better with an ML algorithm than with conventional regression models. ML has an important role in analysis of complex medical data and has demonstrated its superiority in studies based on omics, electronic health records, and image processing[18-20]. However, few researchers have investigated ASBO and the limited literature available tends to focus on radiological diagnosis[21,22]. Therefore, in this study, we sought to identify predictors of the need for surgical intervention after NOM by building ML models and its optimal timing in a retrospective cohort of patients with ASBO.

## Methods

## Patients

We retrospectively reviewed the medical records of 106 patients with ASBO who were treated by LT decompression between September 2011 and August 2016 in the Department of Surgery at Nippon Medical School Chiba Hokusoh Hospital. ASBO was diagnosed on the CT images if the images showed a dilated small bowel and if there were clinical symptoms of nausea, vomiting, or abdominal fulness present. In our department, the first step in NOM for patients with ASBO is decompression with a 12 or 16 Fr NGT (Salem Sump™, Coviden, Tokyo, Japan) or 18 Fr LT, continuously suctioned with negative pressure of 10 cmH2O, (ClinyⓇ, Create Medic, Tokyo, Japan). If NGT decompression is ineffective at around 48 h after intubation, the NGT is replaced with an LT to improve the efficacy of decompression. We initially introduced LT for decompression in patients with severe abdominal fullness and/or severe radiological findings, such as an intense degree of width and range of small intestinal dilatation. For intubation using an LT, 50 ml of water-soluble contrast agent (WSCA; GastrografinⓇ, Bayer, Leverkusen, Germany) are administered via a catheter to confirm the position of the tip of the LT. Surgical intervention for patients who have failed on NOM is planned for around seven days after intubation.

The inclusion criteria in this study were age ≥20 years, previous history of laparotomy, ASBO diagnosed by abdominal computed tomography, and LT decompression. The following exclusion criteria were applied: need for surgery because of suspected strangulation or perforation, recurrence of ASBO within 30 days of laparotomy, and inflammatory bowel disease, mesenteric vascular disease, suggestive of non-adhesive etiologies such as paralytic ileus, fecal impaction, peritoneal carcinomatosis, incarcerated hernia. Attending surgeons determined the indication for surgical intervention based on clinical and radiological findings and a constant drainage volume.

The study protocol was approved by the ethics committee of Nippon Medical School Chiba Hokusoh Hospital (approval number: 522) and conducted in accordance with the Declaration of Helsinki. The requirement for written informed consent was waived in view of the retrospective nature of the research.

## Data collection

Clinical characteristics, laboratory data on admission, and radiologic findings over time were retrieved from the medical records. Information was collected on age, sex, date of diagnosis of ASBO, date of LT intubation, date and type of any previous laparotomic procedures, surgical history, number of recurrences of ASBO, comorbidities, drainage volume on day 1 after LT intubation, white blood cell count, creatine phosphokinase and C-reactive protein levels, ascites, passage of WSCA through the colon at 48 h, and dilatation of the small intestine (normal, 4 cm[23]) at 48 h after LT intubation assessed by radiography or CT, passes of first flatus, and if so, the date.

## Analysis of data

Continuous data are expressed as the median with interquartile range. Continuous variables were compared using the Mann-Whitney U test. Discrete variables were compared using the chi-squared test and Fisher's exact test. To identify risk factors for transition to surgical intervention, multivariate logistic regression analyses were applied using variables that were statistically significant in univariate analysis and had a P-value <0.1. The statistical analyses were performed using BellCurve for Excel (Social Survey Research Information, Tokyo, Japan). A P-value of <0.05 was considered statistically significant. Python software version 3.8 was used for statistical testing and computing ML methods. The study population was randomly divided into a training set and a test set in a ratio of 8:2. The prediction model was established by creating a training set and then applying the trained model to the test set for prediction. Five algorithms, namely, decision tree, random forest, gradient boosting, naïve Bayes, and logistic regression, were used to evaluate the likelihood of risk of transition to surgical intervention. The prediction model was developed based on the ML algorithm with the best performance, which was determined by the area under the curve (AUC). If the AUC is greater than 0.9, then it is considered to have excellent predictive power in the model.

## Results

The patient demographics and clinical characteristics are shown in Table 1. NOM with LT decompression was successful in 78 patients (74%) and failed (i.e., transition to surgical intervention was required) in 28 (26%). Body mass index was significantly lower in the surgery group than in the non-surgery group (P=0.033). Previous operations for non-inflammatory and malignant disease were more common in the surgery group than in the non-surgery group; however, the between-group differences were not statistically significant (P=0.085 and P=0.083, respectively). A history of surgery via a laparoscopic approach was significantly more common in the surgery group (P=0.041). The number of previous surgeries and number of occurrences of ASBO were comparable between the study groups, as was the rate of bridging from NGT to LT intubation. The interval between diagnosis of ASBO and LT intubation was significantly longer and the drainage volume via the LT on day 1 was significantly greater in the surgery group than in the non-surgery group (P<0.001 and P<0.001, respectively). The rate of passage of WSCA into the colon at 48 h was significantly lower and the rate of small intestinal dilation at 48 h after LT intubation was significantly higher in the surgery group (P=0.020 and P<0.001, respectively). The median interval between LT intubation and surgical intervention was 7.0 days in the surgery group. There was a significant between-group difference in the total length of hospital stay.

Clinical Characteristics of ASBO Patients (n=106).

Abbreviations: ASBO, adhesive small bowel obstruction; NGT, nasogastric decompression tube; LT, long transnasal intestinal tube; WSCA, water-soluble contrast agent; NOM, non-operative management

aMedian (interquartile range)

The results of multivariate logistic regression analysis for transition to surgical intervention are shown in Table 2. Drainage volume via the LT ≥665 ml on day 1, interval between diagnosis of ASBO and LT intubation, and small bowel dilatation at 48 h were identified to be independent predictors of transition to surgical intervention (odds ratios 7.10, 1.42, and 19.81, respectively; 95% confidence intervals 1.63-30.94, 1.00-2.02, and 3.04-129.10; P-values 0.009, 0.047, and 0.002).

Multivariate Logistic Regression Analysis for Transition to Surgery.

Abbreviations: LT, long transnasal intestinal tube; WSCA, water-soluble contrast agent

Body mass index and drainage volume via LT (1st day) were divided using the cut-off of respective median values.

The relative importance of variables in the random forest and gradient boosting algorithms for prediction of transition to surgical intervention is shown in Figure 1A, 1B. The top three important variables were identified to be drainage volume via the LT on day 1, small bowel dilatation at 48 h, and interval between diagnosis of ASBO and LT intubation by the random forest algorithm and drainage volume via the LT on day 1, small bowel dilatation at 48 h, and white blood cell count by the gradient boosting algorithm. The receiver-operating characteristic (ROC) curves for the five ML algorithms are shown for the training set in Figure 2 and for the test set in Figure 3. A summary of the performance of each algorithm in each set is shown in Table 3. In the traini

……（全文较长，此处截取前 12000 字符）