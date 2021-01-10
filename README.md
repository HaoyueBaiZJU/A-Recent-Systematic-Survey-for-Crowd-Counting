# CNN-based Single Image Crowd Counting: Network Design, Loss Function, and Supervisory Signal

- Single image crowd counting is a challenging computer vision problem with wide applications in public safety, city planning, traffic management, etc. 
- This survey is to provide a comprehensive summary of recent advanced crowd counting techniques based on Convolutional Neural Network (CNN) via density map estimation. 
- Our goals are to provide an up-to-date review of recent approaches, and educate new researchers in this field the design principles and trade-offs.

The arXiv paper can be found at [paper](https://arxiv.org/pdf/2012.15685.pdf)


***


## Introduction

#### Crowd counting techniques applied in different domains

- Privacy preserving crowd monitoring: Counting people without people models or tracking [[paper](http://visal.cs.cityu.edu.hk/static/pubs/conf/cvpr08-peoplecnt.pdf)]
- Learning to count objects in images [[paper](https://papers.nips.cc/paper/2010/file/fe73f687e5bc5280214e0486b273a5f9-Paper.pdf)]
- Towards perspective-free object counting with deep learning [[paper](http://agamenon.tsc.uah.es/Personales/rlopez/docs/eccv2016-onoro.pdf)]


#### Detection-based

- Estimating the number of people in crowded scenes by mid based foreground segmentation and head-shoulder detection [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=4761705&casa_token=dzAA-G4aQVwAAAAA:8GI1YCkmg5NyAZfT8rP0bQ-eHVD9ONvE_DEpmKBoHKd0ECw1ujCYdmfQCPaO_pcSguMgOgWods8)]
- Shape-based human detection and segmentation via hierarchical part-template matching [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=5374413&casa_token=aZiFsfDQbQUAAAAA:RGNPYi0ICULTEDB5H7ORmGhrIGOKiq4RvogPECLl00R7eQcsmKd-nhB4CxMtuwbmeZ4qP93PalU)]
- Counting crowded moving objects [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=1640823&casa_token=Tszl5nZ5wpwAAAAA:U32Qpr_s8QU3oXPYTnwvmXZcs5A1fN0ziMR35EB7Oop7hUOb_M-ippIcO7ET8gdkbhc5CbfrrHg)]

#### Regression-based

- Bayesian poisson regression for crowd counting [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=5459191&casa_token=G4EQj857y4kAAAAA:iO0U-FLzaGA09NE-X_V0P6PGe4Pd_iJFQAnZorJiGPhjPKs34zSdg1KkLHPDKH9c33zSP_FE-Mc)]
- Counting people with low-level features and Bayesian regression [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=6054049&casa_token=pwSFIUIQ2S4AAAAA:FUwna8LcvdjWHeC5Isi3QwFn1WIrEtPH6NsqrMDkMpLQTJiH8akXPQyOOKPxlJtNgwEYRStVCl4)]
- Deep people counting in extremely dense crowds [[paper](https://dl.acm.org/doi/pdf/10.1145/2733373.2806337?casa_token=Lxw56nvKYkgAAAAA:4h2TKbGy8IyCHETIZiPywOkAQwYPn4fHgYvnmw5hB6Z2odj41O_yCkRCiduAI6pOoY7gZFb6PTCzmko)]


#### Density map estimation









![summary](https://github.com/HaoyueBaiZJU/A-Recent-Systematic-Survey-for-Crowd-Counting/blob/master/images/summary.PNG)


we review the recent advances with detailed comparisons on three major design modules for crowd counting: deep neural network designs, loss functions, and supervisory signals.




## Datasets and Performance Evaluation

### Datasets

### Performance Evaluation and Metrics




## Deep Neural Network Design


### Fully Convolutional Network

### Encoder-Decoder Architecture

### Multi-Column and Pyramid Network

### Dilated and Deformable Convolutional Operations

### Attention-based Model

### Others





## Loss Function

### Euclidean Loss


### SSIM Loss

### Adversarial Loss

### Multi-task Learning

### Others



## Supervisory Signal


### Fully Supervised Learning

### Weakly Supervised and Semi-supervised Learning

### Unsupervised and Self-supervised Learning

### Automatic Labeling through Synthetic Data


## Conclution and Future Directions

- Automatic and lightweight network designing.
- Weakly supervised and unsupervised crowd counting.
- Crowd counting in videos.
- Multi-view fusion for crowd counting



Towards perspective-free object counting with deep learning, 2016

Learning to count objects in images, 2010

Privacy preserving crowd monitoring: Counting people without people models or tracking, 2008



Framework



Network Details




![dataset](https://github.com/HaoyueBaiZJU/A-Recent-Systematic-Survey-for-Crowd-Counting/blob/master/images/dataset.PNG)





















