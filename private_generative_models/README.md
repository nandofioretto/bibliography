# Private Generative Models Bibliography
Last update: Jun 16, 2018


## Content
<a name='_content'></a>

- [Private Generative Adverarial Networks](#_dp_gans)

- [Generative Model for Private Data Synthesis](#_dp_gen)



## Private Generative Adverarial Networks
<a name='_dp_gans'></a>

[Jump to Top](#_content) 


- Differentially Private Generative Adversarial Network
    <a name="Xie:18"></a>
    [[Paper]](https://arxiv.org/pdf/1802.06739.pdf)

    _Liyang Xie1, Kaixiang Lin1, Shu Wang2, Fei Wang3, Jiayu Zhou1 (CCS 2018)_

    _Generative Adversarial Network (GAN) and its variants have recently attracted intensive research interests due to their elegant theoretical foundation and excellent empirical performance as generative models. These tools provide a promising direction in the studies where data availability is limited. One common issue in GANs is that the density of the learned generative distribution could concentrate on the training data points, meaning that they can easily remember training samples due to the high model complexity of deep networks. This becomes a major concern when GANs are applied to private or sensitive data such as patient medical records, and the concentration of distribution may divulge critical patient information. To address this issue, in this paper we propose a differentially private GAN (DPGAN) model, in which we achieve differential privacy in GANs by adding carefully designed noise to gradients during the learning procedure. We provide rigorous proof for the privacy guarantee, as well as comprehensive empirical evidence to support our analysis, where we demonstrate that our method can generate high quality data points at a reasonable privacy level._

    >[Comments]:
    - This paper was submitted to CCS-18 and seem to be rejected.
    - Need to check its privacy guarantees.

- Differentially Private Releasing via Deep Generative Model
    <a name='Zhang:18'></a>
    [[Paper]](https://arxiv.org/abs/1801.01594)

    _Xinyang Zhang, Shouling Ji, Ting Wang (ArXiv 2018)_

    >_Privacy-preserving releasing of complex data (e.g., image, text, audio) represents a long-standing challenge for the data mining research community. Due to rich semantics of the data and lack of a priori knowledge about the analysis task, excessive sanitization is often necessary to ensure privacy, leading to significant loss of the data utility. In this paper, we present dp-GAN, a general private releasing framework for semantic-rich data. Instead of sanitizing and then releasing the data, the data curator publishes a deep generative model which is trained using the original data in a differentially private manner; with the generative model, the analyst is able to produce an unlimited amount of synthetic data for arbitrary analysis tasks. In contrast of alternative solutions, dp-GAN highlights a set of key features: (i) it provides theoretical privacy guarantee via enforcing the differential privacy principle; (ii) it retains desirable utility in the released model, enabling a variety of otherwise impossible analyses; and (iii) most importantly, it achieves practical training scalability and stability by employing multi-fold optimization strategies. Through extensive empirical evaluation on benchmark datasets and analyses, we validate the efficacy of dp-GAN._


- Context-Aware Generative Adversarial Privacy
    <a name='Huang:18'></a>
    [[Paper]](https://arxiv.org/pdf/1710.09549.pdf)

    _Chong Huang, Peter Kairouz, Xiao Chen, Lalitha Sankar, Ram Rajagopal (Entropy 2018)_
    
    >_Preserving the utility of published datasets while simultaneously providing provable privacy guarantees is a well-known challenge. On the one hand, context-free privacy solutions, such as differential privacy, provide strong privacy guarantees, but often lead to a significant reduction in utility. On the other hand, context-aware privacy solutions, such as information theoretic privacy, achieve an improved privacy-utility tradeoff, but assume that the data holder has access to dataset statistics. We circumvent these limitations by introducing a novel context-aware privacy framework called generative adversarial privacy (GAP). GAP leverages recent advancements in generative adversarial networks (GANs) to allow the data holder to learn privatization schemes from the dataset itself. Under GAP, learning the privacy mechanism is formulated as a constrained minimax game between two players: a privatizer that sanitizes the dataset in a way that limits the risk of inference attacks on the individuals' private variables, and an adversary that tries to infer the private variables from the sanitized dataset. To evaluate GAP's performance, we investigate two simple (yet canonical) statistical dataset models: (a) the binary data model, and (b) the binary Gaussian mixture model. For both models, we derive game-theoretically optimal minimax privacy mechanisms, and show that the privacy mechanisms learned from data (in a generative adversarial fashion) match the theoretically optimal ones. This demonstrates that our framework can be easily applied in practice, even in the absence of dataset statistics._

    >Note: This is a very interesting paper showcasing the use of MI for protecting private attributes.


- Differentially Private Generative Adversarial Network
    <a name='Xie:18'></a>   
    [[Paper]](https://arxiv.org/pdf/1802.06739.pdf)

    _L Xie, K Lin, S Wang, F Wang, J Zhou (arXiv-2018)_

    >_Generative Adversarial Network (GAN) and its variants have recently attracted intensive research interests due to their elegant theoretical foundation and excellent empirical performance as generative models. These tools provide a promising direction in the studies where data availability is limited. One common issue in GANs is that the density of the learned generative distribution could concentrate on the training data points, meaning that they can easily remember training samples due to the high model complexity of deep networks. This becomes a major concern when GANs are applied to private or sensitive data such as patient medical records, and the concentration of distribution may divulge critical patient information. To address this issue, in this paper we propose a di erentially private GAN (DPGAN) model, in which we achieve di erential privacy in GANs by adding carefully designed noise to gradients during the learning procedure. We provide rigorous proof for the privacy guarantee, as well as comprehensive empirical evidence to support our analysis, where we demonstrate that our method can generate high quality data points at a reasonable privacy level._


- Generating Differentially Private Datasets Using GANs
    <a name='Triastcyn:18'></a>
    [[Paper]](https://openreview.net/forum?id=rJv4XWZA-&noteId=BynjVJaSG)

    _A Triastcyn, B Faltings (ArXiv-2018)_

    >[Comments]:
    - This is a rejected paper from ICLR 2018.
    - A new version was just (Jun, 4, 2018) deposited to the ArXiv. It seems that there was an error with the generation process and thus the whole data-generation process is not differentially private.
    - The privacy guarantees of the paper are not valid!

- Differentially Private Mixture of Generative Neural Networks
    <a name='Acs:17'></a>
    [[Paper]](https://arxiv.org/abs/1709.04514)

    _Gergely Acs, Luca Melis, Claude Castelluccia, Emiliano De Cristofaro (ICDM 2017)_

    >_Generative models are used in a wide range of applications building on large amounts of contextually rich information. Due to possible privacy violations of the individuals whose data is used to train these models, however, publishing or sharing generative models is not always viable. In this paper, we present a novel technique for privately releasing generative models and entire high-dimensional datasets produced by these models. We model the generator distribution of the training data with a mixture of k generative neural networks. These are trained together and collectively learn the generator distribution of a dataset. Data is divided into k clusters, using a novel differentially private kernel k-means, then each cluster is given to separate generative neural networks, such as Restricted Boltzmann Machines or Variational Autoencoders, which are trained only on their own cluster using differentially private gradient descent. We evaluate our approach using the MNIST dataset, as well as call detail records and transit datasets, showing that it produces realistic synthetic samples, which can also be used to accurately compute arbitrary number of counting queries._



## Generative Model for Private Data Synthesis
<a name='_dp_gen'></a>

[Jump to Top](#_content)

- Plausible Deniability for Privacy-Preserving Data Synthesis
    <a name='Bindschaedler:17'></a>
    [[Paper]](https://vbinds.ch/pdfs/vbindsch_VLDB2017.pdf)

    _Vincent Bindschaedler, Reza Shokri, Carl A. Gunter (VLDB 2017)_

    >_Releasing full data records is one of the most challenging problems in data privacy. On the one hand, many of the popular techniques such as data de-identification are proble- matic because of their dependence on the background knowledge of adversaries. On the other hand, rigorous methods such as the exponential mechanism for differential privacy are often computationally impractical to use for releasing high dimensional data or cannot preserve high utility of original data due to their extensive data perturbation.
    <br>
    This paper presents a criterion called plausible deniability that provides a formal privacy guarantee, notably for releasing sensitive datasets: an output record can be released only if a certain amount of input records are indistinguishable, up to a privacy parameter. This notion does not depend on the background knowledge of an adversary. Also, it can efficiently be checked by privacy tests. We present mechanisms to generate synthetic datasets with similar statistical properties to the input data and the same format. We study this technique both theoretically and experimentally. A key theoretical result shows that, with proper randomization, the plausible deniability mechanism generates differentially private synthetic data. We demonstrate the efficiency of this generative technique on a large dataset; it is shown to preserve the utility of original data with respect to various statistical analysis and machine learning measures._

- Coupling Random Orthonormal Projection with Gaussian Generative Model for Non-Interactive Private Data Release
    <a name='Chanyaswad:18'></a>
    [[Paper]](https://arxiv.org/pdf/1709.00054.pdf)
    [[Code]](https://github.com/inspire-group/RON-Gauss)

    _Thee Chanyaswad, Changchang Liu, Prateek Mittal (ArXiv 2018)_

    >_A key challenge facing the design of differential privacy in the non-interactive setting is to maintain the utility of the released data. To overcome this challenge, we utilize the Diaconis-Freedman-Meckes (DFM) effect, which states that most projections of high-dimensional data are nearly Gaussian. Hence, we propose the RON-Gauss model that leverages the novel combination of dimensionality reduction via random orthonormal (RON) projection and the Gaussian generative model for synthesizing differentially-private data. We analyze how RON-Gauss benefits from the DFM effect, and present multiple algorithms for a range of machine learning applications, including both unsupervised and supervised learning. Furthermore, we rigorously prove that (a) our algorithms satisfy the strong ϵ-differential privacy guarantee, and (b) RON projection can lower the level of perturbation required for differential privacy. Finally, we illustrate the effectiveness of RON-Gauss under three common machine learning applications -- clustering, classification, and regression -- on three large real-world datasets. Our empirical results show that (a) RON-Gauss outperforms previous approaches by up to an order of magnitude, and (b) loss in utility compared to the non-private real data is small. Thus, RON-Gauss can serve as a key enabler for real-world deployment of privacy-preserving data release._




## Other resources

### Tutorials 

### Slides

### Media-articles

