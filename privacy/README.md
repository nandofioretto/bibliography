# Differential Privacy Papers Repository

This repo serves the purpose of organizing papers on Differential Privacy


## Books and Seminal Work

- Differential Privacy: A Survey of Results	
	[[Paper]](http://web.cs.ucdavis.edu/~franklin/ecs289/2010/dwork_2008.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:2XFT4-OFmBUJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXkON19s9zJUA_b-2leazRirIVXtzYl&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Cynthia Dwork (TAMC 2008)_


- A firm foundation for private data analysis 
	[[Paper]](https://www.microsoft.com/en-us/research/wp-content/uploads/2011/01/dwork_cacm.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:M9zjB3R503gJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXku7RjvNTGU5I5kb703DzRuU58nkfD&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_Cynthia Dwork (Communications of the ACM 2011)_


- The Algorithmic Foundations of Differential Privacy
	[[Paper]](https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:U2_JsgxAEdQJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXj3gdueEXahzojphGMX7JkBK4HsxHw&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_Cynthia Dwork, Aaron Roth (2014)_


- The Complexity of Differential Privacy
	[[Paper]](https://privacytools.seas.harvard.edu/files/privacytools/files/complexityprivacy_1.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:VX4mKQQcywsJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXjSjtKBoZDmIFXBncjls-eZe8ucNSD&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Salil Vadhan (Tutorials on the Foundations of Cryptography 2017)_


- Differential Privacy: A Primer for a Non-technical Audience
	[[Paper]](http://privacytools.seas.harvard.edu/files/privacytools/files/pedagogical-document-dp_0.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:NZhnwWKU4iUJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXlHkKEsK7olQ-Inlh9V5hI9HHNnYbF&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_Kobbi Nissim†, Thomas Steinke, Alexandra Wood, Mark Bun, Marco Gaboardi,David R. O’Brien, and Salil Vadhan (2017)_
  
  

## Differential Privacy Mechanisms for General Queries


### Basic Mechanisms

### <a name="dwork:06"></a>
- Calibrating Noise to Sensitivity in Private Data Analysis
	[[Paper]](http://people.csail.mit.edu/asmith/PS/sensitivity-tcc-final.pdf)

	_Cynthia Dwork, Frank McSherry, Kobbi Nissim, Adam Smith (TCC 2006)_

    >[Notes]: The *Laplace Mechanism*.

	>_We continue a line of research initiated in [10,11]on privacy-preserving statistical databases. Consider a trusted server that holds a database of sensitive information. Given a query function f mapping databases to reals, the so-called true answer is the result of applying f to the database. To protect privacy, the true answer is perturbed by the addition of random noise generated according to a carefully chosen distribution, and this response, the true answer plus noise, is returned to the user._
	>_Previous work focused on the case of noisy sums, in which f = ∑ig(xi), where xi denotes the ith row of the database and g maps database rows to [0,1]. We extend the study to general functions f, proving that privacy can be preserved by calibrating the standard deviation of the noise according to the sensitivity of the function f. Roughly speaking, this is the amount that any single argument to f can change its output. The new analysis shows that for several particular applications substantially less noise is needed than was previously understood to be the case._
	>_The first step is a very clean characterization of privacy in terms of indistinguishability of transcripts. Additionally, we obtain separation results showing the increased value of interactive sanitization mechanisms over non-interactive._


### <a name="inusaha:06"></a>
- A discrete analogue of the Laplace distribution.
	[[Paper]](https://www.sciencedirect.com/science/article/pii/S0378375804003519)

	_Seidu Inusaha, Tomasz J.Kozubowski (Journal of Statistical Planning and Inference 2006)_

	> [Notes]: The paper introduces the discrete Laplace distribution.

	>_Following Kemp (J. Statist. Plann. Inference 63 (1997) 223) who defined a discrete analogue of the normal distribution, we derive a discrete version of the Laplace (double exponential) distribution. In contrast with the discrete normal case, here closed-form expressions are available for the probability density function, the distribution function, the characteristic function, the mean, and the variance. We show that this discrete distribution on integers shares many properties of the classical Laplace distribution on the real line, including unimodality, infinite divisibility, closure properties with respect to geometric compounding, and a maximum entropy property. We also discuss statistical issues of estimation under the discrete Laplace model._


### <a name"McSherry:07"></a>
- Mechasim Design via Differential Privacy
	[[Paper]](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/mdviadp.pdf)

	_F. McSherry, K. Talwar (FOCS 2007)_

	>[Notes]: The *Exponential Mechanism*.

	>_We study the role that privacy-preserving algorithms, which prevent the leakage of speciﬁc information about participants, can play in the design of mechanisms for strategic agents, which must encourage players to honestly report information. Speciﬁcally, we show that the recent notion of differential privacy [15, 14], in addition to its own intrinsic virtue, can ensure that participants have limited effect on the outcome of the mechanism, and as a consequence have limited incentive to lie. More precisely, mechanisms with differential privacy are approximate dominant strategy under arbitrary player utility functions, are automatically resilient to coalitions, and easily allow repeatability. We study several special cases of the unlimited supply auction problem, providing new results for digital goods auctions, attribute auctions, and auctions with arbitrary structural constraints on the prices. As an important prelude to developing a privacy-preserving auction mechanism, we introduce and study a generalization of previous privacy work that accommodates the high sensitivity of the auction setting, where a single participant may dramatically alter the optimal ﬁxed price, and a slight change in the offered price may take the revenue from optimal to zero._


### <a name="hardt:10"></a>
- A Multiplicative Weights Mechanism for Privacy-Preserving Data Analysis
	[[Paper]](http://ieeexplore.ieee.org/document/5670948/)

	_Moritz Hardt, Guy N. Rothblum (FOCS 2010)_

	> [Notes]: The paper introduces the *Multiplicative Weights* (MW) Mechanism. It explits the composition theorem to answer queries interactively, by casting the query release problem as an online _learning problem_.

	>_We consider statistical data analysis in the interactive setting. In this setting a trusted curator maintains a database of sensitive information about individual participants, and releases privacy-preserving answers to queries as they arrive. Our primary contribution is a new differentially private multiplicative weights mechanism for answering a large number of interactive counting (or linear) queries that arrive online and may be adaptively chosen. This is the first mechanism with worst-case accuracy guarantees that can answer large numbers of interactive queries and is efficient (in terms of the runtime's dependence on the data universe size). The error is asymptotically optimal in its dependence on the number of participants, and depends only logarithmically on the number of queries being answered. The running time is nearly linear in the size of the data universe. As a further contribution, when we relax the utility requirement and require accuracy only for databases drawn from a rich class of databases, we obtain exponential improvements in running time. Even in this relaxed setting we continue to guarantee privacy for any input database. Only the utility requirement is relaxed. Specifically, we show that when the input database is drawn from a smooth distribution — a distribution that does not place too much weight on any single data item — accuracy remains as above, and the running time becomes poly-logarithmic in the data universe size. The main technical contributions are the application of multiplicative weights techniques to the differential privacy setting, a new privacy analysis for the interactive setting, and a technique for reducing data dimensionality for databases drawn from smooth distributions._


### <a name="hardt:12"></a>
- A Simple and Practical Algorithm for Differentially Private Data Release
	[[Paper]](http://mrtz.org/papers/mwem.pdf)

	_Moritz Hardt, Katrina Ligett, Frank McSherry (NIPS 2012)_

	>[Notes]: The *MWEM Mechanism*.

	>_We present a new algorithm for differentially private data release, based on a simple combination of the Exponential Mechanism with the Multiplicative Weights update rule. Our MWEM algorithm achieves what are the best known and nearly optimal theoretical guarantees, while at the same time being simple to implement and experimentally more accurate on actual data sets than existing techniques._




### Hierarchical (todo)

- H2 (Data independent)
- Hb (Data independent)

- DPCube (data dependent)
- QuadTree (data dependent)
- UGrid, AGrid (data dependent)


### Binning Strategies  (todo)
- AHP (data dependent)
- DAWA (data dependent)


### Dimensionality reduction  (todo)

- Privelet (data independent)
- PHP (data dependent)



## Machine Learning

- Differential Privacy and Machine Learning: a Survey and Review
	[[Paper]](https://arxiv.org/pdf/1412.7584.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:LRO1F80djTQJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXgery5uyaEwnsDib386XbLo5xCEY9P&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_Zhanglong Ji, Zachary C. Lipton, Charles Elkan (2014)_


### Regression

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


### Decision Trees

- A Practical Differentially Private Random Decision Tree Classifier
	[[Paper]](http://www.tdp.cat/issues11/tdp.a082a11.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:8B-ebfA_ULYJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXL0IS1bxkTVArIQtNj7eHBXkUuv8vi&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_Geetha Jagannathan, Krishnan Pillaipakkamnatt, Rebecca N Wright (ICDMW 2009)_


- Data mining with differential privacy
	[[Paper]](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.799.7017&rep=rep1&type=pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:6W2IOf41ouYJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXepl_IBmJDpOMR9xTHMmICyfzrOqlC&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Arik Friedman and Assaf Schuster (KDD 2010)_


- Differentially Private Data Release for Data Mining
	[[Paper]](http://www.cs.umanitoba.ca/~noman/Papers/MCFY11kdd.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:jchI6kjFA68J:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXhk5JM-oCCemh1DEJQOHcuzFHO0CHU&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Noman Mohammed, Rui Chen  Benjamin Fung, Philip S Yu (KDD 2011)_

- A practical differentially private random decision tree classifier
	[[Paper]](http://www.tdp.cat/issues11/tdp.a082a11.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:8B-ebfA_ULYJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXfSSnFdX2-m-NtVwLeZFdz-YasFm9c&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Geetha Jagannathan, Krishnan Pillaipakkamnatt, Rebecca N. Wright (Trans. Data Privacy 2012)_


- Differentially Private Random Forest with High Utility
	[[Paper]](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7373418)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:aMfsr4-D2MwJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXiSxj9pQ1nN8BljGMc0bnwD1BM0lPO&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Santu Rana, Sunil Kumar Gupta, Svetha Venkatesh (ICDM 2015)_


- Differentially- and non-differentially-private random decision trees
	[[Paper]](https://arxiv.org/pdf/1410.6973.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:No_WixkhfygJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXbon11GP3Gtut0yURTH_WtRe2oKQp_&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_Mariusz Bojarski, Anna Choromanska, KrzysztofChoromanski, Yann LeCun (2015)_


- A Differentially Private Decision Forest
	[[Paper]](http://crpit.com/confpapers/CRPITV168Fletcher.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:gmYaqpu52GsJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXchi23QyOFjXwLcAUDqMvX1x8TnbQ-&scisf=4&ct=citation&cd=-1&hl=en "BibTex")

	_Sam Fletcher, Md Zahidul Islam (AusDM 2015)_


- Decision Tree Classification with Differential Privacy: A Survey
	[[Paper]](https://arxiv.org/pdf/1611.01919.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:k9Cxb-VK_hAJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXMWXEm-6uDX-fv3Uq_upoW-UzYYqSC&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_San Fletcher, Charles Sturt (2017)_


- Differentially Private Random Decision Forests using Smooth Sensitivity
	[[Paper]](https://arxiv.org/pdf/1606.03572.pdf)
	[[BibTex]](https://scholar.googleusercontent.com/scholar.bib?q=info:SA8RKp_ieZUJ:scholar.google.com/&output=citation&scisig=AAGBfm0AAAAAWoXdXz9eDozrdB5ETqik0dIMfJvzmEVn&scisf=4&ct=citation&cd=-1&hl=en "BibTex")
  
	_Sam Fletchera, Md Zahidul Islama (Expert Systems with Applications 2017)_


### Generative Adversarial Models

- Context-Aware Generative Adversarial Privacy
	[[Paper]](https://arxiv.org/pdf/1710.09549.pdf)

	_Chong Huang, Peter Kairouz, Xiao Chen, Lalitha Sankar, Ram Rajagopal (Entropy 2018)_

	>_Preserving the utility of published datasets while simultaneously providing provable privacy guarantees is a well-known challenge. On the one hand, context-free privacy solutions, such as differential privacy, provide strong privacy guarantees, but often lead to a significant reduction in utility. On the other hand, context-aware privacy solutions, such as information theoretic privacy, achieve an improved privacy-utility tradeoff, but assume that the data holder has access to dataset statistics. We circumvent these limitations by introducing a novel context-aware privacy framework called generative adversarial privacy (GAP). GAP leverages recent advancements in generative adversarial networks (GANs) to allow the data holder to learn privatization schemes from the dataset itself. Under GAP, learning the privacy mechanism is formulated as a constrained minimax game between two players: a privatizer that sanitizes the dataset in a way that limits the risk of inference attacks on the individuals' private variables, and an adversary that tries to infer the private variables from the sanitized dataset. To evaluate GAP's performance, we investigate two simple (yet canonical) statistical dataset models: (a) the binary data model, and (b) the binary Gaussian mixture model. For both models, we derive game-theoretically optimal minimax privacy mechanisms, and show that the privacy mechanisms learned from data (in a generative adversarial fashion) match the theoretically optimal ones. This demonstrates that our framework can be easily applied in practice, even in the absence of dataset statistics._


- Differentially Private Generative Adversarial Network
	[[Paper]](https://arxiv.org/pdf/1802.06739.pdf)

	_L Xie, K Lin, S Wang, F Wang, J Zhou (arXiv-2018)_

  	>_Generative Adversarial Network (GAN) and its variants have recently attracted intensive research interests due to their elegant theoretical foundation and excellent empirical performance as generative models. These tools provide a promising direction in the studies where data availability is limited. One common issue in GANs is that the density of the learned generative distribution could concentrate on the training data points, meaning that they can easily remember training samples due to the high model complexity of deep networks. This becomes a major concern when GANs are applied to private or sensitive data such as patient medical records, and the concentration of distribution may divulge critical patient information. To address this issue, in this paper we propose a di erentially private GAN (DPGAN) model, in which we achieve di erential privacy in GANs by adding carefully designed noise to gradients during the learning procedure. We provide rigorous proof for the privacy guarantee, as well as comprehensive empirical evidence to support our analysis, where we demonstrate that our method can generate high quality data points at a reasonable privacy level._


- Generating Differentially Private Datasets Using GANs
	[[Paper]](https://openreview.net/forum?id=rJv4XWZA-&noteId=BynjVJaSG)

	_A Triastcyn, B Faltings (ArXiv-2018)_

	>Note: This is a rejected paper from ICLR 2018



### Adversarial Learning
### <a name="adversarial_learning"></a>

- On the Connection between Differential Privacy and Adversarial Robustness in Machine Learning
	[[Paper]](https://arxiv.org/pdf/1802.03471.pdf)

	_Mathias Lecuyer, Vaggelis Atlidakis, Roxana Geambasu, Daniel Hsu, Suman Jana_

	>_Adversarial examples in machine learning has been a topic of intense research interest, with attacks and defenses being developed in a tight back-and-forth. Most past defenses are best-effort, heuristic approaches that have all been shown to be vulnerable to sophisticated attacks. More recently, rigorous defenses that provide formal guarantees have emerged, but are hard to scale or generalize. A rigorous and general foundation for designing defenses is required to get us off this arms race trajectory. We propose leveraging differential privacy (DP) as a formal building block for robustness against adversarial examples. We observe that the semantic of DP is closely aligned with the formal definition of robustness to adversarial examples. We propose PixelDP, a strategy for learning robust deep neural networks based on formal DP guarantees. PixelDP networks give theoretical guarantees for a subset of their predictions regarding the robustness against adversarial perturbations of bounded size. Our evaluation with MNIST, CIFAR-10, and CIFAR-100 shows that PixelDP networks achieve accuracy under attack on par with the best-performing defense to date, but additionally certify robustness against meaningful-size 1-norm and 2-norm attacks for 40-60% of their predictions. Our experience points to DP as a rigorous, broadly applicable, and mechanism-rich foundation for robust machine learning._



## Theory

### Approximate Differential Privacy
### <a name="approximate_dp"></a>


### <a name="bun:14"></a>
- Fingerprinting Codes and the Price of Approximate Differential Privacy
	[[Paper]](https://arxiv.org/abs/1311.3158)

	_Mark Bun, Jonathan Ullman, Salil Vadhan (STOC 2014)_

	>_We show new lower bounds on the sample complexity of (ε,δ)-differentially private  algorithms that accurately answer large sets of counting queries. A counting query on a database D ∈ ({0,1}^d)^n has the form "What fraction of the individual records in the database satisfy the property q?" We show that in order to answer an arbitrary set Q of >> nd counting queries on D to within error ± \alpha it is necessary that
			n >= \tilde{Theta}( \sqrt(d) log |Q| / alpha^2 \epsilon)
	This bound is optimal up to poly-logarithmic factors, as demonstrated by the [Private Multiplicative Weights algorithm](#hardt:10). In particular, our lower bound is the first to show that the sample complexity required for accuracy and (ε,δ)-differential privacy is asymptotically larger than what is required merely for accuracy, which is O(log|Q|/\alpha^2). In addition, we show that our lower bound holds for the specific case of k-way marginal queries (where |Q|=2^k \binomial(d, k)) when \alpha is not too small compared to d (e.g. when α is any fixed constant).  Our results rely on the existence of short \emph{fingerprinting codes} (Boneh and Shaw, CRYPTO'95, Tardos, STOC'03), which we show are closely connected to the sample complexity of differentially private data release. We also give a new method for combining certain types of sample complexity lower bounds into stronger lower bounds.