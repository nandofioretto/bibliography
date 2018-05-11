# Differential Privacy Papers Repository

This repo serves the purpose of organizing papers on Differential Privacy


## Content
<a name='_content'></a>

- [Books and Seminal Work](#_books)

- [Theory](#_theory_)

- [Mechanisms for Answering General Queries](#_dp_mechanisms)
	+ [Basic Mechanisms](#_basic_mechanisms)
	+ [Hierarchical Mechanisms](#_hierarchical_mechanisms)
	+ [Binning Mechanisms](#_binning_mechanisms)
	+ [Dimensionality Reduction Mechanisms]($_dimensionality_reduction_mechanisms)

- [Generative Models for Differential Privacy](#_dp_gen)

- [Systems supporting Differential Privacy](#_dp_systems)

- [Trajectory Data](#_trajectory_data)

- [Data Streams and Continuous Observations](#_continous_observations)

- [Machine Learning](#_machine_learning)
	+ [Adversarial Learning](#_adversarial_learning) 
	+ [Clustering](#_clustering) 
	+ [Decision Trees](#_decision_trees)
	+ [Generative Adversarial Networks](#_generative_adversarial_models)
	+ [Regression](#_regression)

- [Distributed Differential Privacy](#_distributed_dp)

- [Differential Privacy Model Extensions](#_dp_extensions)
	+ [Approximate Differential Privacy](#_approximate_dp)
	+ [Local Differential Privacy](#_local_dp)
	+ [Pan Privacy](#_pan_privacy)
	+ [Reni Differential Privacy](#)
	+ [Random Differential Privacy](#)


<!-- Differential Privacy Books and Seminal Papers -->

## Books and Seminal Work
<a name='_books'></a>

[Jump to Top](#_content)

- Differential Privacy: A Survey of Results	
	<a name="Dwork:08"></a>
	[[Paper]](http://web.cs.ucdavis.edu/~franklin/ecs289/2010/dwork_2008.pdf)

	_Cynthia Dwork (TAMC 2008)_

- A firm foundation for private data analysis
	<a name="Dwork:11"></a>
	[[Paper]](https://www.microsoft.com/en-us/research/wp-content/uploads/2011/01/dwork_cacm.pdf)
  
	_Cynthia Dwork (Communications of the ACM 2011)_

- The Algorithmic Foundations of Differential Privacy
	<a name="Dwork:14"></a>
	[[Paper]](https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf)
  
	_Cynthia Dwork, Aaron Roth (2014)_

- The Complexity of Differential Privacy
	<a name="Vadhan:17"></a>
	[[Paper]](https://privacytools.seas.harvard.edu/files/privacytools/files/complexityprivacy_1.pdf)

	_Salil Vadhan (Tutorials on the Foundations of Cryptography 2017)_

- Differential Privacy: A Primer for a Non-technical Audience
	<a name="Nissim:17"></a>
	[[Paper]](http://privacytools.seas.harvard.edu/files/privacytools/files/pedagogical-document-dp_0.pdf)
  
	_Kobbi Nissim†, Thomas Steinke, Alexandra Wood, Mark Bun, Marco Gaboardi,David R. O’Brien, and Salil Vadhan (2017)_


<!-- Differential Privacy Theory and useful results -->

## Theory
<a name='_theory_'></a>

[Jump to Top](#_content)

### Composition Theorems

- Our data, ourselves: Privacy via distributed noise generation	[Jump to link](#Dwork:06b)

    >[Comments]: Basic Composition.

- Calibrating Noise to Sensitivity in Private Data Analysis [Jump to link](#Dwork:06a)

    >[Comments]: Basic Composition.

- Boosting and differential privacy. 
	<a name="Dwork:10a"></a>
	[[Paper]](https://guyrothblum.files.wordpress.com/2014/11/drv10.pdf)

	_Cynthia Dwork, Guy N. Rothblum, Salil P. Vadhan (FOCS 2010)_

    >[Comments]: Advanced composition with Boosting

	>_Boosting is a general method for improving the accuracy of learning algorithms. We use boosting to construct privacy-preserving synopses of the input database. These are data structures that yield, for a given set Q of queries over an input database, reasonably accurate estimates of the responses to every query in Q. Given a base synopsis generator that takes a distribution on Q and produces a “weak” synopsis that yields “good” answers for a majority of the weight in Q, our Boosting for Queries algorithm obtains a synopsis that is good for all of Q. We ensure privacy for the rows of the database, but the boosting is performed on the queries. 
	We provide the first base synopsis generator for sets of arbitrary low-sensitivity queries, i.e., queries whose answers do not vary much under the addition or deletion of a single row. 
	Boosting is an iterative method. In our Boosting for Queries algorithm, each iteration incurs a certain privacy loss. In analyzing the cumulative privacy loss over many iterations, we obtain a bound on the expected privacy loss from a single ε-differentially private mechanism. Combining this with evolution of confidence arguments from the literature, we get a fresh perspective – and stronger bounds – on the expected cumulative privacy loss due to multiple mechanisms, each of which provides ε-differential privacy or one of its relaxations, and each of which operates on (potentially) different, adaptively chosen, databases.
	We can also view a database as a training set in a learning algorithm, where each row corresponds to an element in the training set. Given the power and prevalence of boosting, it is natural to search for boosting techniques that preserve the privacy properties of the base learner. We present a differentially private boosting technique, in which privacy comes at little additional cost in accuracy. We call this Boosting for People, since database rows corresponding to individual people are the elements of interest._

- The composition theorem for differential privacy 
	<a name="Kairouz:15"></a>
	[[Paper]](http://proceedings.mlr.press/v37/kairouz15.pdf)

	_Peter Kairouz, Sewoong Oh, and Pramod Viswanath (ICML 2015)_ 

    >[Comments]: The advanced composition theorem.

	>_Sequential querying of differentially private mechanisms degrades the overall privacy level. In this paper, we answer the fundamental question of characterizing the level of overall privacy degradation as a function of the number of queries and the privacy levels maintained by each privatization mechanism. Our solution is complete: we prove an upper bound on the overall privacy level and construct a sequence of privatization mechanisms that achieves this bound. The key innovation is the introduction of an operational interpretation of differential privacy (involving hypothesis testing) and the use of new data processing inequalities. Our result improves over the state-of-the-art and has immediate applications to several problems studied in the literature._

- The complexity of computing the optimal composition of differential privacy
	<a name="Murtagh:16"></a>
	[[Paper]](https://arxiv.org/abs/1507.03113)

	_Jack Murtagh, Salil P. Vadhan (TCC 2016)_
    >[Comments]: The advanced composition theorem.

    >[Comments]: The optimal composition theorem.

	>_In the study of differential privacy, composition theorems (starting with the original paper of Dwork, McSherry, Nissim, and Smith (TCC'06)) bound the degradation of privacy when composing several differentially private algorithms. Kairouz, Oh, and Viswanath (ICML'15) showed how to compute the optimal bound for composing k arbitrary (ϵ,δ)-differentially private algorithms. We characterize the optimal composition for the more general case of k arbitrary (ϵ1,δ1),…,(ϵk,δk)-differentially private algorithms where the privacy parameters may differ for each algorithm in the composition. We show that computing the optimal composition in general is #P-complete. Since computing optimal composition exactly is infeasible (unless FP=#P), we give an approximation algorithm that computes the composition to arbitrary accuracy in polynomial time. The algorithm is a modification of Dyer's dynamic programming approach to approximately counting solutions to knapsack problems (STOC'03)._

### Sampling

- What can we learn privately?
	<a name="Kasiviswanathan:11"></a>
	[[Paper]](https://arxiv.org/abs/0803.0924)

	_Shiva Prasad Kasiviswanathan, Homin K. Lee, Kobbi Nissim, Sofya Raskhodnikova, Adam Smith (SIAM J. Comput 2011)_

	>_Learning problems form an important category of computational tasks that generalizes many of the computations researchers apply to large real-life data sets. We ask: what concept classes can be learned privately, namely, by an algorithm whose output does not depend too heavily on any one input or specific training example? More precisely, we investigate learning algorithms that satisfy differential privacy, a notion that provides strong confidentiality guarantees in contexts where aggregate information is released about a database containing sensitive information about individuals. We demonstrate that, ignoring computational constraints, it is possible to privately agnostically learn any concept class using a sample size approximately logarithmic in the cardinality of the concept class. Therefore, almost anything learnable is learnable privately: specifically, if a concept class is learnable by a (non-private) algorithm with polynomial sample complexity and output size, then it can be learned privately using a polynomial number of samples. We also present a computationally efficient private PAC learner for the class of parity functions. Local (or randomized response) algorithms are a practical class of private algorithms that have received extensive investigation. We provide a precise characterization of local private learning algorithms. We show that a concept class is learnable by a local algorithm if and only if it is learnable in the statistical query (SQ) model. Finally, we present a separation between the power of interactive and noninteractive local learning algorithms._

#### Links and Resources 
- [Secrecy of the sample post](https://adamdsmith.wordpress.com/2009/09/02/sample-secrecy/)

<!-- Differential Privacy Mechanisms -->

## Mechanisms for Answering General Queries
<a name='_dp_mechanisms'></a>

[Jump to Top](#_content)

<!-- Basic Mechanisms -->

### Basic Mechanisms
<a name='_basic_mechanisms'></a>

[Jump to Top](#_content)

- Calibrating Noise to Sensitivity in Private Data Analysis
	<a name="Dwork:06a"></a>
	[[Paper]](http://people.csail.mit.edu/asmith/PS/sensitivity-tcc-final.pdf)

	_Cynthia Dwork, Frank McSherry, Kobbi Nissim, Adam Smith (TCC 2006)_

    >[Comments]: The *Laplace Mechanism*.

	>_We continue a line of research initiated in [10,11]on privacy-preserving statistical databases. Consider a trusted server that holds a database of sensitive information. Given a query function f mapping databases to reals, the so-called true answer is the result of applying f to the database. To protect privacy, the true answer is perturbed by the addition of random noise generated according to a carefully chosen distribution, and this response, the true answer plus noise, is returned to the user.
	Previous work focused on the case of noisy sums, in which f = ∑ig(xi), where xi deComments the ith row of the database and g maps database rows to [0,1]. We extend the study to general functions f, proving that privacy can be preserved by calibrating the standard deviation of the noise according to the sensitivity of the function f. Roughly speaking, this is the amount that any single argument to f can change its output. The new analysis shows that for several particular applications substantially less noise is needed than was previously understood to be the case.
	The first step is a very clean characterization of privacy in terms of indistinguishability of transcripts. Additionally, we obtain separation results showing the increased value of interactive sanitization mechanisms over non-interactive._

- A discrete analogue of the Laplace distribution.
	<a name="Inusaha:06"></a>
	[[Paper]](https://www.sciencedirect.com/science/article/pii/S0378375804003519)

	_Seidu Inusaha, Tomasz J.Kozubowski (Journal of Statistical Planning and Inference 2006)_

	> [Comments]: The paper introduces the discrete Laplace distribution.

	>_Following Kemp (J. Statist. Plann. Inference 63 (1997) 223) who defined a discrete analogue of the normal distribution, we derive a discrete version of the Laplace (double exponential) distribution. In contrast with the discrete normal case, here closed-form expressions are available for the probability density function, the distribution function, the characteristic function, the mean, and the variance. We show that this discrete distribution on integers shares many properties of the classical Laplace distribution on the real line, including unimodality, infinite divisibility, closure properties with respect to geometric compounding, and a maximum entropy property. We also discuss statistical issues of estimation under the discrete Laplace model._

- Mechasim Design via Differential Privacy
	<a name='McSherry:07'></a>
	[[Paper]](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/mdviadp.pdf)

	_F. McSherry, K. Talwar (FOCS 2007)_

	>[Comments]: The *Exponential Mechanism*.

	>_We study the role that privacy-preserving algorithms, which prevent the leakage of speciﬁc information about participants, can play in the design of mechanisms for strategic agents, which must encourage players to honestly report information. Speciﬁcally, we show that the recent notion of differential privacy [15, 14], in addition to its own intrinsic virtue, can ensure that participants have limited effect on the outcome of the mechanism, and as a consequence have limited incentive to lie. More precisely, mechanisms with differential privacy are approximate dominant strategy under arbitrary player utility functions, are automatically resilient to coalitions, and easily allow repeatability. We study several special cases of the unlimited supply auction problem, providing new results for digital goods auctions, attribute auctions, and auctions with arbitrary structural constraints on the prices. As an important prelude to developing a privacy-preserving auction mechanism, we introduce and study a generalization of previous privacy work that accommodates the high sensitivity of the auction setting, where a single participant may dramatically alter the optimal ﬁxed price, and a slight change in the offered price may take the revenue from optimal to zero._

- A Multiplicative Weights Mechanism for Privacy-Preserving Data Analysis
	<a name="hardt:10"></a>
	[[Paper]](http://ieeexplore.ieee.org/document/5670948/)

	_Moritz Hardt, Guy N. Rothblum (FOCS 2010)_

	> [Comments]: The paper introduces the *Multiplicative Weights* (MW) Mechanism. It explits the composition theorem to answer queries interactively, by casting the query release problem as an online _learning problem_.

	>_We consider statistical data analysis in the interactive setting. In this setting a trusted curator maintains a database of sensitive information about individual participants, and releases privacy-preserving answers to queries as they arrive. Our primary contribution is a new differentially private multiplicative weights mechanism for answering a large number of interactive counting (or linear) queries that arrive online and may be adaptively chosen. This is the first mechanism with worst-case accuracy guarantees that can answer large numbers of interactive queries and is efficient (in terms of the runtime's dependence on the data universe size). The error is asymptotically optimal in its dependence on the number of participants, and depends only logarithmically on the number of queries being answered. The running time is nearly linear in the size of the data universe. As a further contribution, when we relax the utility requirement and require accuracy only for databases drawn from a rich class of databases, we obtain exponential improvements in running time. Even in this relaxed setting we continue to guarantee privacy for any input database. Only the utility requirement is relaxed. Specifically, we show that when the input database is drawn from a smooth distribution — a distribution that does not place too much weight on any single data item — accuracy remains as above, and the running time becomes poly-logarithmic in the data universe size. The main technical contributions are the application of multiplicative weights techniques to the differential privacy setting, a new privacy analysis for the interactive setting, and a technique for reducing data dimensionality for databases drawn from smooth distributions._

- A Simple and Practical Algorithm for Differentially Private Data Release
	<a name="Hardt:12"></a>
	[[Paper]](http://mrtz.org/papers/mwem.pdf)

	_Moritz Hardt, Katrina Ligett, Frank McSherry (NIPS 2012)_

	>[Comments]: The *MWEM Mechanism*.
	> It is a data independent mechanism.

	>_We present a new algorithm for differentially private data release, based on a simple combination of the Exponential Mechanism with the Multiplicative Weights update rule. Our MWEM algorithm achieves what are the best known and nearly optimal theoretical guarantees, while at the same time being simple to implement and experimentally more accurate on actual data sets than existing techniques._


<!-- Hierarchical Mechanisms -->

### Hierarchical Methods
<a name='_hierarchical_mechanisms'></a>

[Jump to Top](#_content) 

- Boosting the Accuracy of Differentially-Private Histograms Through Consistency
	<a name='Hay:10'></a>
	[[Paper]](http://www.vldb.org/pvldb/vldb2010/papers/R91.pdf)
	
	_Michael Hay, Vibhor Rastogi, Gerome Miklau, Dan Suciu (VLDB 2010)_

	>[Comments]: The *H2 Mechanism*.
	<br>
	>[Category]: Hierarchical, data-independent mechanism.

	>_We show that it is possible to significantly improve the accuracy of a general class of histogram queries while satisfying differential privacy. Our approach carefully chooses a set of queries to evaluate, and then exploits consistency constraints that should hold over the noisy output. In a post-processing phase, we compute the consistent input most likely to have produced the noisy output. The final output is differentially-private and consistent, but in addition, it is often much more accurate. We show, both theoretically and experimentally, that these techniques can be used for estimating the degree sequence of a graph very precisely, and for computing a histogram that can support arbitrary range queries accurately._

- Optimizing Histogram Queries under Differential Privacy
	<a name='Li:10'></a>
	[[Paper]](https://people.cs.umass.edu/~mcgregor/papers/10-pods.pdf)

	_Chao Li, Michael Hay, Vibhor Rastogi, Gerome Miklau, Andrew McGregor (PODS 2010)_

	>[Comments]: The *Greedy H Mechanism*.
	> It is a data independent mechanism.
	<br>
	>[Category]: Hierarchical, data-independent mechanism.

	>_Differential privacy is a robust privacy standard that has been successfully applied to a range of data analysis tasks. But despite much recent work, optimal strategies for answering a collection of related queries are not known.
	We propose the matrix mechanism, a new algorithm for answering a workload of predicate counting queries. Given a workload, the mechanism requests answers to a different set of queries, called a query strategy, which are answered using the standard Laplace mechanism. Noisy answers to the workload queries are then derived from the noisy answers to the strategy queries. This two stage process can result in a more complex correlated noise distribution that preserves differential privacy but increases accuracy.
	We provide a formal analysis of the error of query answers produced by the mechanism and investigate the problem of computing the optimal query strategy in support of a given workload. We show this problem can be formulated as a rank-constrained semidefinite program. Finally, we analyze two seemingly distinct techniques, whose similar behavior is explained by viewing them as instances of the matrix mechanism._

- Optimizing linear counting queries under differential privacy
	<a name='Qardaji:13'></a>
	[[Paper]](http://www.vldb.org/pvldb/vol6/p1954-qardaji.pdf)

	_Wahbeh Qardaji, Weining Yang, Ninghui Li (VLDB 2013)_

	>[Comments]: The *Hb Mechanism*.
	<br>
	>[Category]: Hierarchical, data-independent mechanism.

	>_In recent years, many approaches to differentially privately publish histograms have been proposed. Several approaches rely on constructing tree structures in order to decrease the error when answer large range queries. In this paper, we examine the factors affecting the accuracy of hierarchical approaches by studying the mean squared error (MSE) when answering range queries. We start with one-dimensional histograms, and analyze how the MSE changes with different branching factors, after employing constrained inference, and with different methods to allocate the privacy budget among hierarchy levels. Our analysis and experimental results show that combining the choice of a good branching factor with constrained inference outperform the current state of the art. Finally, we extend our analysis to multi-dimensional histograms. We show that the benefits from employing hierarchical methods beyond a single dimension are significantly diminished, and when there are 3 or more dimensions, it is almost always better to use the Flat method instead of a hierarchy._

- The matrix mechanism: optimizing linear counting queries under differential privacy
	<a name='Li:15'></a>
	[[Paper]](http://cs.colgate.edu/~mhay/pdfs/li2015optimizing.pdf)

	_Chao Li, Gerome Miklau, Michael Hay, Andrew McGregor, Vibhor Rastogi (VLDB Journal 2015)_

	>[Comments]: The *Matrix Mechanism*. It generalizes several mechanisms able to answer linear counting queries.
	<br>
	>[Category]: Data-independent mechanism.

	>_Differential privacy is a robust privacy standard that has been successfully applied to a range of data analysis tasks. We describe the matrix mechanism, an algorithm for answering a workload of linear counting queries that adapts the noise distribution to properties of the provided queries. Given a workload, the mechanism uses a different set of queries, called a query strategy, which are answered using a standard Laplace or Gaussian mechanism. Noisy answers to the workload queries are then derived from the noisy answers to the strategy queries. This two-stage process can result in a more complex, correlated noise distribution that preserves differential privacy but increases accuracy. We provide a formal analysis of the error of query answers produced by the mechanism and investigate the problem of computing the optimal query strategy in support of a given workload. We show that this problem can be formulated as a rank-constrained semidefinite program. We analyze two seemingly distinct techniques proposed in the literature, whose similar behavior is explained by viewing them as instances of the matrix mechanism. We also describe an extension of the mechanism in which nonnegativity constraints are included in the derivation process and provide experimental evidence of its efficacy._

- DPCube (data dependent)

- QuadTree (data dependent)

- Differentially private grids for geospatial data
	<a name='Qardaji:13'></a>
    [[Paper]](https://arxiv.org/pdf/1209.1322.pdf)

    _Wahbeh Qardaji, Weining Yang, Ninghui Li (ICDE 2013)_
    
    >[Comments]: The *UGrid* and *AGrid* mechanisms to answer 2D queries.
    <br>
    >[Category]: Data-dependent, hierarchical, and based on non-interactive (UGrid) and interactive (AGrid) grid partitioning. 
    
    >_In this paper, we tackle the problem of constructing a differentially private synopsis for two-dimensional datasets such as geospatial datasets. The current state-of-the-art methods work by performing recursive binary partitioning of the data domains, and constructing a hierarchy of partitions. We show that the key challenge in partition-based synopsis methods lies in choosing the right partition granularity to balance the noise error and the non-uniformity error. We study the uniform-grid approach, which applies an equi-width grid of a certain size over the data domain and then issues independent count queries on the grid cells. This method has received no attention in the literature, probably due to the fact that no good method for choosing a grid size was known. Based on an analysis of the two kinds of errors, we propose a method for choosing the grid size. Experimental results validate our method, and show that this approach performs as well as, and often times better than, the state-of-the-art methods. We further introduce a novel adaptive-grid method. The adaptive grid method lays a coarse-grained grid over the dataset, and then further partitions each cell according to its noisy count. Both levels of partitions are then used in answering queries over the dataset. This method exploits the need to have finer granularity partitioning over dense regions and, at the same time, coarse partitioning over sparse regions. Through extensive experiments on real-world datasets, we show that this approach consistently and significantly outperforms the uniform-grid method and other state-of-the-art methods._


<!-- Binning Mechanisms -->

### Binning Strategies  (todo)
<a name='_binning_mechanisms'></a>

[Jump to Top](#_content) 

- AHP (data dependent)

- DAWA (data dependent)


<!-- Dimensionality-Reduction Mechanisms -->

### Dimensionality reduction  (todo)
<a name='_dimensionality_reduction_mechanisms'></a>

[Jump to Top](#_content) 

- Privelet (data independent)

- PHP (data dependent)


<!-- Generative Models for Differential Privacy -->

## Generative Models for Differential Privacy
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



<!-- Differential Privacy Mechanisms -->

## Systems supporting Differential Privacy
<a name='_dp_systems'></a>

[Jump to Top](#_content)

- Differential privacy for collaborative security
	<a name='Reed:10'></a>
	[[Paper]](http://www.cis.upenn.edu/~bcpierce/papers/eurosec2010.pdf)

	_Jason Reed, Adam J. Aviv, Daniel Wagner, Andreas Haeberlen, Benjamin C. Pierce, Jonathan M. Smith (EUROSEC 2010)_

    >_Fighting global security threats with only a local view is inherently difficult. Internet network operators need to fight global phenomena such as botnets, but they are hampered by the fact that operators can observe only the traffic in their local domains. We propose a collaborative approach to this problem, in which operators share aggregate information about the traffic in their respective domains through an automated query mechanism. We argue that existing work on differential privacy and type systems can be leveraged to build a programmable query mechanism that can express a wide range of queries while limiting what can be learned about individual customers. We report on our progress towards building such a mechanism, and we discuss opportunities and challenges of the collaborative security approach._

- Differential Privacy Under Fire
	<a name='Haeberlen:11'></a>
	[[Paper]](https://www.usenix.org/legacy/event/sec11/tech/full_papers/Haeberlen.pdf)

	_Andreas Haeberlen, Benjamin C. Pierce, Arjun Narayan (USENIX 2011)_

	>_Anonymizing private data before release is not enough to reliably protect privacy, as Netflix and AOL have learned to their cost. Recent research on differential privacy opens a way to obtain robust, provable privacy guarantees, and systems like PINQ and Airavat now offer convenient frameworks for processing arbitrary userspecified queries in a differentially private way. However, these systems are vulnerable to a variety of covertchannel attacks that can be exploited by an adversarial querier.
	<br>
	We describe several different kinds of attacks, all feasible in PINQ and some in Airavat. We discuss the space of possible countermeasures, and we present a detailed design for one specific solution, based on a new primitive we call predictable transactions and a simple differentially private programming language. Our evaluation, which relies on a proof-of-conceptimplementation based on the Caml Light runtime, shows that our design is effective against remotely exploitable covert channels, at the expense of a higher query completion time._

- GUPT: Privacy Preserving Data Analysis Made Easy
	<a name='Mohan:12'></a>

	_Prashanth Mohan, Abhradeep Thakurta, Elaine Shi, Dawn Song, David E. Culler (SIGMOD 2012)_

	>_It is often highly valuable for organizations to have their data analyzed by external agents. However, any program that computes on potentially sensitive data risks leaking information through its output. Differential privacy provides a theoretical framework for processing data while protecting the privacy of individual records in a dataset. Unfortunately, it has seen limited adoption because of the loss in output accuracy, the difficulty in making programs differentially private, lack of mechanisms to describe the privacy budget in a programmer’s utilitarian terms, and the challenging requirement that data owners and data analysts manually distribute the limited privacy budget between queries. 
	This paper presents the design and evaluation of a new system, GUPT, that overcomes these challenges. Unlike existing differentially private systems such as PINQ and Airavat, it guarantees differential privacy to programs not developed with privacy in mind, makes no trust assumptions about the analysis program, and is secure to all known classes of side-channel attacks. 
	GUPT uses a new model of data sensitivity that degrades privacy of data over time. This enables efficient allocation of different levels of privacy for different user applications while guaranteeing an overall constant level of privacy and maximizing the utility of each application. GUPT also introduces techniques that improve the accuracy of output while achieving the same level of privacy. These approaches enable GUPT to easily execute a wide variety of data analysis programs while providing both utility and privacy._

- Formal Verification of Differential Privacy for Interactive Systems - Extended Abstract
	<a name='Barthe:13'></a>
	[[Paper]](https://www.sciencedirect.com/science/article/pii/S157106611100106X)

	_Michael Carl Tschantz, Dilsun Kaynar, and Anupam Datta (Electronic Notes in Theoretical Computer Science 2011)_

	>_Differential privacy is a promising approach to privacy preserving data analysis with a well-developed theory for functions. Despite recent work on implementing systems that aim to provide differential privacy, the problem of formally verifying that these systems have differential privacy has not been adequately addressed. We develop a formal probabilistic automaton model of differential privacy for systems by adapting prior work on differential privacy for functions. We present the first sound verification technique for proving differential privacy of interactive systems. The technique is based on a form of probabilistic bisimulation relation. The novelty lies in the way we track quantitative privacy leakage bounds using a relation family instead of a single relation. We illustrate the proof technique on a representative automaton motivated by PINQ, an implemented system that is intended to provide differential privacy. Surprisingly, our analysis yields a privacy leakage bound of (2t ∗ \epsilon) rather than (t ∗ \epsilon) when \epsilon-differentially private functions are called t times. The extra leakage arises from accounting for bounded memory constraints of real computers._

- Probabilistic Relational Reasoning for Differential Privacy
	<a name='Barthe:13'></a>
	[[Paper]](http://certicrypt.gforge.inria.fr/2012.POPL.pdf)

	_Gilles Barthe, Boris Köpf, Federico Olmedo, Santiago Zanella-Béguelin (TOPLAS 2013)_

	>_Differential privacy is a notion of confidentiality that allows useful computations on sensible data while protecting the privacy of individuals. Proving differential privacy is a difficult and error-prone task that calls for principled approaches and tool support. Approaches based on linear types and static analysis have recently emerged; however, an increasing number of programs achieve privacy using techniques that fall out of their scope. Examples include programs that aim for weaker, approximate differential privacy guarantees and programs that achieve differential privacy without using any standard mechanisms. Providing support for reasoning about the privacy of such programs has been an open problem.
	<br>
	We report on CertiPriv, a machine-checked framework for reasoning about differential privacy built on top of the Coq proof assistant. The central component of CertiPriv is a quantitative extension of probabilistic relational Hoare logic that enables one to derive differential privacy guarantees for programs from first principles. We demonstrate the applicability of CertiPriv on a number of examples whose formal analysis is out of the reach of previous techniques. In particular, we provide the first machine-checked proofs of correctness of the Laplacian, Gaussian, and exponential mechanisms and of the privacy of randomized and streaming algorithms from the literature._

- PSI: a Private data Sharing Interface
	<a name='Gaboardi:16'></a>
	[[Paper]](https://arxiv.org/abs/1609.04340)

	_Marco Gaboardi, James Honaker, Gary King, Jack Murtagh, Kobbi Nissim, Jonathan Ullman, Salil Vadhan (ArXiv 2016)_

	>_We provide an overview of PSI ("a Private data Sharing Interface"), a system we are developing to enable researchers in the social sciences and other fields to share and explore privacy-sensitive datasets with the strong privacy protections of differential privacy._

- Differential Privacy: Now it's Getting Personal
	<a name='Ebadi:16'></a>
	[[Paper]](https://dl.acm.org/citation.cfm?id=2677005)

	_Hamid Ebadi, David Sands, Gerardo Schneider (POPL 2015)_

	>_Differential privacy provides a way to get useful information about sensitive data without revealing much about any one individual. It enjoys many nice compositionality properties not shared by other approaches to privacy, including, in particular, robustness against side-knowledge.
	<br>
	Designing differentially private mechanisms from scratch can be a challenging task. One way to make it easier to construct new differential private mechanisms is to design a system which allows more complex mechanisms (programs) to be built from differentially private building blocks in principled way, so that the resulting programs are guaranteed to be differentially private by construction.
	<br>
	This paper is about a new accounting principle for building differentially private programs. It is based on a simple generalisation of classic differential privacy which we call Personalised Differential Privacy (PDP). In PDP each individual has its own personal privacy level. We describe ProPer, a interactive system for implementing PDP which maintains a privacy budget for each individual. When a primitive query is made on data derived from individuals, the provenance of the involved records determines how the privacy budget of an individual is affected: the number of records derived from Alice determines the multiplier for the privacy decrease in Alice's budget. This offers some advantages over previous systems, in particular its fine-grained character allows better utilisation of the privacy budget than mechanisms based purely on the concept of global sensitivity, and it applies naturally to the case of a live database where new individuals are added over time.
	<br>
	We provide a formal model of the ProPer approach, prove that it provides personalised differential privacy, and describe a prototype implementation based on McSherry's PINQ system._

- Programming language techniques for differential privacy
	<a name='Barthe:16'></a>
	[[Paper]](https://siglog.hosting.acm.org/wp-content/uploads/2016/01/siglog_news_7.pdf)

	_Gilles Barthe, Marco Gaboardi, Justin Hsu, Benjamin Pierce (SIGLOG News 2016)_

	>_Differential privacy is rigorous framework for stating and enforcing privacy guarantees on computations over sensitive data. Informally, differential privacy ensures that the presence or absence of a single individual in a database has only a negligible statistical effect on the computation’s result. Many specific algorithms have been proved differentially private, but manually checking that a given program is differentially private can be subtle, tedious, or both. This approach becomes unfeasible when larger programs are considered. 
	<br>
	This situation has motivated research in developing techniques for assisting programmers in building differentially private applications. We survey a range of approaches based on ideas from programming language research, discussing the formal guarantees that each of these approaches provides and showing how each can be used to ensure differential privacy in practice._

- A framework for adaptive differential privacy
	<a name='Winograd-Cort:17'></a>
	[[Paper]](http://www.cis.upenn.edu/~ahae/papers/adafuzz-icfp2017.pdf)

	_Daniel Winograd-Cort, Andreas Haeberlen, Aaron Roth, Benjamin C. Pierce (ACM on Programming Languages 2017)_

	>_Differential privacy is a widely studied theory for analyzing sensitive data with a strong privacy guaranteeâany change in an individualâs data can have only a small statistical effect on the results and a growing number of programming languages now support differentially private data analysis. A common shortcoming of these languages is poor support for adaptivity. In practice, a data analyst rarely wants to run just one function over a sensitive database, nor even a predetermined sequence of functions with fixed privacy parameters; rather, she wants to engage in an interaction where, at each step, both the choice of the next function and its privacy parameters are informed by the results of prior functions. Existing languages support this scenario using a simple composition theorem, which often gives rather loose bounds on the actual privacy cost of composite functions, substantially reducing how much computation can be performed within a given privacy budget. The theory of differential privacy includes other theorems with much better bounds, but these have not yet been incorporated into programming languages.
	<br>
	We propose a novel framework for adaptive composition that is elegant, practical, and implementable. It consists of a reformulation based on typed functional programming of privacy filters, together with a concrete realization of this framework in the design and implementation of a new language, called Adaptive Fuzz. Adaptive Fuzz transplants the core static type system of Fuzz to the adaptive setting by wrapping the Fuzz typechecker and runtime system in an outer adaptive layer, allowing Fuzz programs to be conveniently constructed and typechecked on the fly. We describe an interpreter for Adaptive Fuzz and report results from two case studies demonstrating its effectiveness for implementing common statistical algorithms over real data sets._

- Sensitivity Analysis for Non-Interactive Differential Privacy: Bounds and Efficient Algorithms
	<a name='Inan:17'></a>
	[[Paper]](http://ieeexplore.ieee.org/document/7999165/)

	_Ali Inan, Mehmet Emre Gursoy, Yucel Saygin (IEEE Transactions on Dependable and Secure Computing 2017)_

	>_Differential privacy (DP) has gained significant attention lately as the state of the art in privacy protection. It achieves privacy by adding noise to query answers. We study the problem of privately and accurately answering a set of statistical range queries in batch mode (i.e., under non-interactive DP). The noise magnitude in DP depends directly on the sensitivity of a query set, and calculating sensitivity was proven to be NP-hard. Therefore, efficiently bounding the sensitivity of a given query set is still an open research problem. In this work, we propose upper bounds on sensitivity that are tighter than those in previous work. We also propose a formulation to exactly calculate sensitivity for a set of COUNT queries. However, it is impractical to implement these bounds without sophisticated methods. We therefore introduce methods that build a graph model G based on a query set Q, such that implementing the aforementioned bounds can be achieved by solving two well-known clique problems on G. We make use of the literature in solving these clique problems to realize our bounds efficiently. Experimental results show that for query sets with a few hundred queries, it takes only a few seconds to obtain results._


#### Links and Resources

- [Harvard University Privacy Tools Project](https://privacytools.seas.harvard.edu/)
- [DataTags](https://datatags.org/)
- [PSI](https://beta.dataverse.org/custom/DifferentialPrivacyPrototype/)
- [DP-comp](https://www.dpcomp.org/)


<!-- Trajectory Data -->

## Trajectory Data
<a name="_trajectory_data"></a>

[Jump to Top](#_content)

- Lclean: A Plausible Approach to Individual Trajectory Data Sanitization
	<a name="Han:18"></a>
	[[Paper]](https://arxiv.org/pdf/1804.01818.pdf)

	_Qilong Han,Dan Lu, Kejia Zhang, Xiaojiang Du, Mohsen Guizani (ArXiv 2018)_

	>_In recent years, with the continuous development of significant data industrialization, trajectory data have more and more critical analytical value for urban construction and environmental monitoring. However, the trajectory contains a lot of personal privacy, and rashly publishing trajectory data set will cause serious privacy leakage risk. At present, the privacy protection of trajectory data mainly uses the methods of data anonymity and generalization, without considering the background knowledge of attackers and ignores the risk of adjacent location points may leak sensitive location points. In this paper, based on the above problems, combined with the location correlation of trajectory data, we proposed a plausible replacement method. Firstly, the correlation of trajectory points is proposed to classify the individual trajectories containing sensitive points. Then, according to the relevance of location points and the randomized response mechanism, a reasonable candidate set is selected to replace the sensitive points in the trajectory to satisfy the local differential privacy. Theoretical and experimental results show that the proposed method not only protects the sensitive information of individuals, but also does not affect the overall data distribution_



<!-- Data-streams and Temporal Data -->

## Data Streams and Continous Observations
<a name='_continous_observations'></a>

[Jump to Top](#_content)

-  Time series compressibility and privacy
	<a name='Papadimitriou:07'></a>
	[[Paper]](https://pdfs.semanticscholar.org/758f/3023f29a59646d186c544e536d9fbeb0611a.pdf )

	_Spiros Papadimitriou, Feifei Li, George Kollios, Philip S Yu (2007)_

	>_In this paper we study the trade-offs between time series compressibility and partial information hiding and their fundamental implications on how we should introduce uncertainty about individual values by perturbing them. More specifically, if the perturbation does not have the same compressibility properties as the original data, then it can be detected and filtered out, reducing uncertainty. Thus, by making the perturbation “similar” to the original data, we can both preserve the structure of the data better, while simultaneously making breaches harder. However, as data become more compressible, a fraction of the uncertainty can be removed if true values are leaked, revealing how they were perturbed. We formalize these notions, study the above trade-offs on real data and develop practical schemes which strike a good balance and can also be extended for on-the-fly data hiding in a streaming environment._


- Pan-Private Streaming Algorithms [Jump to link](#Dwork:09)

- Differential Privacy under Continual Observation 
	<a name='Dwork:10b'></a>
	[[Paper]](https://www.cs.toronto.edu/~toni/Papers/dp-observation.pdf)

	_Cynthia Dwork, Moni Naor, Toniann Pitassi, Guy N. Rothblum (STOC 2010)_

    >[Comments]: Event based privacy.

	>_Differential privacy is a recent notion of privacy tailored to privacy-preserving data analysis [11]. Up to this point, research on differentially private data analysis has focused on the setting of a trusted curator holding a large, static, data set; thus every computation is a "one-shot" object: there is no point in computing something twice, since the result will be unchanged, up to any randomness introduced for privacy. However, many applications of data analysis involve repeated computations, either because the entire goal is one of monitoring, e.g., of traffic conditions, search trends, or incidence of influenza, or because the goal is some kind of adaptive optimization, e.g., placement of data to minimize access costs. In these cases, the algorithm must permit continual observation of the system's state. We therefore initiate a study of differential privacy under continual observation. We identify the problem of maintaining a counter in a privacy preserving manner and show its wide applicability to many different problems._

- Differential privacy in new settings
	<a name='Dwork:10c'></a>
	[[Paper]](https://www.microsoft.com/en-us/research/wp-content/uploads/2010/01/dwork_soda10.pdf)

	_Cynthia Dwork, Moni Naor, Toniann Pitassi, Guy N. Rothblum (SODA 2010)_

    >[Comments]: Pan privacy and Event based privacy.

	>_Differential privacy is a recent notion of privacy tailored to the problem of statistical disclosure control: how to release statistical information about a set of people without compromising the the privacy of any individual [7].
	We describe new work [10, 9] that extends differentially private data analysis beyond the traditional setting of a trusted curator operating, in perfect isolation, on a static dataset. We ask:
		- How can we guarantee differential privacy, even against an adversary that has access to the algorithm's internal state, eg, by subpoena? An algorithm that achives this is said to be pan-private.
		- How can we guarantee differential privacy when the algorithm must continually produce outputs? We call this differential privacy under continual observation.
	<br>
	We also consider these requirements in conjunction._

- Differentially private aggregation of distributed time-series with transformation and encryption
	<a name="Rastogi:10"></a>
	[[Paper]](https://dl.acm.org/citation.cfm?id=1807247)

	_Vibhor Rastogi, Suman Nath (SIGMOD 2010)_

	>_We propose the first differentially private aggregation algorithm for distributed time-series data that offers good practical utility without any trusted server. This addresses two important challenges in participatory data-mining applications where (i) individual users collect temporally correlated time-series data (such as location traces, web history, personal health data), and (ii) an untrusted third-party aggregator wishes to run aggregate queries on the data. To ensure differential privacy for time-series data despite the presence of temporal correlation, we propose the Fourier Perturbation Algorithm (FPAk). Standard differential privacy techniques perform poorly for time-series data. To answer n queries, such techniques can result in a noise of Θ(n) to each query answer, making the answers practically useless if n is large. Our FPAk algorithm perturbs the Discrete Fourier Transform of the query answers. For answering n queries, FPAk improves the expected error from Θ(n) to roughly Θ(k) where k is the number of Fourier coefficients that can (approximately) reconstruct all the n query answers. Our experiments show that k << n for many real-life data-sets resulting in a huge error-improvement for FPAk. 
	<br>
	To deal with the absence of a trusted central server, we propose the Distributed Laplace Perturbation Algorithm (DLPA) to add noise in a distributed way in order to guarantee differential privacy. To the best of our knowledge, DLPA is the first distributed differentially private algorithm that can scale with a large number of users: DLPA outperforms the only other distributed solution for differential privacy proposed so far, by reducing the computational load per user from O(U) to O(1) where U is the number of users._

- Pan-private algorithms via statistics on sketches
	<a name='Mir:11'></a>
	[[Paper]](https://www.cs.rutgers.edu/~rwright1/Publications/pods11.pdf)

	_Darakhshan Mir, S. Muthukrishnan, Aleksandar Nikolov, Rebecca N. Wright (PODS 2011)_

	>_Consider fully dynamic data, where we track data as it gets inserted and deleted. There are well developed notions of private data analyses with dynamic data, for example, using differential privacy. We want to go beyond privacy, and consider privacy together with security, formulated recently as pan-privacy by Dwork et al. (ICS 2010). Informally, pan-privacy preserves differential privacy while computing desired statistics on the data, even if the internal memory of the algorithm is compromised (say, by a malicious break-in or insider curiosity or by fiat by the government or law).
	<br/>
	We study pan-private algorithms for basic analyses, like estimating distinct count, moments, and heavy hitter count, with fully dynamic data. We present the first known pan-private algorithms for these problems in the fully dynamic model. Our algorithms rely on sketching techniques popular in streaming: in some cases, we add suitable noise to a previously known sketch, using a novel approach of calibrating noise to the underlying problem structure and the projection matrix of the sketch; in other cases, we maintain certain statistics on sketches; in yet others, we define novel sketches. We also present the first known lower bounds explicitly for pan privacy, showing our results to be nearly optimal for these problems. Our lower bounds are stronger than those implied by differential privacy or dynamic data streaming alone and hold even if unbounded memory and/or unbounded processing time are allowed. The lower bounds use a noisy decoding argument and exploit a connection between pan-private algorithms and data sanitization._

- Private and Continual Release of Statistics
	<a name='Chan:11'></a>
	[[Paper]](https://eprint.iacr.org/2010/076.pdf)

	_T.-H. Hubert Chan, Elaine Shi, Dawn Song (TISSEC 2011)_

	>_We ask the question: how can Web sites and data aggregators continually release updated statistics, and meanwhile preserve each individual user’s privacy? Suppose we are given a stream of 0’s and 1’s. We propose a differentially private continual counter that outputs at every time step the approximate number of 1’s seen thus far. Our counter construction has error that is only poly-log in the number of time steps. We can extend the basic counter construction to allow Web sites to continually give top-k and hot items suggestions while preserving users’ privacy._

- Differentially private continual monitoring of heavy hitters from distributed streams
	<a name='Chan:12'></a>
	[[Paper]](https://eprint.iacr.org/2012/218.pdf)

	_T-H. Hubert Chan, Mingfei Li, Elaine Shi, and Wenchang Xu (PETS 2012)_

	>_We consider applications scenarios where an untrusted aggregator wishes to continually monitor the heavy-hitters across a set of distributed streams. Since each stream can contain sensitive data, such as the purchase history of customers, we wish to guarantee the privacy of each stream, while allowing the untrusted aggregator to accurately detect the heavy hitters and their approximate frequencies. Our protocols are scalable in settings where the volume of streaming data is large, since we guarantee low memory usage and processing overhead by each data source, and low communication overhead between the data sources and the aggregator._

- Real-time Aggregate Monitoring with Differential Privacy
	<a name='Fan:12'></a>
	[[Paper]](https://dl.acm.org/citation.cfm?id=2398595)

	_Liyue Fan, Li Xiong (CIKM 2012)_ 

    >[Comments]: Extended in [Fan:14](#Fan:14).

	>_Sharing real-time aggregate statistics of private data has given much benefit to the public to perform data mining for understanding important phenomena, such as Influenza outbreaks and traffic congestion. However, releasing time-series data with standard differential privacy mechanism has limited utility due to high correlation between data values. We propose FAST, an adaptive system to release real-time aggregate statistics under differential privacy with improved utility. To minimize overall privacy cost, FAST adaptively samples long time-series according to detected data dynamics. To improve the accuracy of data release per time stamp, filtering is used to predict data values at non-sampling points and to estimate true values from noisy observations at sampling points. Our experiments with three real data sets confirm that FAST improves the accuracy of time-series release and has excellent performance even under very small privacy cost._

- Private decayed predicate sums on streams
	<a name='Bolt:13'></a>
	[[Paper]](https://dl.acm.org/citation.cfm?id=2448530)

	_Jean Bolot, Nadia Fawaz, S. Muthukrishnan, Aleksandar Nikolov, Nina Taft (ICDT 2013)_

	>_In many monitoring applications, recent data is more important than distant data. How does this affect privacy of data analysis? We study a general class of data analyses --- predicate sums --- in this context.
	Formally, we study the problem of estimating predicate sums privately, for sliding windows and other decay models. While we require accuracy in analysis with respect to the decayed sums, we still want differential privacy for the entire past. This is challenging because window sums are not monotonic or even near-monotonic as the problems studied previously [DPNR10].
	<br>
	We present accurate ε-differentially private algorithms for decayed sums. For window and exponential decay sums, our algorithms are accurate up to additive 1/ε and polylog terms in the range of the computed function; for polynomial decay sums which are technically more challenging because partial solutions do not compose easily, our algorithms incur additional relative error. Our algorithm for polynomial decay sums generalizes to arbitrary decay sum functions. The algorithm crucially relies on our solution for the window sum problem as a subroutine. Further, we show lower bounds, tight within polylog factors and tight with respect to the dependence on the probability of error. Our results are obtained via a natural dyadic tree we maintain, but the crux is we treat the tree data structure in non-uniform manner.
	<br>
	We also extend our study and consider the "dual" question of maintaining conventional running sums on the entire data thus far, but when privacy constraints expire with time. We define a new model of privacy with expiration and consider the problems of designing accurate running sum and linear map algorithms in this model. Now the goal is to design algorithms whose accuracy guarantees scale with the size of the privacy window. We reduce running sum with a privacy window W to window sum without privacy expiration, and characterize the accuracy of output perturbation for general linear maps with privacy window W._

- Efficient and accurate strategies for differentially-private sliding window queries
	<a name='Cao:13'></a>
	[[Paper]](https://dl.acm.org/citation.cfm?id=2452400)

	_Jianneng Cao, Qian Xiao, Gabriel Ghinita, Ninghui Li, Elisa Bertino, Kian-Lee Tan (EDBT 2013)_

	>_Regularly releasing the aggregate statistics about data streams in a privacy-preserving way not only serves valuable commercial and social purposes, but also protects the privacy of individuals. This problem has already been studied under differential privacy, but only for the case of a single continuous query that covers the entire time span, e.g., counting the number of tuples seen so far in the stream. However, most real-world applications are window-based, that is, they are interested in the statistical information about streaming data within a window, instead of the whole unbound stream. Furthermore, a Data Stream Management System (DSMS) may need to answer numerous correlated aggregated queries simultaneously, rather than a single one. To cope with these requirements, we study how to release differentially private answers for a set of sliding window aggregate queries. We propose two solutions, each consisting of query sampling and composition. We first selectively sample a subset of representative sliding window queries from the set of all the submitted ones. The representative queries are answered by adding Laplace noises in a way satisfying differential privacy. For each non-representative query, we compose its answer from the query results of those representatives. The experimental evaluation shows that our solutions are efficient and effective._

- Differentially private event sequences over infinite streams
	<a name='Kellaris:14'></a>
	[[Paper]](http://www.vldb.org/pvldb/vol7/p1155-kellaris.pdf)

	_Georgios Kellaris, Stavros Papadopoulos, Xiaokui Xiao, Dimitris Papadias (VLDB 2014)_

    >[Comments]: Introduced w-event privacy.

	>_Numerous applications require continuous publication of statistics or monitoring purposes, such as real-time traffic analysis, timely disease outbreak discovery, and social trends observation. These statistics may be derived from sensitive user data and, hence, necessitate privacy preservation. A notable paradigm for offering strong privacy guarantees in statistics publishing is ε-differential privacy. However, there is limited literature that adapts this concept to settings where the statistics are computed over an infinite stream of "events" (i.e., data items generated by the users), and published periodically. These works aim at hiding a single event over the entire stream. We argue that, in most practical scenarios, sensitive information is revealed from multiple events occurring at contiguous time instances. Towards this end, we put forth the novel notion of w-event privacy over infinite streams, which protects any event sequence occurring in w successive time instants. We first formulate our privacy concept, motivate its importance, and introduce a methodology for achieving it. We next design two instantiations, whose utility is independent of the stream length. Finally, we confirm the practicality of our solutions experimenting with real data._


- An Adaptive Approach to Real-Time Aggregate Monitoring With Differential Privacy
	<a name='Fan:14'></a>
	[[Paper]](https://ieeexplore.ieee.org/document/6542629/)

	_Liyue Fan, Li Xiong (IEEE Trans, on Knowledge and Data Engineering 2014)_ 

	>_Sharing real-time aggregate statistics of private data is of great value to the public to perform data mining for understanding important phenomena, such as Influenza outbreaks and traffic congestion. However, releasing time-series data with standard differential privacy mechanism has limited utility due to high correlation between data values. We propose FAST, a novel framework to release real-time aggregate statistics under differential privacy based on filtering and adaptive sampling. To minimize the overall privacy cost, FAST adaptively samples long time-series according to the detected data dynamics. To improve the accuracy of data release per time stamp, FAST predicts data values at non-sampling points and corrects noisy observations at sampling points. Our experiments with real-world as well as synthetic data sets confirm that FAST improves the accuracy of released aggregates even under small privacy cost and can be used to enable a wide range of monitoring applications._

 
 - Privacy Integrated Data Stream Queries
 	<a name='Waye:14'></a>
 	[[Paper]](http://lucaswaye.com/papers/spinq-psp14.pdf)

 	_Lucas Waye (PSP 2014)_

 	>_Research on differential privacy is generally concerned with examining data sets that are static. Because the data sets do not change, every computation on them produces “one-shot” query results; the results do not change aside from randomness introduced for privacy . There are many circumstances, however, where this model does not apply, or is simply infeasible. Data streams are examples of non-static data sets where results may change as more data is streamed. Theoretical support for differential privacy with data streams has been researched in the form of differentially private streaming algorithms. In this paper, we present a practical framework for which a non-expert can perform differentially private operations on data streams. The system is built as an extension to PINQ (Privacy Integrated Queries), a differentially private programming framework for static data sets. The streaming extension provides a programmatic interface for the different types of streaming differential privacy from the literature so that the privacy trade-offs of each type of algorithm can be understood by a non-expert programmer._

- Pure differential privacy for rectangle queries via private partitions
	<a name='Dwork:15'></a>
	[[Paper]](https://link.springer.com/content/pdf/10.1007/978-3-662-48800-3_30.pdf)

	_Cynthia Dwork, Moni Naor, Omer Reingold, and Guy N. Rothblum (2015)_
	
	>_We consider the task of data analysis with pure differential privacy. We construct new and improved mechanisms for statistical release of interval and rectangle queries. We also obtain a new algorithm for counting over a data stream under continual observation, whose error has optimal dependence on the data stream's length.
	A central ingredient in all of these result is a differentially private partition mechanism. Given set of data items drawn from a large universe, this mechanism outputs a partition of the universe into a small number of segments, each of which contain only a few of the data items._

- Differentially Private Real-time Data Release over Infinite Trajectory Streams
	<a name='Cao:15'></a>
	[[Paper]](https://www.db.soc.i.kyoto-u.ac.jp/PNS/privacy/HuMoComP_CM.pdf)

	_Yang Cao, Mashatoshi Yoshikawa (MDM 2015)_

	>_Recent emerging mobile and wearable technologies make it easy to collect personal spatiotemporal data such as activity trajectories in daily life. Releasing real-time statistics over trajectory streams produced by crowds of people is expected to be valuable for both academia and business, answering questions such as “How many people are in Central Station now?” However, analyzing these raw data will entail risks of compromising individual privacy. ϵ-Differential Privacy has emerged as a de facto standard for private statistics publishing because of its guarantee of being rigorous and mathematically provable. Since user trajectories will be generated infinitely, it is difficult to protect every trajectory under ϵ-differential privacy. To this end, we propose a flexible privacy model of ℓ-trajectory privacy to ensure every length of ℓ trajectories under protection of ϵ-differential privacy. Then we hierarchically design algorithms to satisfy ℓ-trajectory privacy. Experiments using four real-life datasets show that our proposed algorithms are effective and efficient._

- Gradual Release of Sensitive Data under Differential Privacy
	<a name="Koufogiannis:16"></a>
	[[Paper]](http://repository.cmu.edu/cgi/viewcontent.cgi?article=1145&context=jpc)
	
	_Fragkiskos Koufogiannis, Shuo Han, George J. Pappas (Journal of Privacy and Confidentiality 2016)_

    >_We introduce the problem of releasing private data under differential privacy when the privacy level is subject to change over time. Existing work assumes that privacy level is determined by the system designer as a fixed value before private data is released. For certain applications, however, users may wish to relax the privacy level for subsequent releases of the same data after either a re-evaluation of the privacy concerns or the need for better accuracy. Specifically, given a database containing private data, we assume that a response y1 that preserves \epsilon1-differential privacy has already been published. Then, the privacy level is relaxed to \epsilon2, with \epsilon2 > \epsilon1, and we wish to publish a more accurate response y2 while the joint response (y1, y2) preserves \epsilon2-differential privacy. How much accuracy is lost in the scenario of gradually releasing two responses y1 and y2 compared to the scenario of releasing a single response that is \epsilon2-differentially private? Our results consider the more general case with multiple privacy level relaxations and show that there exists a composite mechanism that achieves no loss in accuracy.
    <br>
    We consider the case in which the private data lies within R^n with an adjacency relation induced by the L1-norm, and we initially focus on mechanisms that approximate identity queries. We show that the same accuracy can be achieved in the case of gradual release through a mechanism whose outputs can be described by a lazy Markov stochastic process. This stochastic process has a closed form expression and can be efficiently sampled. Moreover, our results extend beyond identity queries to a more general family of privacy-preserving mechanisms. To this end, we demonstrate the applicability of our tool to multiple scenarios including Google’s project RAPPOR, trading of private data, and controlled transmission of private data in a social network. Finally, we derive similar results for the approximated differential privacy._

- PeGaSus: Data-Adaptive Differentially Private Stream Processing
	<a name='Chen:17'></a>
	[[Paper]](https://users.cs.duke.edu/~ashwin/pubs/Chen-PeGaSus-CCS2017-final.pdf)

	_Yan Chen, Ashwin Machanavajjhala, Michael Hay, Gerome Miklau (CCS 2017)_

	> _Individuals are continually observed by an ever-increasing number of sensors that make up the Internet of Things. The resulting streams of data, which are analyzed in real time, can reveal sensitive personal information about individuals. Hence, there is an urgent need for stream processing solutions that can analyze these data in real time with provable guarantees of privacy and low error.
	<br>
	We present PeGaSus, a new algorithm for differentially private stream processing. Unlike prior work that has focused on answering individual queries over streams, our algorithm is the first that can simultaneously support a variety of stream processing tasks -- counts, sliding windows, event monitoring -- over multiple resolutions of the stream. PeGaSus uses a Perturber to release noisy counts, a data-adaptive Perturber to identify stable uniform regions in the stream, and a query specific Smoother, which combines the outputs of the Perturber and Grouper to answer queries with low error. In a comprehensive study using a WiFi access point dataset, we empirically show that PeGaSus can answer continuous queries with lower error than the previous state-of-the-art algorithms, even those specialized to particular query types._

- An Algorithm for Differential Privacy Streaming Data Adaptive Publication
	<a name='Yingjie:17'></a>
	[[Paper]](http://crad.ict.ac.cn/EN/abstract/abstract3594.shtml)

	_Wu Yingjie, Zhang Liqun, Kang Jian, Wang Yilei (Journal of Computer Research and Development 2017)_

	>_Nowadays, many practical applications need to publish streaming data continuously. Most of existing research works for differential privacy single streaming data publication focus on range accumulation. However, many practical scenarios need to answer arbitrary range counting queries of streaming data. At the same time, there exist specific rules of queries from users, so adaptive analysis and calculation for historical queries should be concerned. To improve the usability of published data, an algorithm HQDPASP for differential privacy streaming data adaptive publication based on historical queries is proposed. Combining the characteristics of streaming data, HQDPASP firstly uses the sliding window mechanism to construct the differential privacy range tree of the streaming data dynamically. Secondly, by analyzing the coverage probability of tree nodes and calculating the privacy parameters from leaves to root, HQDPASP allocates privacy budget from root to leaves and adds non-uniform noise on tree nodes. Finally, the privacy budget of tree nodes and tree's parameters are adjusted adaptively based on the characteristic of historical queries. Experiments are designed for testing the feasibility and effectiveness of HQDPSAP. The results show that HQDPSAP is effective in answering arbitrary range counting queries on the published streaming data while assuring low mean squared error of queries and high algorithm efficiency._

- Privacy Preserving Stream Analytics: The Marriage of Randomized Response and Approximate Computing
	<a name='LeQuoc:17'></a>
	[[Paper]](https://arxiv.org/pdf/1701.05403.pdf)

	_Do Le Quoc, Martin Beck, Pramod Bhatotia, Ruichuan Chen, Christof Fetzer, and Thorsten Strufe† (Tech. Report 2017)_

	>_How to preserve users’ privacy while supporting high-utility analytics for low-latency stream processing? To answer this question: we describe the design, implementation and evaluation of PRIVAPPROX, a data analytics system for privacy-preserving stream processing. PRIVAPPROX provides three properties: (i) Privacy: zero-knowledge privacy guarantee for users, a privacy bound tighter than the state-of-the-art differential privacy; (ii) Utility: an interface for data analysts to systematically explore the trade-offs between the output accuracy (with error-estimation) and the query execution budget; (iii) Latency: near real-time stream processing based on a scalable “synchronization-free” distributed architecture. The key idea behind our approach is to marry two techniques together, namely, sampling (used in the context of approximate computing) and randomized response (used in the context of privacy-preserving analytics). The resulting marriage is complementary — it achieves stronger privacy guarantees and also improves the performance for low-latency stream analytics._

- Local Differential Privacy for Evolving Data
	<a name="Joseph:18"></a>
	[[Paper]](https://arxiv.org/pdf/1802.07128.pdf)

	_Matthew Joseph, Aaron Roth, Jonathan Ullman, Bo Waggoner (2018)_
    
    >_There are now several large scale deployments of differential privacy used to track statistical information about users. However, these systems periodically recollect the data and recompute the statistics using algorithms designed for a single use and as a result do not provide meaningful privacy guarantees over long time scales. Moreover, existing techniques to mitigate this effect do not apply in the “local” model of differential privacy that these systems use. In this paper, we introduce a new local differential privacy technique to maintain persistently up-to-date statistics over time, with privacy guarantees scaling only with the number of changes in the underlying distribution rather than the number of collection periods. The key ideas include batching time into epochs—varying the epoch size allows us to trade off accuracy against frequency of updates—and a protocol for users to “vote” to update out-of-date statistics while losing very little privacy. We prove our main results for the setting where users hold a single bit, redrawn at every time period, from a common (but changing) distribution; however, our framework is quite general and we give an application to frequency and heavy-hitter estimation._


#### Other Resources
##### Slides
- [[Privacy of Dynamic Data: Continual Observation and Pan Privacy - Moni Naor]](https://www.microsoft.com/en-us/research/wp-content/uploads/2010/01/Naor_Privacy_and_Trust_RFS_71210.pdf)
- [[Differential Privacy in the Streaming World - Aleksandar Nikolov ]](https://simons.berkeley.edu/sites/default/files/docs/1123/nikolovslides.pdf)
- [[Differential Privacy in the Streaming Model - Jalaj Upadhyay]](https://www.cs.jhu.edu/~vova/sublinear2016/slides/Upadhyay.pdf)

##### Videos
- [[Privacy of Dynamic Data: Continual Observation and Pan Privacy - Moni Naor]](https://www.youtube.com/watch?v=KU3AAYEWNR0)



<!-- Differentially Private Machine Learning Algorithms -->

## Machine Learning
<a name='_machine_learning'></a>

[Jump to Top](#_content)

- Differential Privacy and Machine Learning: a Survey and Review
	[[Paper]](https://arxiv.org/pdf/1412.7584.pdf)
  
	_Zhanglong Ji, Zachary C. Lipton, Charles Elkan (2014)_

- Privacy-preserving Prediction
    <a name='Dwork:18'></a>
    [[Paper](https://arxiv.org/pdf/1803.10266.pdf)
    
    _Cynthia Dwork, Vitaly Feldman (ArXiv 2018)_

    > _Ensuring differential privacy of models learned from sensitive user data is an important goal that has been studied extensively in recent years. It is now known that for some basic learning problems, especially those involving high-dimensional data, producing an accurate private model requires much more data than learning without privacy. At the same time, in many applications it is not necessary to expose the model itself. Instead users may be allowed to query the prediction model on their inputs only through an appropriate interface. Here we formulate the problem of ensuring privacy of individual predictions and investigate the overheads required to achieve it in several standard models of classification and regression. 
    <br>
    We first describe a simple baseline approach based on training several models on disjoint subsets of data and using standard private aggregation techniques to predict. We show that this approach has nearly optimal sample complexity for (realizable) PAC learning of any class of Boolean functions. At the same time, without strong assumptions on the data distribution, the aggregation step introduces a substantial overhead. We demonstrate that this overhead can be avoided for the well-studied class of thresholds on a line and for a number of standard settings of convex regression. The analysis of our algorithm for learning thresholds relies crucially on strong generalization guarantees that we establish for all differentially private prediction algorithms._


### Clustering
<a name='_clustering'></a>

- Practical privacy: the SuLQ framework
    <a name='Blum:05'></a>
	[[Paper]](http://delivery.acm.org/10.1145/1070000/1065184/p128-blum.pdf?ip=141.212.164.68&id=1065184&acc=ACTIVE%20SERVICE&key=93447E3B54F7D979%2E0A17827594E6F2C8%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35&__acm__=1520269776_ffb205ebd8018257604d9eaf39338ac3)

    _Avrim Blum, Cynthia Dwork, Frank McSherry, Kobbi Nissim (PODS 2005)_
    
    >_We consider a statistical database in which a trusted administrator introduces noise to the query responses with the goal of maintaining privacy of individual database entries. In such a database, a query consists of a pair (S, f) where S is a set of rows in the database and f is a function mapping database rows to {0, 1}. The true answer is ΣiεS f(di), and a noisy version is released as the response to the query. Results of Dinur, Dwork, and Nissim show that a strong form of privacy can be maintained using a surprisingly small amount of noise -- much less than the sampling error -- provided the total number of queries is sublinear in the number of database rows. We call this query and (slightly) noisy reply the SuLQ (Sub-Linear Queries) primitive. The assumption of sublinearity becomes reasonable as databases grow increasingly large.We extend this work in two ways. First, we modify the privacy analysis to real-valued functions f and arbitrary row types, as a consequence greatly improving the bounds on noise required for privacy. Second, we examine the computational power of the SuLQ primitive. We show that it is very powerful indeed, in that slightly noisy versions of the following computations can be carried out with very few invocations of the primitive: principal component analysis, k means clustering, the Perceptron Algorithm, the ID3 algorithm, and (apparently!) all algorithms that operate in the in the statistical query learning model [11]._

- Privacy integrated queries: an extensible platform for privacy-preserving data analysis
    <a name='McSherry:09'></a>
    [[Paper](http://delivery.acm.org/10.1145/1560000/1559850/p19-mcsherry.pdf?ip=141.212.164.68&id=1559850&acc=ACTIVE%20SERVICE&key=93447E3B54F7D979%2E0A17827594E6F2C8%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35&__acm__=1520270227_abf8ba4086bdc7553329309864918815)

    _Frank McSherry (SIGMOD 2009)_
    
    >_We report on the design and implementation of the Privacy Integrated Queries (PINQ) platform for privacy-preserving data analysis. PINQ provides analysts with a programming interface to unscrubbed data through a SQL-like language. At the same time, the design of PINQ's analysis language and its careful implementation provide formal guarantees of differential privacy for any and all uses of the platform. PINQ's unconditional structural guarantees require no trust placed in the expertise or diligence of the analysts, substantially broadening the scope for design and deployment of privacy-preserving data analysis, especially by non-experts._

- Differentially private publication of general time-serial trajectory data
    <a name='Hua:15'></a>
    [[Paper]](http://114.212.191.112/images/d/d5/Infocom2015.pdf)

    _Jingyu Hua, Yue Gao, Sheng Zhong (INFOCOM 2015)_

    >_Trajectory data, i.e., human mobility traces, is extremely valuable for a wide range of mobile applications. However, publishing raw trajectories without special sanitization poses serious threats to individual privacy. Recently, researchers begin to leverage differential privacy to solve this challenge. Nevertheless, existing mechanisms make an implicit assumption that the trajectories contain a lot of identical prefixes or n-grams, which is not true in many applications. This paper aims to remove this assumption and propose a differentially private publishing mechanism for more general time-series trajectories. One natural solution is to generalize the trajectories, i.e., merge the locations at the same time. However, trivial merging schemes may breach differential privacy. We, thus, propose the first differentially-private generalization algorithm for trajectories, which leverage a carefully-designed exponential mechanism to probabilistically merge nodes based on trajectory distances. Afterwards, we propose another efficient algorithm to release trajectories after generalization in a differential private manner. Our experiments with real-life trajectory data show that the proposed mechanism maintains high data utility and is scalable to large trajectory datasets._
    
- Privacy aware K-means clustering with high utility
    <a name='Nguyen:16'></a>
    [[Paper]()

    _Thanh Dai Nguyen, Sunil Gupta, Santu Rana, Svetha Venkatesh (PAKDD 2016)_

    >_Privacy-preserving data mining aims to keep data safe, yet useful. But algorithms providing strong guarantees often end up with low utility. We propose a novel privacy preserving framework that thwarts an adversary from inferring an unknown data point by ensuring that the estimation error is almost invariant to the inclusion/exclusion of the data point. By focusing directly on the estimation error of the data point, our framework is able to significantly lower the perturbation required. We use this framework to propose a new privacy aware K-means clustering algorithm. Using both synthetic and real datasets, we demonstrate that the utility of this algorithm is almost equal to that of the unperturbed K-means, and at strict privacy levels, almost twice as good as compared to the differential privacy counterpart._
    
- Differentially Private k-Means Clustering
    <a name='Su:16'></a>
    [[Paper](https://arxiv.org/pdf/1504.05998.pdf)
    
    _Dong Su, Jianneng Cao, Ninghui Li, Elisa Bertino, Hongxia Jin (CODASPY 2016)_

    >_There are two broad approaches for differentially private data analysis. The interactive approach aims at developing customized differentially private algorithms for various data mining tasks. The non-interactive approach aims at developing differentially private algorithms that can output a synopsis of the input dataset, which can then be used to support various data mining tasks. In this paper we study the effectiveness of the two approaches on differentially private k-means clustering. We develop techniques to analyze the empirical error behaviors of the existing interactive and non-interactive approaches. Based on the analysis, we propose an improvement of DPLloyd which is a differentially private version of the Lloyd algorithm. We also propose a non-interactive approach EUGkM which publishes a differentially private synopsis for k-means clustering. Results from extensive and systematic experiments support our analysis and demonstrate the effectiveness of our improvement on DPLloyd and the proposed EUGkM algorithm._


### Decision Trees
<a name='_decision_trees'></a>

- A Practical Differentially Private Random Decision Tree Classifier
	[[Paper]](http://www.tdp.cat/issues11/tdp.a082a11.pdf)
  
	_Geetha Jagannathan, Krishnan Pillaipakkamnatt, Rebecca N Wright (ICDMW 2009)_

- Data mining with differential privacy
	[[Paper]](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.799.7017&rep=rep1&type=pdf)

	_Arik Friedman and Assaf Schuster (KDD 2010)_

- Differentially Private Data Release for Data Mining
	[[Paper]](http://www.cs.umanitoba.ca/~noman/Papers/MCFY11kdd.pdf)

	_Noman Mohammed, Rui Chen  Benjamin Fung, Philip S Yu (KDD 2011)_

- A practical differentially private random decision tree classifier
	[[Paper]](http://www.tdp.cat/issues11/tdp.a082a11.pdf)

	_Geetha Jagannathan, Krishnan Pillaipakkamnatt, Rebecca N. Wright (Trans. Data Privacy 2012)_

- Differentially Private Random Forest with High Utility
	[[Paper]](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7373418)

	_Santu Rana, Sunil Kumar Gupta, Svetha Venkatesh (ICDM 2015)_

- Differentially- and non-differentially-private random decision trees
	[[Paper]](https://arxiv.org/pdf/1410.6973.pdf)
  
	_Mariusz Bojarski, Anna Choromanska, KrzysztofChoromanski, Yann LeCun (2015)_

- A Differentially Private Decision Forest
	[[Paper]](http://crpit.com/confpapers/CRPITV168Fletcher.pdf)

	_Sam Fletcher, Md Zahidul Islam (AusDM 2015)_

- Decision Tree Classification with Differential Privacy: A Survey
	[[Paper]](https://arxiv.org/pdf/1611.01919.pdf)
  
	_San Fletcher, Charles Sturt (2017)_

- Differentially Private Random Decision Forests using Smooth Sensitivity
	[[Paper]](https://arxiv.org/pdf/1606.03572.pdf)
  
	_Sam Fletchera, Md Zahidul Islama (Expert Systems with Applications 2017)_


### Generative Adversarial Models
<a name='_generative_adversarial_models'></a>


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

- Differentially Private Generative Adversarial Network
	<a name='Xie:18'></a>	
	[[Paper]](https://arxiv.org/pdf/1802.06739.pdf)

	_L Xie, K Lin, S Wang, F Wang, J Zhou (arXiv-2018)_

  	>_Generative Adversarial Network (GAN) and its variants have recently attracted intensive research interests due to their elegant theoretical foundation and excellent empirical performance as generative models. These tools provide a promising direction in the studies where data availability is limited. One common issue in GANs is that the density of the learned generative distribution could concentrate on the training data points, meaning that they can easily remember training samples due to the high model complexity of deep networks. This becomes a major concern when GANs are applied to private or sensitive data such as patient medical records, and the concentration of distribution may divulge critical patient information. To address this issue, in this paper we propose a di erentially private GAN (DPGAN) model, in which we achieve di erential privacy in GANs by adding carefully designed noise to gradients during the learning procedure. We provide rigorous proof for the privacy guarantee, as well as comprehensive empirical evidence to support our analysis, where we demonstrate that our method can generate high quality data points at a reasonable privacy level._

- Generating Differentially Private Datasets Using GANs
	<a name='Triastcyn:18'></a>
	[[Paper]](https://openreview.net/forum?id=rJv4XWZA-&noteId=BynjVJaSG)

	_A Triastcyn, B Faltings (ArXiv-2018)_

	>Note: This is a rejected paper from ICLR 2018

- Differentially Private Mixture of Generative Neural Networks
	<a name='Acs:17'></a>
	[[Paper]](https://arxiv.org/abs/1709.04514)

	_Gergely Acs, Luca Melis, Claude Castelluccia, Emiliano De Cristofaro (ICDM 2017)_

	>_Generative models are used in a wide range of applications building on large amounts of contextually rich information. Due to possible privacy violations of the individuals whose data is used to train these models, however, publishing or sharing generative models is not always viable. In this paper, we present a novel technique for privately releasing generative models and entire high-dimensional datasets produced by these models. We model the generator distribution of the training data with a mixture of k generative neural networks. These are trained together and collectively learn the generator distribution of a dataset. Data is divided into k clusters, using a novel differentially private kernel k-means, then each cluster is given to separate generative neural networks, such as Restricted Boltzmann Machines or Variational Autoencoders, which are trained only on their own cluster using differentially private gradient descent. We evaluate our approach using the MNIST dataset, as well as call detail records and transit datasets, showing that it produces realistic synthetic samples, which can also be used to accurately compute arbitrary number of counting queries._


### Regression
<a name='_regression'></a>

- Differential Privacy and Robust Statistics
	[[Paper]](http://www.stat.cmu.edu/~jinglei/dl09.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:Z-LD4ASNIoQJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXGe-UHAG19UsSNEQ2RwLXyyB4SdtbA&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Cynthia Dwork, Jing Lei (STOC 2009)_

- Privacy-preserving logistic regression
	[[Paper]](https://papers.nips.cc/paper/3486-privacy-preserving-logistic-regression.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:jTZmFlLL6rcJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXEipuHdAjGeBLUhDtaWHX2b0sMAfkW&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_Kamalika Chaudhuri, Claire Monteleoni (NIPS 2009)_

- Private Convex Empirical Risk Minimization and High-dimensional Regression
	[[Paper]](http://proceedings.mlr.press/v23/kifer12/kifer12.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:y1zDUr2O_nYJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXJxh-0YCjf4QldGd_zavm9Q7qaK99Q&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Daniel Kifer, Adam Smith, Abhradeep Thakurta (JMLR 2012)_

- Revisiting Differentially Private Regression: Lessons From Learning Theory and their Consequences
	[[Paper]](https://arxiv.org/pdf/1512.06388.pdf) 
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:qnLQEzVhaW8J:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXCmeTCRw-khVZFPdjqutebHTh4jhPM&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Xi Wu, Matthew Fredrikson, Wentao Wu, Somesh Jha, Jeffrey F. Naughton (2015)_
  
- Functional Mechanism: Regression Analysis under Differential Privacy
	[[Paper]](http://vldb.org/pvldb/vol5/p1364_junzhang_vldb2012.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:rjQilC3UUO0J:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXKOnsUse63UjyNAGPhExDVD39hhPzy&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_Jun Zhang, Zhenjie Zhang, Xiaokui Xiao, Yin Yang, Marianne Winslett (VLDB 2012)_


### Adversarial Learning
<a name='_adversarial_learning'></a>

- On the Connection between Differential Privacy and Adversarial Robustness in Machine Learning
	[[Paper]](https://arxiv.org/pdf/1802.03471.pdf)

	_Mathias Lecuyer, Vaggelis Atlidakis, Roxana Geambasu, Daniel Hsu, Suman Jana_

	>_Adversarial examples in machine learning has been a topic of intense research interest, with attacks and defenses being developed in a tight back-and-forth. Most past defenses are best-effort, heuristic approaches that have all been shown to be vulnerable to sophisticated attacks. More recently, rigorous defenses that provide formal guarantees have emerged, but are hard to scale or generalize. A rigorous and general foundation for designing defenses is required to get us off this arms race trajectory. We propose leveraging differential privacy (DP) as a formal building block for robustness against adversarial examples. We observe that the semantic of DP is closely aligned with the formal definition of robustness to adversarial examples. We propose PixelDP, a strategy for learning robust deep neural networks based on formal DP guarantees. PixelDP networks give theoretical guarantees for a subset of their predictions regarding the robustness against adversarial perturbations of bounded size. Our evaluation with MNIST, CIFAR-10, and CIFAR-100 shows that PixelDP networks achieve accuracy under attack on par with the best-performing defense to date, but additionally certify robustness against meaningful-size 1-norm and 2-norm attacks for 40-60% of their predictions. Our experience points to DP as a rigorous, broadly applicable, and mechanism-rich foundation for robust machine learning._



## Distributed Differential Privacy
<a name='_distributed_dp'></a>

- Our Data, Ourselves: Privacy via Distributed Noise Generation
	<a name='Dwork:06b'></a>
	[[Paper]](https://www.iacr.org/archive/eurocrypt2006/40040493/40040493.pdf)

	_Cynthia Dwork, Krishnaram Kenthapadi, Frank McSherry, Ilya Mironov, Moni Naor (Eurocrypt 2006)_

	>_. In this work we provide efficient distributed protocols for generating shares of random noise, secure against malicious participants. The purpose of the noise generation is to create a distributed implementation of the privacy-preserving statistical databases described in recent papers [14, 4, 13]. In these databases, privacy is obtained by perturbing the true answer to a database query by the addition of a small amount of Gaussian or exponentially distributed random noise. The computational power of even a simple form of these databases, when the query is just of the form \Sum_i f(di), that is, the sum over all rows i in the database of a function f applied to the data in row i, has been demonstrated in [4]. A distributed implementation eliminates the need for a trusted database administrator. The results for noise generation are of independent interest. The generation of Gaussian noise introduces a technique for distributing shares of many unbiased coins with fewer executions of verifiable secret sharing than would be needed using previous approaches (reduced by a factor of n). The generation of exponentially distributed noise uses two shallow circuits: one for generating many arbitrarily but identically biased coins at an amortized cost of two unbiased random bits apiece, independent of the bias, and the other to combine bits of appropriate biases to obtain an exponential distribution._


## Differential Privacy Model Extensions
<a name='_dp_extensions'></a>

[Jump to Top](#_content)


### Approximate Differential Privacy
<a name="_approximate_dp"></a>

[Jump to Top](#_content)


### Concentrated Differential Privacy
<a name='_concentrated_dp'></a>

[Jump to Top](#_content)

- Concentrated Differential Privacy
	<a name='Dwork:16'></a>
	[[Paper]](https://arxiv.org/pdf/1603.01887.pdf)

	_Cynthia Dwork, Guy N. Rothblum (ArXiv 2016)_

	>_We introduce Concentrated Differential Privacy, a relaxation of Differential Privacy enjoying better accuracy than both pure differential privacy and its popular “(ε, δ)” relaxation without compromising on cumulative privacy loss over multiple computations._


### Local Differential Privacy
<a name="_local_dp"></a>

[Jump to Top](#_content)


### Lipschitz Differential Privacy 
<a name='_lipschitz_dp'></a>

- Analyzing Graphs with Node Differential Privacy
	<a name='Kasiviswanathan:13'></a>
	[[Paper]](https://link.springer.com/content/pdf/10.1007/978-3-642-36594-2_26.pdf)

	_Shiva Prasad Kasiviswanathan, Kobbi Nissim, Sofya Raskhodnikova, Adam Smith (TCC 2013)_

	>_. We develop algorithms for the private analysis of network data that provide accurate analysis of realistic networks while satisfying stronger privacy guarantees than those of previous work. We present several techniques for designing node differentially private algorithms, that is, algorithms whose output distribution does not change significantly when a node and all its adjacent edges are added to a graph. We also develop methodology for analyzing the accuracy of such algorithms on realistic networks.
	<br>
	The main idea behind our techniques is to “project” (in one of several senses) the input graph onto the set of graphs with maximum degree below a certain threshold. We design projection operators, tailored to specific statistics that have low sensitivity and preserve information about the original statistic. These operators can be viewed as giving a fractional (low-degree) graph that is a solution to an optimization problem described as a maximum flow instance, linear program, or convex program. In addition, we derive a generic, efficient reduction that allows us to apply any differentially private algorithm for bounded-degree graphs to an arbitrary graph. This reduction is based on analyzing the smooth sensitivity of the “naive” truncation that simply discards nodes of high degree._


### Pan Privacy
<a name='_pan_privacy'></a>

[Jump to Top](#_content)

- Pan-Private Streaming Algorithms
	<a name='Dwork:09'></a>
	[[Paper]](https://www.cs.toronto.edu/~toni/Papers/panprivacy.pdf)

	_Cynthia Dwork, Moni Naor, Toniann Pitassi, Guy N. Rothblum, Sergey Yekhanin (ICS 2010)_

	>_Collectors of confidential data, such as governmental agencies, hospitals, or search engine providers, can be pressured to permit data to be used for purposes other than that for which they were collected. To support the data curators, we initiate a study of pan-private algorithms; roughly speaking, these algorithms retain their privacy properties even if their internal state becomes visible to an adversary. Our principal focus is on streaming algorithms, where each datum may be discarded immediately after processing._

- Pan-private Algorithms: When Memory Does Not Help
	<a name='_Darakhshan:10'></a>
	[[Paper]](https://arxiv.org/abs/1009.1544)

	_Darakhshan Mir, S. Muthukrishnan, Aleksandar Nikolov, Rebecca N. Wright (ArXiv 2010)_

	>_Consider updates arriving online in which the tth input is (it,dt), where it's are thought of as IDs of users. Informally, a randomized function f is {\em differentially private} with respect to the IDs if the probability distribution induced by f is not much different from that induced by it on an input in which occurrences of an ID j are replaced with some other ID k Recently, this notion was extended to {\em pan-privacy} where the computation of f retains differential privacy, even if the internal memory of the algorithm is exposed to the adversary (say by a malicious break-in or by fiat by the government). This is a strong notion of privacy, and surprisingly, for basic counting tasks such as distinct counts, heavy hitters and others, Dwork et al~\cite{dwork-pan} present pan-private algorithms with reasonable accuracy. The pan-private algorithms are nontrivial, and rely on sampling. We reexamine these basic counting tasks and show improved bounds. In particular, we estimate the distinct count $\Dt$ to within $(1\pm \eps)\Dt \pm O(\polylog m)$, where m is the number of elements in the universe. This uses suitably noisy statistics on sketches known in the streaming literature. We also present the first known lower bounds for pan-privacy with respect to a single intrusion. Our lower bounds show that, even if allowed to work with unbounded memory, pan-private algorithms for distinct counts can not be significantly more accurate than our algorithms. Our lower bound uses noisy decoding. For heavy hitter counts, we present a pan private streaming algorithm that is accurate to within O(k) in worst case; previously known bound for this problem is arbitrarily worse. An interesting aspect of our pan-private algorithms is that, they deliberately use very small (polylogarithmic) space and tend to be streaming algorithms, even though using more space is not forbidden._

- Fingerprinting Codes and the Price of Approximate Differential Privacy
	<a name="Bun:14"></a>
	[[Paper]](https://arxiv.org/abs/1311.3158)

	_Mark Bun, Jonathan Ullman, Salil Vadhan (STOC 2014)_

	>_We show new lower bounds on the sample complexity of (ε,δ)-differentially private  algorithms that accurately answer large sets of counting queries. A counting query on a database D ∈ ({0,1}^d)^n has the form "What fraction of the individual records in the database satisfy the property q?" We show that in order to answer an arbitrary set Q of >> nd counting queries on D to within error ± \alpha it is necessary that
			n >= \tilde{Theta}( \sqrt(d) log |Q| / alpha^2 \epsilon)
	This bound is optimal up to poly-logarithmic factors, as demonstrated by the [Private Multiplicative Weights algorithm](#hardt:10). In particular, our lower bound is the first to show that the sample complexity required for accuracy and (ε,δ)-differential privacy is asymptotically larger than what is required merely for accuracy, which is O(log|Q|/\alpha^2). In addition, we show that our lower bound holds for the specific case of k-way marginal queries (where |Q|=2^k \binomial(d, k)) when \alpha is not too small compared to d (e.g. when α is any fixed constant).  Our results rely on the existence of short \emph{fingerprinting codes} (Boneh and Shaw, CRYPTO'95, Tardos, STOC'03), which we show are closely connected to the sample complexity of differentially private data release. We also give a new method for combining certain types of sample complexity lower bounds into stronger lower bounds._




