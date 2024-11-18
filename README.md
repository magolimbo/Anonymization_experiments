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
The system also reacts remarkably well to a black face mask, delivering compelling performance up to 90% opacity of the mask. It’s noteworthy that a small mask at 100% opacity
just on the eye area significantly degrades the model.

![image](https://github.com/user-attachments/assets/d9e2978f-0fb8-4895-b766-8a95d1ebcbd6)

To understand if such masks, as well
as other filters, are adequate for rendering the face unrecognizable, we consider the EER point with a decision threshold of 0.2398. At this
threshold, the rates of FMR and FNMR are identical, indicating a balance point in error
trade-offs. Figure below shows the trend of average mated comparisons for each filter as the filter intensity
varies. 

![image](https://github.com/user-attachments/assets/42e5dc0f-12bb-4847-86d4-9302adf2b459)

Our plots exhibit characteristics reminiscent of an e−x shape for Gaussian blur and median blur, while pixelization and black mask display an inverse −ex profile, suggesting
a greater robustness of the model to the application of pixelization and black mask.
It is interesting to note how at intensity 40, the average correlation for pixelization anoma-
lously increases compared to intensity 30, before resuming the negative trend from in-
tensity 50 onwards. This could be due to the moderate application of a pixelization filter
reducing noise in the images, temporarily enhancing the average correlation. Alternatively,
the pixelization filter may interact specifically with image features, accentuating or atten-
uating certain details or patterns that influence the average correlation.
It is also important to highlight how applying a black mask filter only over the eyes at
100%, as indicated by the red dot in Figure 8.d, is insufficient at the chosen decision
threshold to anonymize the face, demonstrating the robustness of MagFace.
The following table shows the values of the intensities for the different filters where the
recognition system is more likely to fail to recognize the original face at the EER point,
with an accuracy of 94.03%. An example of corresponding images with the filters applied
is shown in the Figure below

![image](https://github.com/user-attachments/assets/24d1e257-00fd-4e05-9deb-350d506770f9)



