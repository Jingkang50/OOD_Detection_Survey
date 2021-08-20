# 5. OOD Detection

## 5.1 Classfication-based Method
### 5.1.0 Baseline
**[ICLR-2017]**
[A baseline for detecting misclassified and out-of-distribution examples in neural networks](https://arxiv.org/abs/1610.02136).

**Authors:** Hendrycks, Dan and Gimpel, Kevin

**Institution:** University of California, Berkeley; Toyota Technological Institute at Chicago
> <details>
> <summary> The starting point that simply uses softmax probabilities for OOD detection.</summary>
> <p style="text-align:left">
> Correctly classified examples tend to have greater maximum softmax probabilities than erroneously classified and out-of-distribution examples, allowing for their detection.
> </p>
> </details>

### 5.1.1 Confidence Calibration

#### 5.1.1.1 Post-hoc Calibration
**[ICLR-2018]**
[Enhancing The Reliability of Out-of-distribution Image Detection in Neural Networks](https://github.com/facebookresearch/odin).

Authors: Liang, Shiyu and Li, Yixuan and Srikant, R.
> <details>
> <summary> Using temperature scaling on softmax probabilities with small perturbations for robustness.</summary>
> <p style="text-align:left">
> Temperature scaling can calibrate the softmax probabilities so the model takes the calibrated maximum softmax probabilities as the indicator for OOD detection. A perturbation on each sample at test time can further exploit the model robustness in detecting ID samples. However, it requires part of the OOD samples for hyperparameter tuning.
> </p>
> </details>

**[CVPR-2020]**
[Generalized ODIN: Detecting Out-of-distribution Image without Learning from Out-of-distribution Data](https://arxiv.org/abs/2002.11297).

**Authors:** Hsu, Yen-Chang and Shen, Yilin and Jin, Hongxia and Kira, Zsolt

**Institution:** Georgia Institute of Technology; Samsung Research

> <details>
> <summary> Improving ODIN by decomposed confidence scoring and a modified input pre-processing method.</summary>
> <p style="text-align:left">
> The method find that previous work relies on the class posterior probability p(y|x), which does not consider the domain variable at all. Therefore, they use the explicit variable in the classifier, rewriting it as the quotient of the joint class-domain probability and the domain probability using the rule of conditional probability, and take the decomposed confidence scores for OOD detection. 
The decomposed confidence in the end is the probability of an input being in-distribution, computed by the cosine similarity between sample features and class features.
The method also modifies the input preprocessing by only optimizing in-distribution data, therefore extra OOD validation samples are not required.
> </p>
> </details>



#### 5.1.1.2 Bayesian Methods
The Bayesian uncertainty methods could be directly applied to reject OOD samples as we would expect the uncertainty to be high on such inputs.

**[ICML-2016]**
[Dropout as a bayesian approximation: Representing model uncertainty in deep learning](https://arxiv.org/abs/1506.02142).

Authors: Gal, Yarin and Ghahramani, Zoubin
> <details>
> <summary>Dropout training as approximate Bayesian inference in deep Gaussian processes.</summary>
> <p style="text-align:left">
> This paper develops a new theoretical framework for deep uncertainty estimation without sacrificing either computational complexity or test accuracy, which is the drawbacks that often occur in deep Bayesian models.
> </p>
> </details>

**[NeurIPS-2017]**
[Simple and scalable predictive uncertainty estimation using deep ensembles](https://arxiv.org/abs/1612.01474).

Authors: Lakshminarayanan, Balaji and Pritzel, Alexander and Blundell, Charles
> <details>
> <summary>Ensemble training as an alternative to Bayesian NNs for high-quality predictive uncertainty estimate.</summary>
> <p style="text-align:left">
> First work to investigate their usefulness for predictive uncertainty estimation and compare their performance to current state-of-the-art approximate Bayesian
methods on a series of classification and regression benchmark datasets.
> </p>
> </details>


**[ICML-2020]**
[How good is the bayes posterior in deep neural networks really?](???)

Authors: Wenzel, Florian and Roth, Kevin and Veeling, Bastiaan S and {\'S}wi{\k{a}}tkowski, Jakub and Tran, Linh and Mandt, Stephan and Snoek, Jasper and Salimans, Tim and Jenatton, Rodolphe and Nowozin, Sebastian
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>


**[NeurIPS-2019]**
[Practical deep learning with Bayesian principles](???).

Authors: Osawa, Kazuki and Swaroop, Siddharth and Jain, Anirudh and Eschenhagen, Runa and Turner, Richard E and Yokota, Rio and Khan, Mohammad Emtiyaz
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>


**[ICML-2020]**
[Bayesian deep learning and a probabilistic perspective of generalization](???).

Authors: Wilson, Andrew Gordon and Izmailov, Pavel
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>



**[ICMLW-2020]**
['In-Between' Uncertainty in Bayesian Neural Networks](???).

Authors: Foong, Andrew YK and Li, Yingzhen and Hern{\'a}ndez-Lobato, Jos{\'e} Miguel and Turner, Richard E
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>


#### 5.1.1.3 Other Confidence Enhancement Methods

**[arXiv-2018]**
[Learning confidence for out-of-distribution detection in neural networks](???).

Authors: DeVries, Terrance and Taylor, Graham W
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>


**[CVPR-2019]**
[Why relu networks yield high-confidence predictions far away from the training data and how to mitigate the problem](???).

Authors: Hein, Matthias and Andriushchenko, Maksym and Bitterwolf, Julian
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>


**[NeurIPS-2020]**
[Certifiably adversarially robust detection of out-of-distribution data](???).

Authors: Bitterwolf, Julian and Meinke, Alexander and Hein, Matthias
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>


**[NeurIPS-2019]**
[On mixup training: Improved calibration and predictive uncertainty for deep neural networks](???).

Authors: Thulasidasan, Sunil and Chennupati, Gopinath and Bilmes, Jeff and Bhattacharya, Tanmoy and Michalak, Sarah
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>


**[arXiv-2019]**
[Towards neural networks that provably know when they don't know](???).

Authors: Meinke, Alexander and Hein, Matthias
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>



**[ECCV-2018]**
[Out-of-Distribution Detection Using an Ensemble of Self Supervised Leave-out Classifiers](https://arxiv.org/abs/1809.03576)

Authors: Vyas, Apoorv and Jammalamadaka, Nataraj and Zhu, Xia and Das, Dipankar and Kaul, Bharat and Willke, Theodore L.
> <details>
> <summary>Using an additional background or garbage class for an entropic open-set and objectosphere losses.</summary>
> <p class="small" style="text-align:left">
> 
> </p>
> </details>


**[arXiv-2020]**
[Robust out-of-distribution detection for neural networks](???).

Authors: Chen, Jiefeng and Li, Yixuan and Wu, Xi and Liang, Yingyu and Jha, Somesh
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>


**[CVPR-2021]**
[MOOD: Multi-level Out-of-distribution Detection](???).

Authors: Lin, Ziqian and Roy, Sreya Dutta and Li, Yixuan
> <details>
> <summary></summary>
> <p style="text-align:left">
> 
> </p>
> </details>


### 5.1.2 Outlier Exposure

**[NeurIPS-2018]**
[Reducing network agnostophobia](https://arxiv.org/abs/1811.04110).

Authors: Dhamija, Akshay Raj and G{\"u}nther, Manuel and Boult, Terrance E
> <details>
> <summary>Using an additional background or garbage class for an entropic open-set and objectosphere losses.</summary>
> <p class="small" style="text-align:left">
> The paper designs novel losses to maximize entropy for unknown inputs while increasing separation in deep feature space by modifying magnitudes of known and unknown samples. In sum, logits entropy and feature magnitudes are used for OOD detection.
> </p>
> </details>


**[NeurIPS-2018]**
[Deep anomaly detection with outlier exposure](https://arxiv.org/abs/1610.02136).

Authors: Hendrycks, Dan and Mazeika, Mantas and Dietterich, Thomas
> <details>
> <summary>A model to produce a uniform posterior distribution on auxiliary dataset of outliers.</summary>
> <p class="small" style="text-align:left">
> It can learn effective heuristics for detecting out-of-distribution inputs by exposing the model to OOD examples, thus learning a more conservative concept of the inliers and enabling the detection of novel forms of anomalies. The result is shown effective on both CV and NLP tasks.
> </p>
> </details>


**[ICCV-2019]**
[Unsupervised out-of-distribution detection by maximum classifier discrepancy](https://arxiv.org/abs/1908.04951).

Authors: Yu, Qing and Aizawa, Kiyoharu
> <details>
> <summary>Two-branch network to enlarge entropy discrepancy between two branches when encountering OOD training data.</summary>
> <p class="small" style="text-align:left">
> It trains a two-head CNN consisting of one common feature extractor and two classifiers which have different decision boundaries but can classify in-distribution samples correctly. Then it uses the unlabeled data to maximize the discrepancy between the decision boundaries of two classifiers to push OOD samples outside the manifold of the in-distribution samples, which enables to detect OOD samples that are far from the support of the ID samples.
> </p>
> </details>

**[AAAI-2020]**
[Self-supervised learning for generalizable out-of-distribution detection](?)

Authors: Mohseni, Sina and Pitale, Mandar and Yadawa, JBS and Wang, Zhangyang


**[Neurocomputing-2021]**
[Outlier exposure with confidence control for out-of-distribution detection](?)

Authors: Papadopoulos, Aristotelis-Angelos and Rajati, Mohammad Reza and Shaikh, Nazim and Wang, Jiamian


### 5.1.3 OOD Data Generation

**[ICLR-2018]**
[Training confidence-calibrated classifiers for detecting out-of-distribution samples](??)

Authors: Lee, Kimin and Lee, Honglak and Lee, Kibok and Shin, Jinwoo

**[NeurIPSW-2018]**
[Building robust classifiers through generation of confident out of distribution examples](?)

Authors: Sricharan, Kumar and Srivastava, Ashok

**[CVPR-2019]**
[Out-of-distribution detection for generalized zero-shot action recognition](?)

Authors: Mandal, Devraj and Narayan, Sanath and Dwivedi, Sai Kumar and Gupta, Vikram and Ahmed, Shuaib and Khan, Fahad Shahbaz and Shao, Ling

**[NeurIPSW-2019]**
[Out-of-distribution detection in classifiers via generation]()

Authors: Vernekar, Sachin and Gaurav, Ashish and Abdelzad, Vahdat and Denouden, Taylor and Salay, Rick and Czarnecki, Krzysztof


### 5.1.4 Label Space Redesign

**[arXiv-2021]** 
[Exploring the Limits of Out-of-Distribution Detection](https://arxiv.org/abs/2106.03004).

Authors: Fort, Stanislav and Ren, Jie and Lakshminarayanan, Balaji.


**[CVPR-2021]**
[MOS: Towards Scaling Out-of-distribution Detection for Large Semantic Space](https://arxiv.org/abs/2105.01879).

Authors: Huang, Rui and Li, Yixuan.


**[NeurIPS-2018]**
[Out-of-Distribution Detection using Multiple Semantic Label Representations](https://arxiv.org/abs/1808.06664). 

Authors: Shalev, Gabi and Adi, Yossi and Keshet, Joseph.


**[CVPR-2018]**
[Hierarchical Novelty Detection for Visual Object Recognition](https://arxiv.org/abs/1804.00722). 

Authors: Lee, Kibok and Lee, Kimin and Min, Kyle and Zhang, Yuting and Shin, Jinwoo and Lee, Honglak.


### 5.1.5 Big Pretrained Model
**[arXiv-2021]**
[Exploring the Limits of Out-of-Distribution Detection](??)
Authors: Fort, Stanislav and Ren, Jie and Lakshminarayanan, Balaji


**[arXiv-2020]**
[Pretrained transformers improve out-of-distribution robustness](??)

Authors: Hendrycks, Dan and Liu, Xiaoyuan and Wallace, Eric and Dziedzic, Adam and Krishnan, Rishabh and Song, Dawn

**[arXiv-2021]**
[OODformer: Out-Of-Distribution Detection Transformer](??)

Authors: Koner, Rajat and Sinhamahapatra, Poulami and Roscher, Karsten and G{\"u}nnemann, Stephan and Tresp, Volker


## 5.2 Density-based Method
### 5.2.1 Embedding-based Method

**[NeurIPS-2018]**
[A simple unified framework for detecting out-of-distribution samples and adversarial attacks](??)

Authors: Lee, Kimin and Lee, Kibok and Lee, Honglak and Shin, Jinwoo

**[NeurIPS-2019]**
[Likelihood ratios for out-of-distribution detection](??)

Authors: Ren, Jie and Liu, Peter J and Fertig, Emily and Snoek, Jasper and Poplin, Ryan and DePristo, Mark A and Dillon, Joshua V and Lakshminarayanan, Balaji

**[NeurIPS-2019]**
[Further analysis of outlier detection with deep generative models](?)

Authors: Wang, Ziyu and Dai, Bin and Wipf, David and Zhu, Jun

**[NeurIPS-2020]**
[Likelihood regret: An out-of-distribution detection score for variational auto-encoder](?)

Authors: Xiao, Zhisheng and Yan, Qing and Amit, Yali

**[NeurIPS-2018]**
[Do deep generative models know what they don't know?](?)

Authors: Nalisnick, Eric and Matsukawa, Akihiro and Teh, Yee Whye and Gorur, Dilan and Lakshminarayanan, Balaji

**[ICLR-2020]**
[Novelty detection via blurring](?)

Authors: Choi, Sungik and Chung, Sae-Young

**[ICLR-2020]**
[Input complexity and out-of-distribution detection with likelihood-based generative models](?)

Authors: Serr{\`a}, Joan and {\'A}lvarez, David and G{\'o}mez, Vicen{\c{c}} and Slizovskaia, Olga and N{\'u}{\~n}ez, Jos{\'e} F and Luque, Jordi}

**[arXiv-2020]**
[Probabilistic auto-encoder]()

Authors: B{\"o}hm, Vanessa and Seljak, Uro{\v{s}}

**[CVPR-2021]**
[Soft-IntroVAE: Analyzing and Improving the Introspective Variational Autoencoder](?)

Authors: Daniel, Tal and Tamar, Aviv


### 5.2.2 Flow-based Method
**[CVPR-2020]**
[Deep residual flow for out of distribution detection](?)

Authors: Zisselman, Ev and Tamar, Aviv


**[NeurIPS-2020]**
[Why normalizing flows fail to detect out-of-distribution data](?)

Authors: Kirichenko, Polina and Izmailov, Pavel and Wilson, Andrew Gordon

**[NeurIPS-2020]**
[Understanding anomaly detection with deep invertible networks through hierarchies of distributions and features](?)

Authors: Schirrmeister, Robin Tibor and Zhou, Yuxuan and Ball, Tonio and Zhang, Dan


### 5.2.3 Energy-based Method
**[ICLR-2019]**
[Your classifier is secretly an energy based model and you should treat it like one](?)

Authors: Grathwohl, Will and Wang, Kuan-Chieh and Jacobsen, J{\"o}rn-Henrik and Duvenaud, David and Norouzi, Mohammad and Swersky, Kevin

**[NeurIPS-2020]**
[Energy-based out-of-distribution detection](?)

Authors: Liu, Weitang and Wang, Xiaoyun and Owens, John D and Li, Yixuan


## 5.3 Distance-based Method
**[ACCV-2020]**
[Hyperparameter-free out-of-distribution detection using cosine similarity](https://arxiv.org/abs/1905.10628)

**Authors:** Techapanurak, Engkarat and Suganuma, Masanori and Okatani, Takayuki

**Institution:** Tohoku University; RIKEN

> <details>
> <summary> Using scaled cosine similarity between test sample features and class features to determine OOD samples. </summary>
> <p class="small" style="text-align:left">
> The first work employs softmax of scaled cosine similarity instead of ordinary softmax of logits. Taking the metric learning idea into OOD detection.
  It is also the concurrent work of Generalized ODIN, 
> </p>
> </details>



**[CVPR-2021]**
[Out-of-Distribution Detection Using Union of 1-Dimensional Subspaces](https://github.com/zaeemzadeh/OOD)

Authors: Zaeemzadeh, Alireza and Bisagno, Niccol{\`o} and Sambugaro, Zeno and Conci, Nicola and Rahnavard, Nazanin and Shah, Mubarak
> <details>
> <summary> class membership probabilities in . </summary>
> <p class="small" style="text-align:left">
> The cosine similarities between the extracted feature and the class vectors are used to compute the class membership probabilities, using a Union of 1-dimensional subspaces 
> </p>
> </details>


**[ECCV-2020]**
[A boundary based out-of-distribution classifier for generalized zero-shot learning](https://arxiv.org/abs/2008.04872)

Authors: Chen, Xingyu and Lan, Xuguang and Sun, Fuchun and Zheng, Nanning.


**[arXiv-2020]**
[Feature Space Singularity for Out-of-Distribution Detection](https://arxiv.org/abs/2011.14654)

Authors: Huang, Haiwen and Li, Zhihan and Wang, Lulu and Chen, Sishuo and Dong, Bin and Zhou, Xinyu
> <details>
> <summary> Distance to Feature Space Singularity can measure OOD.</summary>
> <p class="small" style="text-align:left">
> It is observed that in feature spaces, OOD samples concentrate near a Feature Space Singularity (FSS) point, and the distance from a sample to FSS measures the degree of OOD. It can be exlained that moving speeds of features of other data depend on their similarity to the training data. During training, they use generated uniform noise or validation data as OOD.
> </p>
> </details>


**[ICML-2020]**
[Detecting out-of-distribution examples with gram matrices](?)

Authors: Sastry, Chandramouli Shama and Oore, Sageev


**[ICML-2020]**
[Uncertainty estimation using a single deep deterministic neural network](?)

Authors: Van Amersfoort, Joost and Smith, Lewis and Teh, Yee Whye and Gal, Yarin


## 5.4 Meta-Learning-based Method
**[NeurIPS-2020]**
[OOD-MAML: Meta-learning for few-shot out-of-distribution detection and classification](?)

Authors: Jeong, Taewon and Kim, Heeyoung

**[ICLR-2020]**
[Learning to balance: Bayesian meta-learning for imbalanced and out-of-distribution tasks](?)

Authors: Lee, Hae Beom and Lee, Hayeon and Na, Donghyun and Kim, Saehoon and Park, Minseop and Yang, Eunho and Hwang, Sung Ju

## 5.5 Other Methods

Isolation forests exploits the fact that anomalies are scarce and different and while constructing the isolation tree, it is observed that the anomalous samples appear close to the root of the tree. These anomalies are then identified by measuring the length of the path from the root to a terminating node; the closer a node is to the root, the higher is its chance of representing an OOD.
