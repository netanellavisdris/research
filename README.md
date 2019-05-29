# research
Research management with papers


 
# Segmentation

## Semi-supervised


# Medical

## Fetal growth

### Garel
### Kyrkyapodoulu

# Reconstruction 

## 2D to 3D

### Fast motion compensation and super-resolution from multiple stacks of 2D slices [code](https://github.com/bkainz/fetalReconstruction) [paper](https://github.com/bkainz/fetalReconstruction/blob/master)
In test

### Slice-to-Volume Registration Network (SVRnet) [code](https://github.com/farrell236/SVRnet) [paper](https://ieeexplore.ieee.org/abstract/document/8295121/)
For me, There is need for dataset (They use iFind) So I will try to reconstruct one from equivoxel T2 (Preterm) and resample.

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

