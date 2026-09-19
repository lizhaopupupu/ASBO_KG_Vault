# Predicting postoperative adhesive small bowel obstruction in infants under 3 months with intestinal malrotation: a random forest approach.

> PMC 开放获取全文（PMC11889664），对应文献笔记：[[39765335_Predicting postoperative adhesive small bowel obstruction]]

## Objective

This study aimed to develop a predictive model using a random forest algorithm to determine the likelihood of postoperative adhesive small bowel obstruction (ASBO) in infants under 3 months with intestinal malrotation.

## Methods

A machine learning model was used to predict postoperative adhesive small bowel obstruction using comprehensive clinical data extracted from 107 patients with a follow-up of at least 24 months. The Boruta algorithm was used for selecting clinical features, and nested cross-validation tuned and selected hyper-parameters for the random forest model. The model's performance was validated with 1000 bootstrap samples and assessed using receiver operating characteristic (ROC) analysis, the area under the ROC curve (AUC), sensitivity, specificity, precision, and F1 score.

## Results

The random forest model demonstrated high diagnostic accuracy with an AUC of 0.960. Significant predictors of ASBO included pre-operative white blood cell count (pre-WBC), mechanical ventilation (MV) duration, surgery duration, and post-operative albumin levels (post-ALB). Partial dependence plots showed non-linear relationships and threshold effects for these variables. The model achieved high sensitivity (0.805) and specificity (0.952), along with excellent precision (0.809) and a robust F1 score (0.799), indicating balanced recall and precision performance.

## Conclusion

This study presents a machine learning model to accurately predict postoperative ASBO in infants with intestinal malrotation. Demonstrating high accuracy and robustness, this model shows great promise for enhancing clinical decision-making and patient outcomes in pediatric surgery.

## Keywords

Editor: G.P. da Silva

## Introduction

Intestinal malrotation is a congenital disorder characterized by abnormal embryonic midgut development, resulting in disrupted bowel rotation and fixation. This leads to anatomical abnormalities that increase the risk of complications such as volvulus and obstruction. Approximately 1 in 500 live births are affected by this condition,1, 2, 3 which is usually diagnosed during infancy or early childhood. The current standard treatment for intestinal malrotation is surgical intervention, aiming to correct the anatomical abnormalities and minimize the risk of complications. However, even with advancements in surgical techniques and perioperative care, some patients may develop postoperative complications, including adhesive small bowel obstruction (ASBO).

ASBO frequently occurs following abdominal surgery),4, 5, 6 such as that for intestinal malrotation. It is caused by fibrous bands, known as adhesions, forming between abdominal organs and tissues. These adhesions can lead to intestinal obstruction through compression or torsion of the bowel, producing symptoms like abdominal pain, distension, and emesis. The incidence of ASBO post-surgery for intestinal malrotation ranges from 8 % to 29 %.7, 8, 9, 10, 11, 12

Diagnosing ASBO currently relies heavily on clinical judgment and imaging techniques).13,14 However, these methods have limitations in specificity and can be challenging due to the subtle presenting symptoms in infants. Consequently, there is growing interest in using machine learning algorithms to enhance diagnostic accuracy and support decision-making in the early identification of ASBO.

Machine learning models, which have become increasingly popular in various fields, offer advantages over traditional statistical analysis methods. They can analyze nonlinear relationships between data, proving beneficial in disease diagnosis, subtype identification, and biomarker discovery).15, 16, 17 Random forest is a machine learning algorithm that uses an ensemble of decision trees to make predictions. Each decision tree in the “forest” works independently, analyzing different parts of the data to classify outcomes or make predictions. The final result is determined by combining the outputs of all the trees.

This study aims to apply a random forest algorithm to develop a predictive model for early identification of ASBO in infants under three months who have undergone surgery for intestinal malrotation. By analyzing a range of clinical parameters, the goal is to establish a model that effectively predicts the likelihood of ASBO. This will aid in timely clinical decision-making, optimize patient management, and ultimately improve outcomes for this vulnerable patient group.

## Material and methods

This study's framework, depicted in Figure 1, includes three main parts: data preparation, model building, and model visualization and evaluation.Figure 1Architecture of the framework of this study.Figure 1

Architecture of the framework of this study.

## Patient selection

Patients treated at the Children's Hospital of Chongqing Medical University from January 2012 to December 2020 were enrolled in this study. All participants were diagnosed with intestinal malrotation and had undergone surgery. They were followed up for at least two years postoperatively, with categorization based on the occurrence of ASBO. The Ethics Committee of the Children's Hospital of Chongqing Medical University approved this study (File No 57–2, 2022).

## Inclusion and exclusion criteria

The study included patients aged under three months, definitively diagnosed with intestinal malrotation, and who had undergone Ladd's procedure at the hospital. Exclusion criteria encompassed patients with incomplete clinical data, those who discontinued treatment or left the hospital voluntarily, and those with less than two years of follow-up.

## Definition of ASBO

Adhesive small bowel obstruction (ASBO) is characterized by symptoms such as vomiting, abdominal pain, and distension. Its diagnosis is confirmed by abdominal X-rays showing significant intestinal loop dilation and air-fluid levels. ASBO commonly results from fibrous adhesions in the small intestine, often occurring after abdominal surgeries.

## Predictor variables

The present study carefully selected a wide range of factors for a comprehensive analysis that includes both clinical observations and laboratory data. Factors considered include the rotation angle observed during surgery, and demographic and physiological data like gender, age in days, mode of delivery, birth weight, and admission weight. Surgical evaluation focused on the duration of the procedure, while postoperative care included mechanical ventilation duration (MV duration). Laboratory analysis, covering both preoperative and postoperative periods, involved parameters such as white blood cell count (WBC), neutrophil-to-lymphocyte ratio (NLR), red blood cell count (RBC), hemoglobin (HB), platelet count (PLT), C-reactive protein (CRP), total bilirubin (TBIL), and blood urea nitrogen (BUN), with postoperative values collected between 5 and 7 days after surgery. The liver function test enzyme index (LFTEI) was calculated from alanine aminotransferase (ALT) and aspartate aminotransferase (AST) levels and the time to start oral feeding (SOF) was recorded as an indicator of postoperative recovery.

## Feature selection

In this study, the authors used the Boruta algorithm for feature selection to identify significant predictors of ASBO in patients with intestinal malrotation. Designed for high-dimensional datasets, the Boruta algorithm creates shadow features by generating random copies of the original features. It then compares the importance of each real feature to these shadow features using a random forest classifier. Features less important than the most significant shadow feature are iteratively removed, ensuring that only those with statistically significant contributions to the model's predictive power are retained.

## Parameter tuning

After feature selection, the authors utilized the random forest algorithm for modeling, to optimize the random forest model, we applied a nested cross-validation approach combined with grid search. This approach addresses the challenges posed by the limited sample size. Instead of partitioning the dataset into distinct training and testing sets, the authors implemented 4-fold cross-validation in both the inner and outer loops of the nested procedure. This approach provides a robust estimate of model performance by evaluating various parameter combinations across different data subsets.

In the inner loop, grid search systematically explored parameter settings, with each configuration evaluated through 4-fold cross-validation. The results were visualized using heatmaps, facilitating the identification of optimal parameter combinations based on performance metrics. This method minimizes the risk of overfitting by ensuring the selected parameters generalize effectively across the entire dataset, thereby enhancing predictive performance.

## Model visualization and evaluation

The authors employed feature importance metrics and partial dependence plots to visualize and interpret the model. Feature importance metrics identified variables significantly influencing predictions, while partial dependence plots illustrated the effects of key features on the model's output. To further enhance interpretability, the authors visualized six individual trees from the random forest model, providing insights into the contributions of different trees to the final predictions.

For model evaluation, the authors applied a bootstrap method with 1000 replications, yielding reliable estimates of accuracy, sensitivity, specificity, F1 score, and the area under the ROC curve (AUC). The ROC curve analysis assessed the model's ability to discriminate between classes, serving as a robust diagnostic tool. Together, these visualization and evaluation techniques ensured the robustness and reliability of the model.

## Statistical analysis and software tools

Continuous variables were presented as mean ± standard deviation (SD) or median (p25, p75), depending on their distribution. Categorical variables were expressed as numbers and percentages. The authors used the t-test or Wilcoxon rank-sum test for continuous variables, and the chi-square test for categorical variables, based on data distribution.

Descriptive statistics and data management were performed using IBM SPSS Statistics (version 27). Feature selection with the Boruta algorithm was conducted in R using the ‘Boruta’ package (version 4.3.1). Random forest modeling, visualization, and evaluation were carried out in Python (version 3.11).

## Results

In this study, 107 infants were included. Table 1 presents the demographic and clinical characteristics of both the non-ASBO (n = 87) and ASBO (n = 20) groups. Notably, there is a female majority in both groups, with a higher percentage of females in the ASBO group. A significant finding is the longer duration of surgery in the ASBO group compared to the non-ASBO group. Correspondingly, the ASBO group required extended MV duration postoperatively. Hematological analysis revealed significant changes in specific blood parameters when comparing pre-and post-operative values in both groups. Particularly, the ASBO group exhibited a substantial postoperative increase in WBC, potentially indicating a stronger inflammatory or stress response to surgery. Additionally, the NLR, another critical systemic inflammation indicator, was notably higher in the ASBO group after surgery.Table 1Demographic and clinical characteristics.Table 1non-ASBO, n = 87ASBO, n = 20gender male21 (24.1 %)2 (10 %) female66 (75.9 %)18 (90 %)mode of delivery vaginal delivery28 (32.2 %)10 (50 %) cesarean section59 (67.8 %)10 (50 %)rotation angle, degree360 (360,540)540 (360,675)days of age8 (3,17)7.5 (5,28)birth weight, kg3.21 (2.90,3.50)3.29 (3.00,3.45)admission weight, kg3.05 (2.70,3.60)3.09 (2.72,3.98)surgery duration, minutes65 (50,80)108 (75,139)MV duration, hours5.5 (3.6,11.4)15.9 (11.6,21.6)pre-WBC, *10^9/L6.6 (4.9,8.9)9.7 (7.8,14.5)pre-NLR1.33 (0.98,2.14)1.92 (1.22,2.7)pre-RBC, *10^12/L3.7 (3

……（全文较长，此处截取前 12000 字符）