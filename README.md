# The EGC-Z datasets 
[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

This repository makes available the datasets used in the paper [Automatic Chronic Degenerative Diseases Identification Using Enteric Nervous System Images](https://link.springer.com/article/10.1007/s00521-021-06164-7) published to Neural Computer and Applications.

## Abstract
Studies recently accomplished on the Enteric Nervous System have shown that chronic degenerative diseases affect the Enteric Glial Cells (EGC) and, thus, the development of recognition methods able to identify whether or not the EGC are affected by these type of diseases may be helpful in its diagnoses. In this work, we propose the use of pattern recognition and machine learning techniques to evaluate if a given animal EGC image was obtained from a healthy individual or one affect by a chronic degenerative disease. In the proposed approach, we have performed the classification task with handcrafted features and deep learning-based techniques, also known as non-handcrafted features. The handcrafted features were obtained from the textural content of the ECG images using texture descriptors, such as the Local Binary Pattern (LBP). Moreover, the representation learning techniques employed in the approach are based on different Convolutional Neural Network (CNN) architectures, such as AlexNet and VGG16, with and without transfer learning. The complementarity between the handcrafted and non-handcrafted features was also evaluated with late fusion techniques. The datasets of EGC images used in the experiments, which are also contributions of this paper, are composed of three different chronic degenerative diseases: Cancer, Diabetes Mellitus, and Rheumatoid Arthritis. The experimental results, supported by statistical analysis, show that the proposed approach can distinguish healthy cells from the sick ones with a recognition rate of 89.30% (Rheumatoid Arthritis), 98.45% (Cancer), and 95.13% (Diabetes Mellitus), being achieved by combining classifiers obtained on both feature scenarios.

## Details
Three novel datasets created by researchers of the Enteric Neural Plasticity Laboratory of the State University of Maringá are presented in this repository. Such datasets are composed of image samples obtained from the Enteric Nervous System (ENS) of rats, in which the Enteric Glial Cells (EGC) can be visualized through the immunostaining of the S100 protein. Each dataset represents an investigated disease, being them: arthritis rheumatoid (AIA), cancer (TW) and diabetes mellitus (D). It is worth mentioning that in this scenario, the datasets can be also called "disease groups".

The datasets are composed of two classes, one containing image samples extracted from the animals that presented the target disease (1) and other from control/healthy (0) ones. The exact quantity of image samples per dataset and per class, and the image samples' dimensions, can be seen in the following table. More details on how the data samples were obtained may be seen in the aforementioned paper.

| Dataset | Sick (1) | Control/Healthy (0) | Image Dimension | # of samples |
| ---- | --- | ---- | ---- | ---- | 
| AIA  | 210 | 208 | 1024 x 768  | 418 |
| TW   | 192 | 224 | 1384 x 1036 | 416 |
| D    | 290 | 224 | 1384 x 1036 | 514 |

While building classifiers with any of the EGC-Z datasets, one should keep under consideration:
* The datasets were obtained separately by different researchers, presenting unique characteristics such as: different noise levels; higher or lower contrast; lack of definition in the EGC; and others. Therefore, **the datasets should be kept separated**, being treated as three different binary classification problems;
* The images are obtained from random samples extracted from the animal's small intestine, not representing any kind of observable continuity or correlation. Thus, using images from the same animal while training and testing should not represent any kind of data leakage. But, to ensure the model's correctiness **we recommend to always keep the images from one source animal together in the same split**;
* Additionally, the use of **the leave-one-out cross-validation method is encouraged**, i.e. each fold is composed exclusively by one animal's image samples.

## Data Organization
The overall data organization is the one that follows:

```
data/
  |__ DATASET_1/
  |  |__ animal_tag_1/
  |  |  |__ sample_1.jpg
  |  |  |__ sample_2.jpg
  |  |  ...
  |  |  |__ sample_n.jpg
  |  |__ animal_tag_2/
  |  ...
  |__ DATASET_2/
  |  ...
```

In each dataset folder, one may find an additional CSV file containing the overall information about it, including each one of the image samples' labels.

## Citation
Whenever using the here available data, remember to cite the original paper:
```
@Article{Felipe2021,
    author={Felipe, Gustavo Z.
        and Zanoni, Jacqueline N.
        and Sehaber-Sierakowski, Camila C.
        and Bossolani, Gleison D. P.
        and Souza, Sara R. G.
        and Flores, Franklin C.
        and Oliveira, Luiz E. S.
        and Pereira, Rodolfo M.
        and Costa, Yandre M. G.},
    title={Automatic chronic degenerative diseases identification using enteric nervous system images},
    journal={Neural Computing and Applications},
    year={2021},
    month={Jun},
    day={17},
    issn={1433-3058},
    doi={10.1007/s00521-021-06164-7},
    url={https://doi.org/10.1007/s00521-021-06164-7}
}
```

## Additional Notes
1. The TW dataset is currently unavailable due to a submitted paper. When the publication process is complete, such data will be made available as well.

## Acknowledgements
We thank the Brazilian Research Support Agency CNPq - National Council for Scientific and Technological Development.

## License 
This work is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].

That means that you can:
* **Share** — copy and redistribute the material in any medium or format
* **Adapt** — remix, transform, and build upon the material

under the following terms:
* **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
* **NonCommercial** — You may not use the material for commercial purposes.
* **ShareAlike** — If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg
