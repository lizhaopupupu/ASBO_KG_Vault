# Multimodal predictive model for strangulation risk in adhesive small bowel obstruction using deep learning and electronic health record data.

> PMC 开放获取全文（PMC12454952），对应文献笔记：[[40983055_Multimodal predictive model for strangulation risk in adhe]]

Authors contribute equally

## Aims

This study aimed to develop and validate a multimodal predictive model for the risk of strangulation in adhesive small bowel obstruction by integrating deep learning–based computed tomography imaging features and clinical electronic health records.

## Methods

A retrospective, observational, multicenter study was conducted across three hospitals, with data from 225 patients used for model development and 123 patients for external validation. A three-dimensional convolutional neural network with a ResNet50 backbone was used to segment abdominal regions from computed tomography scans and classify strangulation risk. The multimodal model integrated deep learning predictions with top electronic health record features using the XGBoost algorithm; global and local interpretability were achieved through variable importance ranking and local interpretable model-agnostic explanations.

## Results

The multimodal model demonstrated superior performance in predicting strangulation within 7 days of admission, achieving an area under the curve of 0.915 in the training set and 0.912 in the test set, outperforming single-modality models. Calibration plots showed good alignment between predicted and observed outcomes, decision curve analysis demonstrated significant clinical utility, and net reclassification improvement confirmed that deep learning enhanced the model’s predictive ability.

## Conclusion

This study highlights the potential of multimodal artificial intelligence combined with clinical data to improve diagnostic accuracy and support clinical decision making in adhesive small bowel obstruction.

## Introduction

Adhesive small bowel obstruction (ASBO) remains a leading cause of emergency surgical admissions. 1 In line with the current Bologna guidelines, ASBO can be managed nonoperatively with intravenous fluid administration, nasogastric tube placement, and the prescription of oral water-soluble contrast, provided there is no suspicion of intestinal ischemia, i.e. strangulation.2,3 Immediate surgical intervention is mandatory if strangulation is suspected. The overall mortality rate following laparotomy for ASBO exceeds 7%, and a delay in emergency laparotomy beyond 72 hours after admission is associated with higher 30-day postoperative mortality and prolonged hospital stays. When nonoperative management fails, costs escalate more than seven fold.4,5 However, identifying patients at high risk of strangulation remains challenging. Robust predictive models that can accurately forecast strangulation could facilitate earlier surgical decision making and ultimately improve both short- and long-term outcomes.

Despite the fact that adhesions are not directly visible on computed tomography (CT) scans, CT imaging can accurately differentiate among various causes of bowel obstruction by ruling out other etiologies.6,7 CT scans are widely acknowledged as the preferred imaging modality when there is uncertainty regarding the diagnosis of SBO, and they are essential for assessing the need for urgent surgery. 8

Recent advances in clinical artificial intelligence have highlighted the transformative potential of multimodal models, which integrate diverse data types (e.g. tabular clinical data, imaging, and text) to enhance diagnostic and prognostic accuracy.9–11 Multimodal fusion leverages complementary information from heterogeneous sources, addressing the limitations of single-modality approaches and aligning with clinicians’ holistic decision-making processes. 12 The integration of imaging and nonimaging data enhances predictive power by resolving data heterogeneity, whereas multimodal approaches emulate clinicians’ reliance on multiple data types for diagnosis and prognosis, mirroring real-world workflows.13,14

Based on this rationale, this study identified clinical risk factors at admission associated with the risk of strangulation in ASBO from basic demographics, symptoms, laboratory tests, and abdominal CT imaging features analyzed using three-dimensional (3D) deep learning. A multimodal model combining tabular electronic health record (EHR) data with deep learning–based CT features was developed to provide a critical basis for rational decision making on the timing of surgery for ASBO.

## Methods

## Study design

This investigation was a retrospective, observational, multicenter trial conducted across three hospitals: the First Affiliated Hospital of Soochow University, the Jintan Affiliated Hospital of Jiangsu University, and Suzhou Yongding Hospital. The prediction models were developed using data from patients at Soochow University Hospital and externally validated using data from patients at Yongding and Jiangsu University hospitals. The study recruitment period spanned January 2016 to December 2024. Ethical approval was obtained from the ethics committee of the First Affiliated Hospital of Soochow University (approval number: 2022098). Informed consent was waived for this retrospective study. The study flowchart is depicted in Figure 1.

Flowchart of the study.

## Participants

Patients presenting to the surgical emergency department with CT-confirmed ASBO and clinically relevant blood samples were included. Exclusion criteria included patients younger than 18 years of age, pregnant individuals, those who had undergone abdominal surgery within the preceding 30 days, patients with inflammatory bowel disease, and those with SBO resulting from intraluminal obstruction, abdominal wall hernia, or peritoneal carcinomatosis. No additional trial interventions were performed after inclusion; patients were managed according to standard hospital protocols. Emergency surgery was performed if strangulation was suspected; otherwise, nonoperative treatment was initiated, including intravenous hydration and nasogastric tube insertion.2,5,15 Signs of strangulation during nonoperative treatment or failure to resolve the obstruction were indications for urgent surgery. 16

## Outcome and variables

The primary study outcome was strangulation, defined by operative findings of intestinal ischemia (either bowel necrosis or reversible ischemia) within 7 days of admission. Data collected at admission from EHRs included the following: (a) patient demographics, medical conditions, prior abdominal surgeries, and SBO; (b) clinical symptoms and signs; and (c) laboratory tests, including complete blood counts, liver and kidney function tests, electrolytes, and markers of glucose and lipid metabolism. Non–contrast-enhanced (plain) CT images obtained within 24 h of admission were also collected. Researchers collecting the data were blinded to patient outcomes. Missing data were handled with median imputation for continuous variables and mode imputation for categorical variables, as part of the standard preprocessing pipeline before model development. Specific definitions for key variables were as follows: 1. Fever was defined as a body temperature ≥38.0°C at the time of admission; 2. abdominal guarding was recorded based on the attending physician’s physical examination, indicating involuntary muscle contraction upon palpation, a sign of peritoneal irritation; 3. prior SBO events were identified from the patient’s medical history documented in the EHR, including any previous clinical or radiological diagnosis of SBO; and 4. all laboratory values (e.g. white blood cell (WBC) and C-reactive protein (CRP)) were the first test results obtained within 24 hours of admission.

## Deep learning–based CT model

We developed a supervised deep learning framework using a 3D convolutional neural network (CNN) with a ResNet50 backbone to segment abdominal and pelvic regions from CT digital imaging and communications in medicine (DICOM) files and classify them into binary categories (strangulation present or absent).

## Abdominal and pelvic region segmentation

Segmentation of the abdominal and pelvic regions from CT DICOM files was the initial step in the framework. This preprocessing step was crucial to focus the model on relevant regions while reducing computational load and minimizing irrelevant noise.

## Data preprocessing

CT DICOM files were converted into a format suitable for deep learning. Each CT scan, comprising multiple two-dimensional slices, was stacked into a 3D volume. Hounsfield unit values were normalized to ensure consistency across scans.

## Segmentation model

A U-Net architecture, renowned for medical image segmentation, was used. The model was trained on annotated CT scans with manually delineated abdominal and pelvic regions by expert radiologists. The model learned to identify these regions based on anatomical features and intensity patterns in the CT images.

## Postprocessing

After segmentation, the abdominal and pelvic regions were resized to a standard dimension (e.g. 256 × 256 ×64) to ensure uniformity for subsequent processing. This step also involved noise reduction and preservation of anatomical integrity.

## Supervised deep learning model for binary classification

The second component of our framework was a supervised deep learning model designed to classify segmented abdominal and pelvic regions into binary categories (strangulation present or absent).

## Model architecture

A 3D CNN with a ResNet50 backbone was utilized. The model, which comprised multiple convolutional layers with batch normalization and rectified linear unit–activation functions, extracted spatial and volumetric features from CT scans to capture complex patterns associated with strangulation.

## Training and validation

The model was trained on segmented CT scans labeled as “strangulation present” or “absent” based on clinical diagnosis. The dataset was divided into training (80%) and validation (20%) sets. Training was performed using the Adam optimizer with a learning rate of 0.001 and a batch size of eight. The binary cross-entropy loss function was used for training.

## Multimodal model

To select EHR variables, we first performed univariate analyses comparing clinical and laboratory features between the strangulation and nonstrangulation groups in the training cohort. Variables demonstrating significant differences and high clinical relevance were selected for the next step. A two-way multimodal model for ASBO strangulation was then constructed by integrating predictions from the deep learning–based CT model with the top four tabular EHR features using the XGBoost algorithm. 17 This approach ensured the use of robust, interpretable, and widely available clinical predictors for multimodal integration.

## Visualization

The characteristics and performance of the multimodal model were evaluated using multiple techniques, including global interpretation (variable importance ranking), local interpretation (local interpretable model-agnostic explanations, LIME), calibration plots, and decision curve analysis (DCA) plots.

LIME provides visual explanations of each feature’s contribution to predictions, offering transparency and interpretability for individual predictions. 18 Partial dependence plots (PDPs) provide a global perspective on the average marginal effect of each feature on the predicted probability of strangulation. Calibration plots assess the alignment between predicted probabilities and observed outcomes, with deviations from the diagonal indicating miscalibration. 19 DCA evaluates the clinical utility of predictive models by quantifying net benefit across decision thresholds, incorporating clinical consequences, and comparing models against default strategies. 20

## Statistical analysis and software

Statistical analyses were performed using R (version 4.1.0) and Python (version 3.9). Continuous variables were reported as means ± SDs for normally distributed data, and as medians with interquartile ranges for non-normally distributed data. Differences in variable distributions between groups were assessed using t-tests or Mann–Whitney U-tests for con

……（全文较长，此处截取前 12000 字符）