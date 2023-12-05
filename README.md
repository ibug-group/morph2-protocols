# Facial Age Estimation Protocols for the Morph2 Dataset

## Introduction

This repo collects the three widely-recognized protocols for using the Morph2 dataset in facial age estimation research. We aim to present precise splits for each protocol to enable researchers to replicate studies and benchmark their results in a consistent and equitable manner.

### AGR Protocol

The AGR Protocol, introduced in the study ["Age Estimation by Multi-scale Convolutional Network,"]((http://www.cbsr.ia.ac.cn/users/dyi/agr.html)) organizes the Morph2 dataset into subsets S1, S2, and S3 according to two guidelines: 1) Balancing the Male-to-Female ratio at 3:1; 2) Equating the White-to-Black ratio.

In all experiments, the training and testing are repeated in two times: 1) training on S1, testing on S2+S3 and 2) training on S2, testing on S1 + S3. The performance of the two experiments and their **average** are reported. The protocol uses all images in Table 1 for age and gender estimation, while it excludes images labeled as "Other" ethnicity for classification tasks.

| Gender | Ethnicity | Subset S1 | Subset S2 | Subset S3 |
| ------ | --------- | --------- | --------- | --------- |
| Male   | Black     | 4012      | 4012      | 28835     |
| Male   | White     | 4012      | 4012      | 0         |
| Male   | Other     | 0         | 0         | 1845      |
| Female | Black     | 1305      | 1305      | 3166      |
| Female | White     | 1305      | 1305      | 0         |
| Female | Other     | 0         | 0         | 130       |

*Table 1. The information of the pre-processed MORPH Album 2 and subsets S1, S2, S3.*

### DEX Protocol

The DEX Protocol is implemented with a collection of 5,475 photographs featuring individuals aged between 16 to 77 years, all of whom are of **White** ethnicity. To facilitate the research, these photographs are randomly allocated into two groups: 80% (amounting to 4,382 photos) are used for the training set, and the remaining 20% (1,095 photos) constitute the testing set. This distribution model has been adopted in the [DEX](https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/) method and is also referenced in the works of Chang et al. (2011), Chen et al. (2013), Guo et al. (2008), Wang et al. (2015), and Rothe et al. (2016), highlighting its prevalence in the field.

### RANDOM Protocol

The RANDOM Protocol is widely favored for its straightforward approach: it randomly assigns 80% of the dataset for training purposes and reserves 20% for testing. Despite its popularity, a recurring challenge has been the lack of accessible details on the specific data splits and random seeds used in various studies, which poses obstacles to replicating the results and conducting fair comparisons. To address this issue, our repository adopts the split detailed by [FP-Age](https://github.com/yiminglin-ai/FP-Age), providing researchers with the necessary information to achieve reproducible and comparable outcomes.

## Reference

If you use this code as part of any published research, please acknowledge the following paper

```bibtex
@misc{lin2021fpage,
      title={FP-Age: Leveraging Face Parsing Attention for Facial Age Estimation in the Wild}, 
      author={Yiming Lin and Jie Shen and Yujiang Wang and Maja Pantic},
      year={2021},
      eprint={2106.11145},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```
