# Proposal

## Proposal Title
**Development of NephroXNet for Explainable Four-Class Kidney CT Classification (Cyst/Normal/Stone/Tumor) and Comparative Analysis**

## Abstract
Kidney findings are common in clinical practice.
CT supports kidney diagnosis and follow up.
Low dose CT is also important for follow up.
Clinicians need models they can trust.
Explainability supports trust.

This proposal uses a public kidney CT dataset from IEEE DataPort.
It is a four class dataset.
The goal is a new Keras model named NephroXNet.
NephroXNet starts from EfficientNet B4 features.
NephroXNet is not a plain EfficientNet baseline.

The workflow has four parts.
Part one is data curation and normalization.
Part one includes augmentation.
Part one includes class aware sampling.
The stone class is the smallest class.

Part two is model design.
NephroXNet uses dual attention.
It uses channel attention.
It uses spatial attention.
It uses multi scale feature fusion.

Part three is benchmarking.
Baselines include ResNet50.
Baselines include DenseNet121.
Baselines include InceptionV3.
Baselines include Xception.
Baselines include MobileNetV2.
Baselines include EfficientNetB0.
Baselines include EfficientNetB4.

Part four is explainability.
Explanations use Grad CAM plus plus.
Explanations use layer wise relevance propagation.
Explanations use attention map visualizations.
Faithfulness uses a masking test.
The test measures confidence drop.

The expected outcome is a robust classifier.
The outcome includes clear per class results.
Extra focus is on the stone class.

## Keywords
Kidney CT classification
Cyst
Normal
Stone
Tumor
Explainable AI
Attention mechanism
NephroXNet
Keras
Transfer learning
Medical image classification
Multi class diagnosis

## Background and motivation
Stone disease has a high recurrence rate.
It often leads to acute pain and urgent care.
Radiologists also encounter cysts and tumors.
CT remains a reliable imaging tool.
Repeated CT raises dose concerns.
Noise can also increase in low dose settings.
Workload is also a challenge in practice.
Automation can support clinical workflows.

Prior work improves parts of this problem.
Some work focuses on low dose CT reconstruction.
Some work focuses on denoising.
Some work focuses on stone detection in X ray.
Some work focuses on stone segmentation.
Some work focuses on data efficient training.
Some work focuses on kidney disease classification.
Some work focuses on kidney tumor segmentation.

A gap remains for an integrated pipeline.
The gap includes a four class CT task.
The gap includes a modified EfficientNet B4 model.
The gap includes dual attention.
The gap includes explainability outputs.
The gap includes broad comparisons.

This proposal addresses that gap.
It keeps the full four class setting.
Stone is clinically important.
Stone is also the minority class.
Imbalance can bias standard training.
The design must address this risk.

Trust is another motivation.
Black box predictions reduce acceptance.
Visual evidence can support clinical review.
This proposal treats explainability as a core goal.

## Problem statement
Many pipelines output only a label and a confidence score.
Explainability outputs are often missing.
Class imbalance can reduce per class performance.
This is most critical for the stone class.
This project targets accuracy and interpretability in one system.

## Main objective
Develop an explainable four class kidney CT classification system.
Improve overall accuracy.
Improve per class performance.
Prioritize improvement for the stone class.
Provide clinically readable explanation maps.
Validate results against strong Keras baselines.

## Specific objectives
1. Design NephroXNet using EfficientNet B4 features.
2. Add dual attention and multi scale fusion.
3. Improve per class performance under imbalance.
4. Compare against standard Keras backbones.
5. Add explainability with multiple methods.
6. Run ablations to verify each component.

## Literature review
### Clinical and imaging context
Recent work highlights low dose CT reconstruction for stones.
Recent work shows deep learning denoising for urolithiasis.
Reviews also note growth of AI in renal imaging.
CT remains important for structural assessment.
Data scarcity is common in clinical settings.

### Kidney stone and kidney disease modeling
Some studies use explainable classification for stone identification.
Many are binary tasks.
Some studies focus on segmentation with special handling for small stones.
Other studies address broader kidney disease categories.
Segmentation studies also support EfficientNet style backbones.

### Attention mechanisms and backbone design
Attention improves feature refinement in medical imaging.
Channel attention highlights informative filters.
Spatial attention highlights relevant regions.
Fusion heads can support better localization behavior.
These ideas motivate NephroXNet design choices.

### Explainable AI in medical imaging
XAI reviews stress the need for trust.
Saliency methods can be useful but need careful interpretation.
Using more than one method improves confidence in explanations.

### Research gap
Kidney stone papers often focus on binary detection.
Renal CT papers often focus on segmentation tasks.
Few studies combine four class CT learning with attention and XAI.
This proposal targets that combined setting.

## Aims and expected contributions
NephroXNet is a named architecture.
It targets a four class setting.
It reports clear per class metrics.
It includes a strong baseline protocol.
It includes a clinically readable XAI workflow.
It supports a paper ready experimental plan.

## Dataset description
The study uses an IEEE DataPort dataset.
It is published in 2024.
The dataset includes four kidney CT categories.

Task.
Four class image classification.

Labels.
Cyst.
Normal.
Stone.
Tumor.

Size.
Total images are 12446.
Cyst images are 3709.
Normal images are 5077.
Stone images are 1377.
Tumor images are 2283.

Data type.
Kidney CT images.
Inputs are resized pixel values.
Inputs are normalized pixel values.

Why it fits.
It supports a clinically meaningful setting.
It includes realistic class imbalance.
It stresses evaluation for the stone class.

## Tools and technologies
Python.
TensorFlow and Keras.
NumPy.
Pandas.
Scikit learn.
OpenCV or Pillow.
Matplotlib.

## Research plan and methodology
### Phase 1 Dataset preparation
Use a stratified split.
Check integrity.
Screen for duplicates.
Verify class counts.
Resize images for EfficientNet B4.
Normalize intensities.
Consider contrast enhancement after pilot inspection.
Create train validation test splits.

Prefer subject wise splitting if identifiers exist.
If not then use image wise splitting.
Add leakage checks.
Use five fold stratified cross validation for model selection.

Handle imbalance during training.
Use class weights.
Use balanced sampling.
Use targeted augmentation.
Track per class metrics.

### Phase 2 Proposed model design
NephroXNet is the core model.
It starts from EfficientNet B4 as a feature extractor.
Remove the top classification layers.
Tap intermediate feature maps.
Apply attention to each selected map.
Fuse multi scale features.
Use global pooling.
Use dropout.
Use dense layers.
Use a four class softmax output.

Why the design fits.
EfficientNet style backbones are efficient.
Attention supports what and where information.
Fusion can support better localization behavior.

### Phase 3 Explainable AI module
Explainability is part of the method.
Use Grad CAM plus plus.
Use layer wise relevance propagation.
Use attention heatmaps.
Run a masking test.
Measure confidence drop after masking salient regions.

### Phase 4 Comparative baselines
Train baselines under the same split and preprocessing.
Use MobileNetV2.
Use ResNet50.
Use DenseNet121.
Use InceptionV3.
Use Xception.
Use EfficientNetB0.
Use EfficientNetB4.

Also compare to ideas from recent journals.
Focus on stone classification and XAI.
Focus on segmentation with imbalance handling.
Focus on data efficient CT training.
Focus on attention driven medical imaging models.

### Phase 5 Training strategy and ablation study
Use transfer learning.
Fine tune in stages.
Use learning rate scheduling.
Use early stopping.
Use regularization.
Use dropout.
Use class weighting.

Run ablations.
1. NephroXNet without attention.
2. NephroXNet with channel attention only.
3. NephroXNet with spatial attention only.
4. NephroXNet with and without class weighting.

### Phase 6 Evaluation protocol
Report overall accuracy.
Report macro precision.
Report macro recall.
Report macro F1 score.
Report one vs rest ROC AUC.
Report a confusion matrix.
Report balanced accuracy.
Report Matthews correlation coefficient.

Report per class metrics.
Report sensitivity for each class.
Report specificity for each class.
Report precision for each class.
Report F1 score for each class.

Focus on stone errors.
Review stone false negatives.
Review common confusions.

Evaluate explanations.
Compare Grad CAM and LRP and attention maps.
Report confidence drop under masking.
Discuss correct cases.
Discuss incorrect cases.

## Expected outcomes
A trained NephroXNet model.
Baseline benchmark results.
Improved macro averaged performance.
Strong stone class analysis.
Explainability examples with faithfulness checks.
A manuscript ready methods and results narrative.

## Workflow figure
The workflow diagram is provided as an SVG file.
File name is kidney stone workflow svg.

Proposed workflow image file is kidney stone workflow svg.

## Conclusions
This proposal targets explainable kidney CT classification.
It covers four renal classes.
It aims for strong per class results.
It includes a new model named NephroXNet.
It uses attention and multi scale fusion.
It includes explainability outputs.
It includes baseline comparisons.
It includes careful evaluation under imbalance.

## References
[1] J. Chaki, “Kidney tumor,” IEEE DataPort. Aug. 30, 2024. doi: 10.21227/646s-6y35.

[2] S. Prod’homme, R. Bouzerar, T. Forzini, A. Delabie, and C. Renard, “Detection of urinary
tract stones on submillisievert abdominopelvic CT imaging with deep-learning image
reconstruction algorithm (DLIR),” Abdominal Radiology, vol. 49, no. 6, pp. 1987–1995,
Mar. 2024, doi: 10.1007/s00261-024-04223-w.

[3] R. Terzis et al., “Deep-Learning-Based Image denoising in Imaging of Urolithiasis:
Assessment of image quality and comparison to State-of-the-Art iterative reconstructions,”
Diagnostics, vol. 13, no. 17, p. 2821, Aug. 2023, doi: 10.3390/diagnostics13172821.

[4] F. Ahmed et al., “Identification of kidney stones in KUB X-ray images using VGG16
empowered with explainable artificial intelligence,” Scientific Reports, vol. 14, no. 1, p.
6173, Mar. 2024, doi: 10.1038/s41598-024-56478-4.

[5] W. Preedanan et al., “Urinary stones segmentation in abdominal X-Ray images using
cascaded U-Net pipeline with Stone-Embedding augmentation and Lesion-Size
reweighting approach,” IEEE Access, vol. 11, pp. 25702–25712, Jan. 2023, doi:
10.1109/access.2023.3257049.

[6] J.-S. Kim and S.-J. Eun, “Data-Efficient Deep Learning Framework for Urolithiasis
Detection using Transfer and Self-Supervised Learning,” International Neurourology
Journal, vol. 29, no. Suppl 2, pp. S90–S94, Nov. 2025, doi: 10.5213/inj.2550292.146.

[7] M. N. Hossain, E. Bhuiyan, M. B. A. Miah, T. A. Sifat, Z. Muhammad, and M. F. A. Masud,
“Detection and Classification of Kidney Disease from CT Images: An Automated Deep
Learning Approach,” Technologies, vol. 13, no. 11, p. 508, Nov. 2025, doi:
10.3390/technologies13110508.

[8] A. Abdelrahman and S. Viriri, “EfficientNet family U-Net models for deep learning
semantic segmentation of kidney tumors on CT images,” Frontiers in Computer Science,
vol. 5, Sep. 2023, doi: 10.3389/fcomp.2023.1235622.

[9] M. Alruwaili, M. A. Mahmood, and M. K. Elbashir, “Dual-Attention EfficientNet Hybrid
U-Net for segmentation of rheumatoid arthritis hand X-Rays,” Diagnostics, vol. 15, no. 24,
p. 3105, Dec. 2025, doi: 10.3390/diagnostics15243105.

[10] I. Das et al., “Improving medical X-Ray imaging diagnosis with attention mechanisms
and robust transfer learning techniques,” IEEE Access, vol. 13, pp. 159002–159027, Jan.
2025, doi: 10.1109/access.2025.3607639.

[11] D. Agarwal, M. Á. Berbís, A. Luna, V. Lipari, J. B. Ballester, and I. De La Torre-Díez,
“Automated Medical Diagnosis of Alzheimer´s Disease Using an Efficient Net
Convolutional Neural Network,” Journal of Medical Systems, vol. 47, no. 1, p. 57, May
2023, doi: 10.1007/s10916-023-01941-4.

[12] N. S. Shaik, N. Veeranjaneulu, and J. D. Bodapati, “Adaptive Fusion Attention for
enhanced classification and interpretability in medical imaging,” Machine Vision and
Applications, vol. 36, no. 3, Mar. 2025, doi: 10.1007/s00138-025-01665-0.

[13] S. Yin et al., “Brain CT image classification based on mask RCNN and attention
mechanism,” Scientific Reports, vol. 14, no. 1, p. 29300, Nov. 2024, doi: 10.1038/s41598-
024-78566-1.

[14] B. M. De Vries, G. J. C. Zwezerijnen, G. L. Burchell, F. H. P. Van Velden, C. W. M.-
V. D. H. Van Oordt, and R. Boellaard, “Explainable artificial intelligence (XAI) in
radiology and nuclear medicine: a literature review,” Frontiers in Medicine, vol. 10, p.
1180773, May 2023, doi: 10.3389/fmed.2023.1180773.

[15] K. Borys et al., “Explainable AI in medical imaging: An overview for clinical
practitioners – Beyond saliency-based XAI approaches,” European Journal of Radiology,
vol. 162, p. 110786, Mar. 2023, doi: 10.1016/j.ejrad.2023.110786.

[16] D. Bhati, F. Neha, and M. Amiruzzaman, “A survey on Explainable Artificial
intelligence (XAI) techniques for visualizing deep learning models in medical imaging,”
Journal of Imaging, vol. 10, no. 10, p. 239, Sep. 2024, doi: 10.3390/jimaging10100239.

[17] K. Raghavan, S. B, and K. V, “Attention guided grad-CAM : an improved explainable
artificial intelligence model for infrared breast cancer detection,” Multimedia Tools and
Applications, vol. 83, no. 19, pp. 57551–57578, Dec. 2023, doi: 10.1007/s11042-023-
17776-7.

[18] D. Mukhtorov, M. Rakhmonova, S. Muksimova, and Y.-I. Cho, “Endoscopic image
classification based on explainable deep learning,” Sensors, vol. 23, no. 6, p. 3176, Mar.
2023, doi: 10.3390/s23063176.

[19] F. Ahmed, N. S. Naz, S. Khan, A. U. Rehman, W. M. Ismael, and M. A. Khan,
“Explainable artificial intelligence (XAI) in medical imaging: a systematic review of
techniques, applications, and challenges,” BMC Medical Imaging, vol. 26, no. 1, p. 37, Jan.
2026, doi: 10.1186/s12880-025-02118-w.

[20] T. Xu et al., “A narrative review on the application of artificial intelligence in renal
ultrasound,” Frontiers in Oncology, vol. 13, p. 1252630, Mar. 2024, doi:
10.3389/fonc.2023.1252630.