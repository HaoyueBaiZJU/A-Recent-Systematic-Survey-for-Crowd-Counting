# A survey on deep learning-based single image crowd counting: Network design, loss function and supervisory signal

- Single image crowd counting is a challenging computer vision problem with wide applications in public safety, city planning, traffic management, etc. 
- This survey is to provide a comprehensive summary of recent advanced crowd counting techniques based on Convolutional Neural Network (CNN) via density map estimation. 
- Our goals are to provide an up-to-date review of recent approaches, and educate new researchers in this field the design principles and trade-offs.

Our long survey paper (23 pages) is accepted to Neurocomputing 2022 [paper](https://arxiv.org/pdf/2012.15685.pdf)


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


More recently, crowd counting via density map estimation has emerged as a promising approach with encouraging results. Such approaches achieve high accuracy for crowded scenes and preserve spatial information of people distribution. 

We summarize by comparing the aforementioned three major crowd counting approaches in the following table. 

![summary](https://github.com/HaoyueBaiZJU/A-Recent-Systematic-Survey-for-Crowd-Counting/blob/master/images/summary.PNG)


we review the recent advances with detailed comparisons on three major design modules for crowd counting: deep neural network designs, loss functions, and supervisory signals.



## Datasets and Performance Evaluation

### Datasets

#### Metrics considered to choose datasets

- **Image resolution**
- **Number of images in the dataset**
- **Object count**

#### Publicly available datasets

We extract and present some typical images from the public datasets in the following figure. 

![dataset](https://github.com/HaoyueBaiZJU/A-Recent-Systematic-Survey-for-Crowd-Counting/blob/master/images/dataset.PNG)


- **NWPU-Crowd:** Nwpu-crowd: A large-scale benchmark for crowd counting [[paper](https://arxiv.org/pdf/2001.03360.pdf)]
 
- **UCF_QNRF:** Composition loss for counting, density map estimation and localization in dense crowds [[paper](https://openaccess.thecvf.com/content_ECCV_2018/papers/Haroon_Idrees_Composition_Loss_for_ECCV_2018_paper.pdf)]

- **GCC:** Pixel-Wise Crowd Understanding via Synthetic Data [[paper](https://link.springer.com/article/10.1007/s11263-020-01365-4)]

- **Fudan-ShanghaiTech:** Locality-constrained spatial transformer network for video crowd counting [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8784762&casa_token=CdYHMLvtMU0AAAAA:St2c0vePEbG60JL1EfR70HitY3-9lUgXxwTg1GWDcHtMrX-wNFmzLo_euOpkx0N8nOpd0_EH2YU&tag=1)]

- **ShanghaiTech A & B:** Single-image crowd counting via multi-column convolutional neural network [[paper](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Zhang_Single-Image_Crowd_Counting_CVPR_2016_paper.pdf)]

- **WorldExpo'10:** Cross-scene crowd counting via deep convolutional neural networks [[paper](https://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Zhang_Cross-Scene_Crowd_Counting_2015_CVPR_paper.pdf)]

- **UCF_CC_50:** Multi-source multi-scale counting in extremely dense crowd images [[paper](https://www.cv-foundation.org/openaccess/content_cvpr_2013/papers/Idrees_Multi-source_Multi-scale_Counting_2013_CVPR_paper.pdf)]

- **Mall:** Feature mining for localised crowd counting [[paper](http://personal.ie.cuhk.edu.hk/~ccloy/files/bmvc_2012b.pdf)]

- **UCSD:** Privacy preserving crowd monitoring: Counting people without people models or tracking [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=4587569&casa_token=Abf09f_74XYAAAAA:dx5cS931yoxMMS3mwLVdRsqjVGhATvFkE2ymiW1-rqwcPRPEdBqM-5vFfAXIfiLCNxLmFi4uQfc)]



### Performance Evaluation and Metrics

- **Accuracy: counting accuracy and location accuracy**
- **Quality of density map: resolution and visual quality**
- **Complexity: computation complexity and annotation complexity**
- **Flexibility and robustness**




## Deep Neural Network Design


### Fully Convolutional Network

- Fully convolutional crowd counting on highly congested scenes [[paper](https://arxiv.org/pdf/1612.00220.pdf)]

### Encoder-Decoder Architecture

- Scale aggregation network for accurate and efficient crowd counting [[paper](https://openaccess.thecvf.com/content_ECCV_2018/papers/Xinkun_Cao_Scale_Aggregation_Network_ECCV_2018_paper.pdf)]
- Crowd counting and density estimation by trellis encoder-decoder networks [[paper](https://openaccess.thecvf.com/content_CVPR_2019/papers/Jiang_Crowd_Counting_and_Density_Estimation_by_Trellis_Encoder-Decoder_Networks_CVPR_2019_paper.pdf)]

### Multi-Column and Pyramid Network

#### Multi-Column architecture

- Single-image crowd counting via multi-column convolutional neural network [[paper](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Zhang_Single-Image_Crowd_Counting_CVPR_2016_paper.pdf)]

- Improving the learning of multi-column convolutional neural network for crowd counting [[paper](https://dl.acm.org/doi/pdf/10.1145/3343031.3350898?casa_token=GZ9MQx0b5KAAAAAA:HI8lB8sjyxjL_S2RokCL3pLY_8YUUPuZpKBzcrwVvfoewWG0c_zGvyA27abKV1puDt7-dJOhfY7Qk24)]

#### Pyramid architecture

- Crowd counting by adaptively fusing predictions from an image pyramid [[paper](https://arxiv.org/pdf/1805.06115.pdf)]

- Generating high-quality crowd density maps using contextual pyramid cnns [[paper](https://openaccess.thecvf.com/content_ICCV_2017/papers/Sindagi_Generating_High-Quality_Crowd_ICCV_2017_paper.pdf)]

### Dilated and Deformable Convolutional Operations

#### Dilated convolution

- An aggregated multicolumn dilated convolution network for perspective-free counting [[paper](https://openaccess.thecvf.com/content_cvpr_2018_workshops/papers/w6/Deb_An_Aggregated_Multicolumn_CVPR_2018_paper.pdf)]

- Denet: A universal network for counting crowd with varying densities and scales [[paper](https://ieeexplore.ieee.org/document/9088979?denied=)]

#### Deformable convolution

- Dadnet: Dilated-attention-deformable convnet for crowd counting [[paper](https://dl.acm.org/doi/pdf/10.1145/3343031.3350881?casa_token=6zSbe2HO2rMAAAAA:QAXD5qaBJCFu6KlvlAnscn_QjL3WrLuo4HCT-edcbDCN0TmM8-gFQHiPAIRgXDTX0qfl-3DqB-g5e50)]

- Adcrowdnet: An attention-injective deformable convolutional network for crowd understanding [[paper](https://openaccess.thecvf.com/content_CVPR_2019/papers/Liu_ADCrowdNet_An_Attention-Injective_Deformable_Convolutional_Network_for_Crowd_Understanding_CVPR_2019_paper.pdf)]

### Attention-based Model

- SCAR: Spatial-/channel-wise attention regression networks for crowd counting [[paper](https://www.sciencedirect.com/science/article/pii/S0925231219311373?casa_token=iwBdg-PkCRUAAAAA:TeeworPPpaREJIn80NKWjRN4SanN7EHws6owI6yfqw_Zk8YscDBulLFdC-80mUKY3V2-Zp1QjSL0)]

- Relational attention network for crowd counting [[paper](https://openaccess.thecvf.com/content_ICCV_2019/papers/Zhang_Relational_Attention_Network_for_Crowd_Counting_ICCV_2019_paper.pdf)]

- Attend to count: Crowd counting with adaptive capacity multi-scale CNNs [[paper](https://www.sciencedirect.com/science/article/pii/S0925231219311282?casa_token=q54u5dJot9EAAAAA:EhMIjJUHC2h90y4L5TcWZsBFda8Xy6p9eBs7yy_fMQ8799JAi1lfzSkbk9JCPSIJ5tpurDXQKvCf)]


### Others

#### Graph neural network-based method

- Hybrid Graph Neural Networks for Crowd Counting [[paper](https://arxiv.org/pdf/2002.00092.pdf)]

#### Recurrent neural network-based method

- Crowd counting using deep recurrent spatial-aware network [[paper](https://arxiv.org/pdf/1807.00601.pdf)]

- End-to-end crowd counting via joint learning local and global count [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7532551&casa_token=NJXuS1NjwWkAAAAA:oLvZWuwhrz_1vygc787C5OoShExACMtdCw_HolV08SDRnr3rejuh3_FTkYWTIenHKh6NJMq8n3I&tag=1)]


#### Combining with detection

- Where are the blobs: Counting by localization with point supervision [[paper](https://openaccess.thecvf.com/content_ECCV_2018/papers/Issam_Hadj_Laradji_Where_are_the_ECCV_2018_paper.pdf)]

- Decidenet: Counting varying density crowds through attention guided detection and density estimation [[paper](https://openaccess.thecvf.com/content_cvpr_2018/papers/Liu_DecideNet_Counting_Varying_CVPR_2018_paper.pdf)]


## Loss Function

### Euclidean Loss


- Csrnet: Dilated convolutional neural networks for understanding the highly congested scenes [[paper](https://openaccess.thecvf.com/content_cvpr_2018/papers/Li_CSRNet_Dilated_Convolutional_CVPR_2018_paper.pdf)]


### SSIM Loss

- Crowd counting with deep structured scale integration network [[paper](https://openaccess.thecvf.com/content_ICCV_2019/papers/Liu_Crowd_Counting_With_Deep_Structured_Scale_Integration_Network_ICCV_2019_paper.pdf)]

- Cross-Level Parallel Network for Crowd Counting [[paper](https://ieeexplore.ieee.org/document/8798674?denied=)]

### Adversarial Loss

- Adversarial learning for multiscale crowd counting under complex scenes [[paper](https://ieeexplore.ieee.org/document/8949751?denied=)]

- Atrous convolutions spatial pyramid network for crowd counting and density estimation [[paper](https://www.sciencedirect.com/science/article/abs/pii/S0925231219304059)]

### Multi-task Learning

- Crowd counting via scale-adaptive convolutional neural network [[paper](https://ieeexplore.ieee.org/document/8354231?denied=)]

- Counting with focus for free [[paper](https://openaccess.thecvf.com/content_ICCV_2019/papers/Shi_Counting_With_Focus_for_Free_ICCV_2019_paper.pdf)]

### Others

- Learning to count with cnn boosting [[paper](http://courses.cs.tau.ac.il/~wolf/papers/learning-count-cnn.pdf)]

- Nonlinear regression via deep negative correlation learning [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8850209&casa_token=FVYY2_B9ysMAAAAA:uWnIHj1VeeihAtTexyNH6QPe80wyKUshgdhh_a-UKt76MGtg_r-sc0yWC9zxNOHY-hdcS9DPir0&tag=1)]

- From open set to closed set: Counting objects by spatial divide-and-conquer [[paper](https://openaccess.thecvf.com/content_ICCV_2019/papers/Xiong_From_Open_Set_to_Closed_Set_Counting_Objects_by_Spatial_ICCV_2019_paper.pdf)]


## Supervisory Signal


### Fully Supervised Learning

- Adaptive density map generation for crowd counting [[paper](https://openaccess.thecvf.com/content_ICCV_2019/papers/Wan_Adaptive_Density_Map_Generation_for_Crowd_Counting_ICCV_2019_paper.pdf)]

- Bayesian loss for crowd count estimation with point supervision [[paper](https://openaccess.thecvf.com/content_ICCV_2019/papers/Ma_Bayesian_Loss_for_Crowd_Count_Estimation_With_Point_Supervision_ICCV_2019_paper.pdf)]

### Weakly Supervised and Semi-supervised Learning

- Ha-ccn: Hierarchical attention-based crowd counting network [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8767009&casa_token=FROykBlRwNQAAAAA:rnRBQiPPKllwdUpCitTg--2glKonx7zi2sBHmz8A3Dw1P0VgRJlje1HVwSjQat2Jx9JpJX8jaeE)]

- Generalizing semi-supervised generative adversarial networks to regression using feature contrasting [[paper](https://www.sciencedirect.com/science/article/pii/S1077314219300955?casa_token=Ma91MYkXZq8AAAAA:2xoOFAH4xvZmyNQND6eQLhNTZW5i_T5BZJmbJbVr9a2rqASxijHs9YO7ocpOHquNQuz8GdCoTF98)]


### Unsupervised and Self-supervised Learning

- Almost unsupervised learning for dense crowd counting [[paper](https://ojs.aaai.org//index.php/AAAI/article/view/4914)]

- Leveraging unlabeled data for crowd counting by learning to rank [[paper](https://openaccess.thecvf.com/content_cvpr_2018/papers/Liu_Leveraging_Unlabeled_Data_CVPR_2018_paper.pdf)]

### Automatic Labeling through Synthetic Data

- Learning from synthetic data for crowd counting in the wild [[paper](https://openaccess.thecvf.com/content_CVPR_2019/papers/Wang_Learning_From_Synthetic_Data_for_Crowd_Counting_in_the_Wild_CVPR_2019_paper.pdf)]

- Focus on semantic consistency for cross-domain crowd understanding [[paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9054768&casa_token=xBMDLzm0p0oAAAAA:T0ORsXuV6ARNk1RqFIHd2niOHJxu8qxlq_nDL9UFqQJPFyNmPOjq4X2DMKynzNs-zJofcfviuHQ)]


## Conclusion and Future Directions

- Automatic and lightweight network designing
- Weakly supervised and unsupervised crowd counting
- Crowd counting in videos
- Multi-view fusion for crowd counting


## References
If you find this work or code useful, please cite:

```
@article{bai2022survey,
  title={A survey on deep learning-based single image crowd counting: Network design, loss function and supervisory signal},
  author={Bai, Haoyue and Mao, Jiageng and Chan, S-H Gary},
  journal={Neurocomputing},
  year={2022},
  publisher={Elsevier}
}
```




