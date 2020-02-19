# research
Research management with papers


 
# Deep learning

## Transfer learning

### MED3D: TRANSFER LEARNING FOR 3D MEDICAL IMAGE ANALYSIS [paper](https://arxiv.org/pdf/1904.00625.pdf) [code](https://github.com/Tencent/MedicalNet)
Tencent's pretrain model for medical image analysis, trained and tested on segmentation challanges, but pretrained on Medical data only.
seems promising, need to check.
## Semi-supervised

### MixMatch: A Holistic Approach to Semi-Supervised Learning [paper](https://arxiv.org/pdf/1905.02249.pdf) [code](https://github.com/google-research/mixmatch)
Learning from minimal labeled + large unlabeled data by using aumentation and sharpening - seems intersting to segmentation variant - Need to try!

## Uncertanty estimation and lack of Ground truth

### Simultaneous Truth and Performance Level Estimation (STAPLE): An Algorithm for the Validation of Image Segmentation [paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1283110/) [code1](https://www.mathworks.com/matlabcentral/fileexchange/56789-staple-d) [code-orig](http://crl.med.harvard.edu/software/STAPLE/request_access.php)
Using EM variant alogorithm for estimation of GT with varirty of segmentations (/algorithms).
The algorithm generates simultanously (M-step) Probablistic map of segmentation and then evaluate(E-step) the given segmentations vs the map. with extension to multiclass segmentation(partD) and global features(partE).
Note that the algorithm assumes pixels are iid so no matter 2D or 3D.
evalutaion was done on brain MRI and prostate MRI.
[extension algorithm links](https://www.researchgate.net/publication/228454733_A_Tutorial_Introduction_to_STAPLE/download)


## Landmarks

### Adaloss: Adaptive Loss Function for Landmark Localization [paper](https://arxiv.org/pdf/1908.01070v1.pdf)
Train landmark detector that increase the accuracy ( by reducing SDof gaussion for landmark detection) in train time adaptive to each class. Currently State-of-the-art in Face landmark detection (AFLW,300W)

### Style Aggregated Network for Facial Landmark Detection [paper](http://openaccess.thecvf.com/content_cvpr_2018/papers/Dong_Style_Aggregated_Network_CVPR_2018_paper.pdf)[code](https://github.com/D-X-Y/landmark-detection)

previous StoA, addressing style varaiations of face landmark by CycleGAN generation, may be useful for robustness.

# General Vision

## Symmetry

### PRST - A Planar-Refective Symmetry Transform for 3D Shapes  [paper](https://gfx.cs.princeton.edu/pubs/Podolak_2006_APS/symmpaper.pdf) [code](https://github.com/cmusatyalab/dermshare/blob/master/gemini/gemini/prst.py)

Symmetry line(s) detection - Doesnt seems to work on 2D or I did not understand the output (R/theta?)

### Loy-Eklundh - Detecting Symmetry and Symmetric Constellations of Features [paper](http://www.cse.psu.edu/~yul11/CourseFall2006_files/loy_eccv2006.pdf) [code](https://github.com/dramenti/symmetry)

Symmetry line detection.
Seems to work with Seg * Image on our data.


# Medica

## Fetal growth

### Cerebral biometry in fetal magnetic resonance imaging: new reference data (*Garel*) [paper](https://www.ncbi.nlm.nih.gov/pubmed/19172662)
Reference data for MRI biometry. 

### Prenatal Brain MR Imaging: Reference Linear Biometric Centiles between 20 and 24 Gestational Weeks [paper](http://www.ajnr.org/content/early/2018/03/08/ajnr.A5574)
Also have Bland-Altman plots  and tables with numerical values for intra-doctor aggreement on linear measurement for fetuses (20-24).

### Normative biometry of the fetal brain using magnetic resonance imaging(*Kyrkyapodoulu*) [paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5504265/)
Explanataion of how we need to measure bometrics and reference excel with cacluations

### Accuracy of transverse cerebellar diameter measurement by ultrasonography in the evaluation of foetal age [paper](https://pdfs.semanticscholar.org/3ccd/f3d47a42c5fd401e843debda9c41e6ee9c56.pdf)
Shows that TCD is better predictor than other linear mesurement for IUGR. Note that this done on US (which have more noise than MRI) but may (and we can see it by the variance) be true also for MRI.
The foetal typo is original.

## Brain age estimation

### Assessment of MRI-Based Automated Fetal Cerebral Cortical Folding Measures in Prediction of Gestational Age in the Third Trimester[paper](http://www.ajnr.org/content/ajnr/early/2015/06/04/ajnr.A4357.full.pdf)
Estimation of brain age using volume and cortical folding (sulcuses). evaluate 8 types of measuring sulcuses and take the best fit. take care that they didnt have a lot of data but still they got 98% R-square.

### Deep Learning with Attention to Predict Gestational Age of the Fetal Brain [paper](https://arxiv.org/pdf/1812.07102.pdf)
Using Unet+Attention on brain to estimate GA. Private DB of ~700 fetuses and straightforward(Medical) approach.
By using multi-view(Cor+Ax+Sag) they got better result.

## Brain symmetry

### A NEW SYMMETRY-BASED METHOD FOR MID-SAGITTAL PLANE EXTRACTION IN NEUROIMAGES [paper](http://www.chenpingyu.org/docs/2011ruppert1.pdf) [code](http://www.chenpingyu.org/media/mspExtraction.zip) - Take cre , only exe
Find mis dagittal plane (MSP) in T1 brain images automatically, by using symetry-to-plane. 
caluclating symmetry by correletaion between images in two side of plane and minimizing.

### An Efficient Automatic Midsagittal Plane Extraction in Brain MRI [paper](https://www.mdpi.com/2076-3417/8/11/2203/pdf)
Faster(1s for 3D) and geometric, still need to understand how it works

## Agreement statistics

### An Overview on Assessing Agreement with Continuous Measurements [paper](https://www.tandfonline.com/doi/full/10.1080/10543400701376480?casa_token=-2YXZJIOGfgAAAAA:v9l3Yn40UUcoSDpOwUramFdCfhG1lBYhRnhpUSId_qDDB1Wmue247k3DnZMWAY6i8n-l-9TaqwgNRNA)
Overview

### A graphical method for assessing agreement with the mean between multiple observers using continuous measures  [paper](https://academic.oup.com/ije/article/40/5/1308/658431)
Estimator for inter-observer variability for more than 2 observers, take care that is is not exactly as Balnd-Altman results.
# Reconstruction 

## 2D to 3D

### Fast motion compensation and super-resolution from multiple stacks of 2D slices (PVR) [code](https://github.com/bkainz/fetalReconstruction) [paper](https://core.ac.uk/download/pdf/96762437.pdf)
In test, The code does not work on my GPU  (CUDA Error in patchBasedPSFReconstructionKernel(), line 132: too many resources requested for launch)

### Slice-to-Volume Registration Network (SVRnet) [code](https://github.com/farrell236/SVRnet) [paper](https://ieeexplore.ieee.org/abstract/document/8295121/)
For me, There is need for dataset (They use iFind) So I will try to reconstruct one from equivoxel T2 (Preterm) and resample.

### Robust Super-resolution Volume Reconstruction from Slice Acquisitions: Application to Fetal Brain MRI [paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3694441/)

Simon's paper - still trying to find it's code.

### Slice-to-volume medical image registration: a survey [paper](https://arxiv.org/pdf/1702.01636.pdf)
Need to move over it again

### An automated framework for localization, segmentation and super-resolution reconstruction of fetal brain MRI [paper](https://www.sciencedirect.com/science/article/pii/S1053811919309152) [code](https://github.com/gift-surg/NiftyMIC)

Full pipeline of localization and reconstruction for fetal, trained on SSFSE. seems promising.


## Super resolution from KSpace 

### Learning-Based Compressive MRI [paper](https://infoscience.epfl.ch/record/255182/files/Learning-Based%20Compressive%20MRI.pdf)
Learning of sampling pattern and reconstruction algorithm for MRI simultaneously. 4-fold,  1D/2D sampling.

### Adversarial and Perceptual Refinement for Compressed Sensing MRI Reconstruction [paper](https://arxiv.org/pdf/1806.11216.pdf) [code]()
Using cascaded CNN and GAN for perceptual refinement for heart MRI. 3 to 9 fold, 1D variable density sampling.
Shows that SNR doesn’t necessarily correlate with image quality and radiological interpretability.

 * We try to run this code and the results wasnt good - need to understand why.

### Deep Learning Based Multi-Modal Fusion for Fast MR Reconstruction [paper](https://ieeexplore.ieee.org/abstract/document/8552399)
close idea, but for T1+ Undersampled T2 -> T2. 
take care that T2 has higher SNR than FLAIR inherently.

# Datasets
## Brain
* Brats2018 - Brain Lesion Segmenation - HGG and LGG [Link](https://www.med.upenn.edu/sbia/brats2018/data.html) [v]

   Constrast : T1, T1Gd, T2, FLAIR   
   Mode : Preprocessed  
   Type : MHA(?)  
   Count : 210 HGG + 75 LGG = 285 Patients, No control  
   Annotations : Lesions - split to components  


* ABIDE [v]
   Constrast : T1-MPRAGE  
   Count : 1109  
   Type : NiFTi  
[Place]
*
* 
## RAW
* FastMRI - Knee [x]


## Sequences 
| GE | Siemens | Philips  |
| --- | ----- | ----- |
| ssFSE | HASTE | |
| FIESTA | TruFI | |

