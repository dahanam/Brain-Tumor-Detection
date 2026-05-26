Brain Tumor Detection
Deep learning models for binary classification of brain MRI scans — detecting the presence or absence of a tumor. Five model architectures are compared, with accuracy ranging from 75% to 90%.
Presented at the 35th GMIS Conference (CAHSI), Kean University.

Models
ModelFrameworkNotesVGG-16Keras/TFTransfer learning with brain crop preprocessingVGG-19Keras/TFDeeper architecture; higher overfitting risk on small datasetsResNet-50Keras/TFSkip connections; strong generalizationEfficientNetB3TensorFlowMost parameter-efficientCustom CNNKeras/TFHigh-level API baseline
Testing accuracy ranged from 75% to 90% across all models.

Dataset
Brain MRI Images for Brain Tumor Detection — Kaggle
Two classes: yes (tumor present) · no (no tumor)
Dataset: Kaggle — Brain MRI Images for Brain Tumor Detection

Notebook
brain_tumor_detection.ipynb — all 5 approaches in one merged notebook.
SectionDescription1. SetupInstalls, Drive mount, imports2. Load & ExploreSample MRI grid, class counts3. PreprocessingBrain crop pipeline with step-by-step visualization4. Shared UtilitiesConfusion matrix and training curve helpers5. VGG-16With augmentation and early stopping6. VGG-19Pretrained ImageNet weights7. ResNet-50Pretrained ImageNet weights8. EfficientNetB3Categorical mode, Adamax optimizer9. Custom CNN (PyTorch)5-block grayscale architecture10. InferenceSingle image prediction with confidence score11. Results SummaryCross-model comparison

Preprocessing
MRI images are cropped to remove empty border space using contour detection before being fed into any model:

Convert to grayscale and apply Gaussian blur
Threshold + erode/dilate to remove noise
Find the largest contour (the brain)
Crop to the extreme points of that contour

This consistently improves model focus on relevant tissue.

Setup

Open brain_tumor_detection.ipynb in Google Colab
Place dataset at /content/drive/MyDrive/BTD_Notebook/brain_tumor_dataset/
Run all cells top to bottom

Note: .h5 and .pth model weight files are not included in this repo due to file size. They are saved locally when you run the notebook.

Tech Stack
Python · TensorFlow · Keras · PyTorch · scikit-learn · OpenCV · Google Colab

References

Brain MRI Dataset — Kaggle
Keras Applications
Keras Pretrained Models — Kaggle
ShareContentpdfpdfctf_challenge_assistant.ipynbipynbPredictingPetPawpularityfromImagesUsingDeepLearning.ipynbipynbchat.pypychatbox.pypycharts.pypyCPS5745_mozruizd_tar.gzgzpdfCPS4801_AI_Final_Project_1_2.ipynbipynbCPS4801_AI_Final_Project2_2.ipynbipynbCopy_of_Kuan_Copy_of_YK_Copy_of_Cyber_project.ipynbipynbCyberbullying_6classes.ipynbipynbCyberbullying_prompt_engineering.ipynbipynbYK_Copy_of_Cyber_project.ipynbipynbPytorch.ipynbipynbVGG19+ResNet50.ipynbipynb[og]VGG-16.ipynbipynbBTDEffNET.h5h5CNNCNN_model.h5h5Copy of BTD__ CNN, VGG-16.ipynbipynbefficientnetb0_notop.h5h5EffiecientNet.ipynbipynbpdfHere is a summary you can paste into a new chat:

---

**Project:** Cougar Pathway to Success, Kean University CS/IT Department. NSF-funded (Awards #1928452, #2129795, #2345334) + Sloan Foundation. Lead author: Dahana Moz Ruiz.

**Paper:** ACM journal paper titled "Pathways to Undergraduate Success pastedchatbox2.py297 linespyactivityimpacts.py228 linespydemo_race.py73 linespysweetspot.py71 linespyval.py117 linespyregression.py212 linespy# Cougar Pathway to Success — Data Analysis & Visualization

Python analysis and visualization scripts for a longitudinal study of 
undergraduate student success in CS/IT at Kean University. This codebase 
produced the figures, statistics, and regression analysis for a paper 
currently in-progress tpastedexcerpt_from_previous_claude_message.txt7 linestxtproj_queries.sql96 linessqlcharts.js341 linesjsdbconfig.php13 linesphpget_corr_chart.php115 linesphpget_monthly_chart.php58 linesphpget_settings.php32 linesphpget_tickers.php15 linesphpindex.php108 linesphplogin.html66 lineshtmllogin.php46 linesphplogout.php6 linesphpmerge.py131 linespysave_settings.php29 linesphpstyles.css282 linescssexcerpt_from_previous_claude_message.txt2 linestxt
