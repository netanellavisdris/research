# research
Research management with papers


 
# Segmentation

## Semi-supervised

### MixMatch: A Holistic Approach to Semi-Supervised Learning [paper](https://arxiv.org/pdf/1905.02249.pdf) [code](https://github.com/google-research/mixmatch)
Learning from minimal labeled + large unlabeled data by using aumentation and sharpening - seems intersting to segmentation variant - Need to try!

# Medical

## Fetal growth

### Cerebral biometry in fetal magnetic resonance imaging: new reference data (*Garel*) [paper](https://www.ncbi.nlm.nih.gov/pubmed/19172662)
Reference data for MRI biometry. 

### Prenatal Brain MR Imaging: Reference Linear Biometric Centiles between 20 and 24 Gestational Weeks [paper](http://www.ajnr.org/content/early/2018/03/08/ajnr.A5574)
Also have Bland-Altman plots  and tables with numerical values for intra-doctor aggreement on linear measurement for fetuses (20-24).

### Normative biometry of the fetal brain using magnetic resonance imaging(*Kyrkyapodoulu*) [paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5504265/)
Explanataion of how we need to measure bometrics and reference excel with cacluations

## Brain age estimation

### Assessment of MRI-Based Automated Fetal Cerebral Cortical Folding Measures in Prediction of Gestational Age in the Third Trimester[paper](http://www.ajnr.org/content/ajnr/early/2015/06/04/ajnr.A4357.full.pdf)
Estimation of brain age using volume and cortical folding (sulcuses). evaluate 8 types of measuring sulcuses and take the best fit. take care that they didnt have a lot of data but still they got 98% R-square.

### Deep Learning with Attention to Predict Gestational Age of the Fetal Brain [paper](https://arxiv.org/pdf/1812.07102.pdf)
Using Unet+Attention on brain to estimate GA. Private DB of ~700 fetuses and straightforward(Medical) approach.
By using multi-view(Cor+Ax+Sag) they got better result.

# Reconstruction 

## 2D to 3D

### Fast motion compensation and super-resolution from multiple stacks of 2D slices (PVR) [code](https://github.com/bkainz/fetalReconstruction) [paper](https://core.ac.uk/download/pdf/96762437.pdf)
In test

### Slice-to-Volume Registration Network (SVRnet) [code](https://github.com/farrell236/SVRnet) [paper](https://ieeexplore.ieee.org/abstract/document/8295121/)
For me, There is need for dataset (They use iFind) So I will try to reconstruct one from equivoxel T2 (Preterm) and resample.

### Slice-to-volume medical image registration: a survey [paper](https://arxiv.org/pdf/1702.01636.pdf)
Need to move over it again


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



