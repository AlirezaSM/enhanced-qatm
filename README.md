# Enhanced QATM for Template Matching

This project aims to improve the [Quality-Aware Template Matching (QATM)](https://openaccess.thecvf.com/content_CVPR_2019/html/Cheng_QATM_Quality-Aware_Template_Matching_for_Deep_Learning_CVPR_2019_paper.html) method by incorporating ideas from the [Visual Object Tracking by Hierarchical Attention Siamese Network](https://ieeexplore.ieee.org/abstract/document/8835075). Our approach focuses on keypart-based template matching, which enhances performance, especially in the context of our custom streetview dataset.

## Introduction

Template matching is a crucial technique in computer vision, commonly used for object detection and localization. Traditional methods often struggle with variations in scale, rotation, and occlusion. The QATM method addresses some of these issues by incorporating quality metrics into the matching process. However, there is still room for improvement.

By leveraging the hierarchical attention mechanism from the 'Visual Object Tracking by Hierarchical Attention Siamese Network' paper, we enhance the QATM method. Our approach utilizes keyparts of the template for more robust and accurate matching.

## Methodology

Our method involves the following steps:

1. **Mask Patch Creation**: We create a mask patch at one-quarter the size of the object. This mask is filled with the mean pixel value of the object.
2. **Mask Application**: The mask patch is applied at various positions on the object.
3. **Comparison and Selection**: The masked images are compared with the original object, and the masked image with the lowest value is selected.
4. **Keypart Extraction**: Based on the covered position of the selected masked image, the corresponding patch under the mask is cropped from the object patch as the key part.
5. **QATM Enhancement**: The keypart is then used to improve the performance of the QATM method.

<p align="center">
<img src="https://github.com/user-attachments/assets/e05891ee-5f59-471c-98bd-658952e19877" style="width: 500px;">
</p>

## Results

Our enhanced QATM method shows improvements in `AUC` performance on our custom streetview dataset which unfortunately is private.

<p align="center">
    <table>
        <thead>
            <th>QATM</th>
            <th>Enhanced QATM (Ours)</th>
        </thead>
        <tbody>
            <td>
                <img src="https://github.com/user-attachments/assets/56fa79dd-7062-4578-b9cf-7073a1490cfc" style="width: 500px;">
            </td>
            <td>
                <img src="https://github.com/user-attachments/assets/1c74aecb-cb18-481b-a9cc-782ec4587b55" style="width: 500px;">
            </td>
        </tbody>
    </table>
</p>

## Usage

To run the template matching with our enhanced method, simply run `template_matching.ipynb` notebook on the google colaboratory.
