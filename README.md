## Evaluating the Impact of Traditional Anonymization Filters on State-of-the-Art Facial Recognition Performance
*The full report can be found in the root folder*

### Project Overview
This repository contains the code and resources for the final project of the MSc course Biometric Systems - 02238 at DTU. The project investigates how traditional anonymization techniques (Gaussian blur, Median blur, Pixelization, and Black Bands) affect the performance of MagFace, a state-of-the-art facial recognition model. The study leverages a subset of the **CelebA dataset** to assess the impact of various filters on recognition accuracy, contributing to a better understanding of privacy-preserving techniques in digital and surveillance environments.

![image](https://github.com/user-attachments/assets/bca4ed00-4696-4bc8-b463-e3c8b08850d5)
*Example of filter applied to the pictures. In this case, a face masking filter is applied to the face with various opacity levels*


### Results
After applying filters at various intensities to the original photos, the DET curves were plotted to analyze the degradation of system performance.
As visible in the Figure below, increasing the filter intensity linearly results in linear degradation of model performance for blur filters, both Gaussian and median, with the latter appearing more impactful on system performance and thus more effective from an anonymization
standpoint. It is also interesting to observe in pixelization how well the recognition model responds to
anonymization, with its performance minimally affected by the presence of a filter. Only at
high pixelization intensities (level 6 and beyond), FMR and FNMR increase significantly.
The system also reacts remarkably well to a black face mask, delivering compelling perfor-
mance up to 90% opacity of the mask. It’s noteworthy that a small mask at 100% opacity
just on the eye area significantly degrades the model.

![image](https://github.com/user-attachments/assets/d9e2978f-0fb8-4895-b766-8a95d1ebcbd6)

To understand if such masks, as well
as other filters, are adequate for rendering the face unrecognizable, we consider the previ-
ously found EER point with a decision threshold of 0.2398. As mentioned earlier, at this
threshold, the rates of FMR and FNMR are identical, indicating a balance point in error
trade-offs. Figure 8 shows the trend of average mated comparisons for each filter as the filter intensity
varies. Our plots exhibit characteristics reminiscent of an e−x shape for Gaussian blur and


