# Deep learning using computed tomography to identify high-risk patients for acute small bowel obstruction: development and validation of a prediction model : a retrospective cohort study.

> PMC 开放获取全文（PMC10720875），对应文献笔记：[[37720936_Deep learning using computed tomography to identify high-r]]

## Objective:

To build a novel classifier using an optimized 3D-convolutional neural network for predicting high-grade small bowel obstruction (HGSBO).

## Summary background data:

Acute SBO is one of the most common acute abdominal diseases requiring urgent surgery. While artificial intelligence and abdominal computed tomography (CT) have been used to determine surgical treatment, differentiating normal cases, HGSBO requiring emergency surgery, and low-grade SBO (LGSBO) or paralytic ileus is difficult.

## Methods:

A deep learning classifier was used to predict high-risk acute SBO patients using CT images at a tertiary hospital. Images from three groups of subjects (normal, nonsurgical, and surgical) were extracted; the dataset used in the study included 578 cases from 250 normal subjects, with 209 HGSBO and 119 LGSBO patients; over 38 000 CT images were used. Data were analyzed from 1 June 2022 to 5 February 2023. The classification performance was assessed based on accuracy, sensitivity, specificity, and area under the receiver operating characteristic curve.

## Results:

After fivefold cross-validation, the WideResNet classifier using dual-branch architecture with depth retention pooling achieved an accuracy of 72.6%, an area under receiver operating characteristic of 0.90, a sensitivity of 72.6%, a specificity of 86.3%, a positive predictive value of 74.1%, and a negative predictive value of 86.6% on all the test sets.

## Conclusions:

These results show the satisfactory performance of the deep learning classifier in predicting HGSBO compared to the previous machine learning model. The novel 3D classifier with dual-branch architecture and depth retention pooling based on artificial intelligence algorithms could be a reliable screening and decision-support tool for high-risk patients with SBO.

## Keywords:

## Introduction

Highlights

We built an artificial intelligence-based model with abdominal computed tomography images to help detect high-risk patients with acute small bowel obstruction (ASBO).

A 3D-convolutional neural network model detected high-risk ASBO patients with high accuracy and efficiency.

Artificial intelligence models can accurately detect high-risk ASBO patients, making them reliable screening and decision-support tools for high-risk patients with ASBO.

Acute small bowel obstruction (ASBO) is one of the most common acute abdominal diseases that may require urgent surgery. In emergent surgical cases, any delay in operation is known to be related to significant morbidity and mortality1. According to reports from the United States, ASBO accounts for 12–16% of surgical hospitalizations, amounting to 300 000 surgeries and $2.3 billion in medical costs annually2. The most common cause of acute intestinal obstruction is postoperative adhesion (70%), followed by cancer, inflammatory bowel disease, and hernias3,4. The pathophysiology of ASBO progresses from the onset of intestinal obstruction due to various causes, followed by the proximal dilatation of the bowel to the occluded area being deteriorated by the accumulation of fermented gas and shifted fluids5. Prolonged intestinal obstruction and distension can lead to hypovolemia and increased intramural pressure, leading to intestinal ischemia or necrosis. Ischemia and bowel wall dilatation weaken the intestinal barrier, increasing the risk of bowel perforation. This risk increases with clinical deterioration and the duration of unsuccessful medical treatment6.

Treatment options for ASBO vary considerably depending on pathophysiological progression. Emergency surgery is essential when an intestinal infarction or peritonitis is suspected. In addition, early surgery is required if intestinal ischemia worsens. However, in ~70% of cases, nonoperative management (NOM) is successful, and ~20% of patients who have undergone NOM will eventually undergo surgery owing to clinical deterioration1. Recently, abdominal computed tomography (CT) has been playing a critical role in predicting the failure of NOM treatment. Several papers have reported using abdominal CT for imaging findings and modeling7,8. However, despite abdominal CT’s crucial role in deciding ASBO surgical treatment, the radiologic findings that require surgery are only discovered by experienced radiologists, and the interobservation variation is relatively high9,10. Recently, artificial intelligence (AI) has been widely applied to various tasks in medical imaging, and AI can make predictions as accurately as professional human interpreters11,12. Most studies on ASBO and AI have been conducted using simple radiography. Furthermore, AI studies using abdominal CT are scarce, and recent ones depend on radiologists’ interpretations rather than AI-based approaches13. Although papers are reporting the use of AI in abdominal CT, several problems have been encountered. For example, a recent study conducted by Vanderbecq et al.14 successfully detected the transition zone of ASBO by CT, but it used only ASBO CT and not the normal CT. The study diagnosed several instances of ASBO from CT; however, the proposed method cannot classify between normal and abnormal instances because the study only used abnormal data. Previously, a pilot study was performed to determine whether an AI can distinguish between normal and ASBO X-ray images11. However, the imbalance between normal and abnormal data was significant, and the study used non-CT images. It is often clinically challenging to diagnose patients that are at risk of requiring emergency surgery. In addition, distinguishing high-risk cases, such as closed-loop obstructions or SBO by band adhesion, is a laborious and challenging task for radiologists and clinicians.

In recognition of these problems, this study aimed to establish a novel AI model that can effectively diagnose ASBO in normal subjects using only CT images and assist in the early diagnosis and identification of patients at risk of surgery.

## Methods

## Dataset

This study has been reported in accordance with the strengthening the reporting of cohort, cross-sectional, and case–control studies in surgery (STROCSS) standards15 (Supplemental Digital Content 1, http://links.lww.com/JS9/B23). This study was registered at cris.nih.go.kr. A single-center retrospective medical record study at a tertiary institution was designed for this diagnostic investigation. The ethical review board authorized this study. In accordance with the university’s requirements for retrospective analyses, informed consent was waived. The research was conducted in accordance with the Transparent Reporting of a Multivariable Prediction Model for Individual Prognosis or Diagnosis (TRIPOD)16 , the Checklist for Artificial Intelligence in Medical Imaging (CLAIM)17 and the Standards for Reporting of Diagnostic Accuracy Studies (STARD)18 (Supplemental Digital Content 2, http://links.lww.com/JS9/B24).

The following dataset refinement process was conducted to identify a high-risk group that may require emergency surgery for intestinal obstruction. The participants consisted of three groups, including the nonsurgical group: patients who visited the emergency department or were admitted to the hospital for ileus between 1 January 2000 and 31 December 2021; surgical group: patients who underwent lysis of adhesion for ASBO during the same period; and the normal subjects: healthy individuals without any abnormal abdominal CT findings during the health screenings in 2019. Their images were extracted after the anonymization process. The inclusion criteria were: 18 years and older, CT image findings with SBO, and mechanism of obstruction caused by the adhesion. Before this process, we identified normal subjects (n=1000) without any abnormal abdominal CT findings during the health screenings conducted in 2019. Since the cause and clinical aspects of intestinal obstruction are very heterogeneous, a detailed review of the case was required. Appendices 1 (Supplemental Digital Content 3, http://links.lww.com/JS9/B25) and 2 (Supplemental Digital Content 4, http://links.lww.com/JS9/B26) describe the exclusion cases during the refinement process. Exclusions were made because of nonadhesion mechanisms; other anatomical locations; or pathological conditions such as malignancy, peritonitis, and inflammatory bowel disease. In addition, cases with gastrografin use and postoperative ileus within one month were excluded. Overt ischemia and necrosis of the small bowel were also excluded. The patient’s demographics are described in Appendix 3 (Supplemental Digital Content 5, http://links.lww.com/JS9/B27). The surgical and nonsurgical groups were investigated to identify patients with high-risk intestinal obstruction. First, in the nonsurgical group, the ileus-related disease classification code (similar to the ICD code) was used. Cases for which abdominal CT images were unavailable and cases of nonadhesive ASBO were excluded. Cases of high-grade SBO (HGSBO) were accompanied by one of the closed-loop findings, adhesive bands, or complete or incomplete high-grade obstruction with abrupt luminal narrowing. In the case of low-grade SBO (LGSBO), it was determined that there was fluid-filled distension of the small bowel, accompanied by one of the following findings: a low possibility of obstruction or a low-grade or partial obstruction. In the surgical group, all patients who underwent abdominal surgery were investigated at the hospital. Cases were refined according to the criteria of adhesiolysis due to adhesive SBO. Finally, high-risk surgical findings, such as adhesive bands or closed loops, consistent with preoperative radiologic findings, such as high-grade obstruction or strangulation, were included in the final cohort. Figure 1 shows a flowchart of the above process. Thus, 209 HGSBO, 119 LGSBO, and 250 normal cases were obtained. The dataset was divided into 462 training sets and 116 test sets to build the model, and fivefold cross-validation was performed.

Patient selection process. CT, computed tomography; HGSBO, high-grade small bowel obstruction; LGSBO, low-grade small bowel obstruction.

## Development and training of AI system

3D image classification is widely used in the medical field. Some works19–23 have used 3D-convolutional neural networks (CNN) for classifying Alzheimer’s disease. Other studies24–26 have used 3D image classification for brain diseases. However, little research has been done on using 3D image classification to distinguish ASBO cases.

The proposed network aims to distinguish between CT images of normal cases, cases of HGSBO that require emergency surgery, and cases of LGSBO or paralytic ileus. HGSBO and LGSBO are clinically distinct because a delay in surgical intervention in the case of HGSBO is known to increase the risk of morbidity and mortality, particularly in older patients1,27; however, the CT images for both appear similar. Therefore, it is challenging to classify HGSBO and LGSBO on CT images using a simple network structure. Thus, we propose two approaches for the classification method: dual-branch architecture (DBA) and depth retention pooling. For DBA, to enrich the class information of HGSBO and LGSBO, we trained the features by learning the base classifier and finer classifier simultaneously; this was to enrich the class information of HGSBO and LGSBO. In the second approach, we preserved the depth information in the last feature map to intensify the subtle information in CT images. Our networks based on these approaches effectively distinguish all three class labels: normal, HGSBO, and LGSBO. A detailed description of the proposed network is presented in the following subsections.

## DBA

Suppose the architecture simply uses a normal three-label classifier as the last fully connected (FC) layer. In that case, it cannot distinguish HGSBO from LGSBO, and it cannot properly learn the conflicting characteristics. Some networks are split into branches to improve 

……（全文较长，此处截取前 12000 字符）