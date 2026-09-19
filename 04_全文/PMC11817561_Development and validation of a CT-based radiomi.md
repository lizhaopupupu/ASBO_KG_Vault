# Development and validation of a CT-based radiomic nomogram for predicting surgical resection risk in patients with adhesive small bowel obstruction.

> PMC 开放获取全文（PMC11817561），对应文献笔记：[[39934668_Development and validation of a CT-based radiomic nomogram]]

## Background

Adhesive small bowel obstruction (ASBO) is a common emergency that requires prompt medical attention, and the timing of surgical intervention poses a considerable challenge. Although computed tomography (CT) is widely used, its effectiveness in accurately identifying bowel strangulation is limited. The potential of radiomics models to predict the necessity for surgical resection in ASBO cases is not yet fully explored.

## Objectives

The aim of this study is to identify risk factors for surgical resection in patients with ASBO and to develop a predictive model that integrates radiomic features with clinical data. This model designed to estimate the likelihood of surgical intervention and aid in clinical decision-making for acute ASBO cases.

## Methods

From January 2019 to February 2022, we enrolled 188 ASBO patients from our hospital, dividing them randomly into a training cohort (n = 131) and a test cohort (n = 57) using a 7:3 ratio. We collected baseline clinical data and extracted radiomic features from CT images to compute a radiomic score (Rad-score). A nomogram was developed that combines clinical characteristics and Rad-score. The performance of clinical, radiomic, and combined nomogram models was evaluated in both cohorts.

## Results

Of the 188 patients, 92 underwent surgical resection, while 96 did not. The nomogram integrated factors such as white blood cell count, duration of obstruction, and preoperative infection indicators (fever, tachycardia, peritonitis), along with CT findings (elevated wall density, thickened wall, mesenteric fluid, ascites, bowel wall gas, small bowel feces, and hyperdensity of mesenteric fat) (p < 0.1). This combined model accurately predicted the need for surgical resection, with area under the curve (AUC) values of 0.761 (95% CI, 0.628–0.893) for the test cohort. Calibration curves showed strong agreement between predicted and observed outcomes, and decision curve analysis validated the model’s utility for acute ASBO cases.

## Conclusion

We developed and validated a CT-based nomogram that combines radiomic features with clinical data to predict the risk of surgical resection in ASBO patients. This tool offers valuable support for treatment planning and decision-making in emergent situations.

## Supplementary Information

The online version contains supplementary material available at 10.1186/s12880-025-01575-7.

## Keywords

## Introduction

Small bowel obstruction (SBO) is a common acute abdomen condition, accounting for more than 15% of emergency surgical admissions [1]. Adhesive small bowel obstruction (ASBO) is frequently caused by intraabdominal adhesions, often a consequence of previous surgeries, which induce torsion and angulation of the small bowel [2]. These adhesive bands can compress the small bowel, potentially leading to severe complications such as closed loop formations, strangulation, or even perforation during the course of ASBO [3]. Although most ASBO patients are managed non-operatively, approximately 15% who are admitted to hospitals undergo surgery, making ASBO one of the predominant reasons for small bowel surgeries, including resection, stoma creation, and adhesiolysis [4]. Typically, adhesiolysis is the most common surgical procedure for ASBO, however, between 28% and 45.7% of surgical patients require bowel resection, which is associated with considerable morbidity and mortality [5–7]. In our previous study, postoperative complication rates ranging from 42.31 to 48.87% were observed in ASBO patients who underwent surgical resection, highlighting significant risks [8]. Consequently, surgeons often face challenging decisions regarding the necessity and timing of surgical resection for ASBO patients: operating too early can increase costs compared to nonoperative treatments and expose patients to surgical risks; however, delayed surgery may lead to prolonged hospital stays and increased risks of intra-abdominal sepsis [9]. Clinical evaluations for assessing bowel viability are often inadequate in timing and accuracy.

Currently, several radiologic procedures are available to assist in evaluating the severity of ASBO, with CT imaging being the most utilized method. Previous studies have validated the advantages of CT imaging in diagnosing, locating, and determining the degree of obstruction, with an accuracy of approximately 70% in identifying bowel ischemia [10, 11]. Nonetheless, the effectiveness of abdominopelvic CT in determining surgical indications remains limited [12]. Matsushima et al. developed a radiographic model based on image signs to predict the necessity for surgical intervention, yet only 10% of patients requiring surgery exhibited the relevant CT findings [13]. Moreover, most previous studies focused primarily on analyzing the relationship between typical CT characteristics and surgical risk, yet these characteristics often appear on CT images only after ASBO has progressed significantly, failing to timely indicate the pathological status of the intestinal tract and potentially causing surgeons to miss the optimal timing for resection of necrotic intestine [14, 15]. Thus, to date, no practical image-based tool effectively predicts the risk of surgical resection at an early stage of ASBO.

In recent years, radiomics has emerged as a novel method for quantifying disease changes through data mining of images and has been widely validated in clinical imaging. This innovative technique extracts quantitative parameters that are imperceptible through visual inspection, using high-throughput technology from images, and enhances decision-making [16]. Radiomic models are increasingly utilized for diagnosing diseases and predicting the prognosis of cancer, such as the preoperative prediction of metastasis or recurrence in gastrointestinal cancers [17]. We previously developed a radiomic model using 167 CT enterography images from Crohn’s disease (CD) cases and achieved good performance in predicting the inflammatory severity of bowel segments in CD patients [18]. Consistent with a series of studies [18, 19], our results underscored the potential usefulness of radiomics in evaluating benign diseases. ASBO, characterized as a benign disease, involves diseased bowel segments whose histopathological changes can be depicted in CT imaging. Thus, we speculate that applying radiomics to predict the surgery risk of ASBO holds promise.

Based on this premise, this study screened clinical risk factors related to the surgical resection risk of ASBO from intraoperative findings, clinical data, and blood biochemical indices, and extracted imaging features of obstructive diseased lesions using radiomic methods. An integrative radio-clinic model was constructed, combining novel imaging features, which is easily applied clinically and provides a crucial basis for rational decision-making in the treatment of ASBO.

## Materials and methods

The CLEAR checklist was used for guiding the reporting of current study and is presented in a Supplementary Table S1 [20]. The overall quality of the pipeline was assessed by the METhodological RadiomICs Score (METRICS) tool [21], with a METRICS score of 82.1% (Supplementary Table S2). This retrospective study was approved by the Ethics Committee of the Affiliated Hospital of Qingdao University (QYFYWZLL26445).

## Patients

The researchers followed all the rules laid out in the Declaration of Helsinki. Patients diagnosed with ASBO who underwent surgery between January 2019 and February 2022 were retrospectively identified. Surgical resections were indicated when intraoperative findings suggested compromised bowel viability, such as signs of prolonged ischemia or necrosis. A total of 188 cases were included, comprising patients who underwent surgical resection and those who did not. These cases were randomly divided into a training cohort (n = 131) and a test cohort (n = 57) at a 7:3 ratio. The randomization process was presented in Supplementary materials A1. Inclusion criteria included: (1) diagnosis of ASBO based on clinical, histological, or radiological findings; (2) history of abdominal surgeries; (3) emergent surgery due to ASBO; and (4) preoperative abdominal CT scans obtained within 24 h of admission. Exclusion criteria included: (1) admission to a non-emergency department; (2) incomplete surgical reports or missing clinical data; (3) bowel obstruction due to primary tumors, hernias, acute mesenteric vascular embolism, ischemic bowel disease or inflammatory bowel disease; and (4) age under 18 years. The patient selection flowchart is shown in Supplementary Figure S1.

## Baseline Clinical Data Collection

Baseline clinical data were collected according to established protocols and included sex, age, body mass index (BMI), presenting symptoms (defecation issues, vomiting, abdominal pain), history of previous abdominal surgeries, time to obstruction, American Society of Anesthesiologists (ASA) score, signs of abdominal sepsis, and laboratory indicators (white blood cell count, platelet count, hemoglobin, albumin, and C-reactive protein levels). Typical CT features associated with surgical resection, as identified in prior studies [11, 22–23], included elevated wall density, wall thickening, mesenteric fluid, ascites, bowel wall gas, small bowel feces, free air, hyperdensity, and whirlpool sign of mesenteric fat. Two experienced radiologists, blinded to the clinical outcomes, reviewed the CT images using the predefined criteria (Supplementary Table S3 and Figure S2).

## CT image evaluation

CT scans were performed within 24 h of emergent admission using two scanners: Somatom Sensation 64 (Siemens Healthcare) and Discovery 750 (GE Healthcare). Scanning parameters included a tube current of 200 mA, tube voltage of 120 kV, matrix size of 512 × 512, pitch of 0.8, and a section thickness of 5 mm. All patients received abdominal CT prior to emergency surgery, revealing dilated loops and transition points. Two radiologists, each with over ten years of experience and blinded to clinical details, independently evaluated the CT images.

## Clinical model construction

Univariate analyses were conducted to compare clinical characteristics, including clinical data, laboratory parameters, and CT findings, between patients who underwent surgical resection and those who did not, using the training set. A multilayer perceptron (MLP) network classifier and logistic regression (LR) were used to develop the clinical model, incorporating significant factors identified through univariate regression. Odds ratios (ORs) and 95% confidence intervals (CIs) were calculated to estimate the relative risks associated with independent factors.

## Image segmentation and extraction of Radiomic features

The workflow of radiomics analysis is depicted in Fig. 1. The first step is volume of interest (VOI) segmentation. Three-dimensional volume rendering was used to analyze the diseased bowel segments, providing greater flexibility than two-dimensional volume rendering [24]. Two experienced radiologists, unaware of clinical details, delineated the VOI within the bowel from axial CT images. Semiautomated threshold-based 3D Slicer software (version 4.11) was used for 3D segmentation, with contours drawn slice-by-slice at the transition zone between dilated small bowel and flat loops, ensuring minimal interference from surrounding structures. Two experienced radiologists meticulously outlined the contours of transition zone and adjacent lumen. This was done to evaluate inter-observer reproducibility. Subsequently, a senior radiologist reviewed the differing opinions and reached a consensus to define unified VOIs. The process of VOI segmentation for two representative patients is illustrated in Fig. 2, and the details are described in Supplementary materials A2. Radiomic features were extracted from the segmented VOIs using the 3D Slicer Radiomics Extension Pack (version 4.10.2). Features includ

……（全文较长，此处截取前 12000 字符）