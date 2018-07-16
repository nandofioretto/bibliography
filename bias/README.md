# Ethics and Bias in Decision Making Bibliography

## Fairness and Bias


- Selection Problems in the Presence of Implicit Bias 
    <a name="Kleinberg:18"></a>
    [[Paper]](http://www.cs.cornell.edu/home/kleinber/itcs18-bias.pdf)

    _Jon Kleinberg, Manish Raghavan (ITCS 2018)_

    >_Over the past two decades, the notion of implicit bias has come to serve as an important component in our understanding of discrimination in activities such as hiring, promotion, and school admissions. Research on implicit bias posits that when people evaluate others – for example, in a hiring context – their unconscious biases about membership in particular groups can have an effect on their decision-making, even when they have no deliberate intention to discriminate against members of these groups. A growing body of experimental work has pointed to the effect that implicit bias can have in producing adverse outcomes. Here we propose a theoretical model for studying the effects of implicit bias on selection decisions, and a way of analyzing possible procedural remedies for implicit bias within this model. A canonical situation represented by our model is a hiring setting: a recruiting committee is trying to choose a set of finalists to interview among the applicants for a job, evaluating these applicants based on their future potential, but their estimates of potential are skewed by implicit bias against members of one group. In this model, we show that measures such as the Rooney Rule, a requirement that at least one of the finalists be chosen from the affected group, can not only improve the representation of this affected group, but also lead to higher payoffs in absolute terms for the organization performing the recruiting. However, identifying the conditions under which such measures can lead to improved payoffs involves subtle trade-offs between the extent of the bias and the underlying distribution of applicant characteristics, leading to novel theoretical questions about order statistics in the presence of probabilistic side information._

- Decoupled Classifiers for Group-Fair and Efficient Machine Learning
    <a name="Dwork:18"></a>
    [[Paper]](http://proceedings.mlr.press/v81/dwork18a/dwork18a.pdf)

    _Cynthia Dwork, Nicole Immorlica, Adam Tauman Kalai, Mark DM Leiserson (PMLR 2018)._

    >_When it is ethical and legal to use a sensitive attribute (such as gender or race) in machine learning systems, the question remains how to do so. We show that the naive application of machine learning algorithms using sensitive attributes leads to an inherent tradeoff in accuracy between groups. We provide a simple and efficient decoupling technique, that can be added on top of any black-box machine learning algorithm, to learn different classifiers for different groups. Transfer learning is used to mitigate the problem of having too little data on any one group._

- Counterfactual Fairness
    <a name="Kusner:17"></a>
    [[Paper]](https://arxiv.org/pdf/1703.06856.pdf)
    
    _Matt Kusner, Joshua Loftus, Chris Russell, Ricardo Silva (NIPS 2017)_

    >_Machine learning can impact people with legal or ethical consequences when it is used to automate decisions in areas such as insurance, lending, hiring, and predictive policing. In many of these scenarios, previous decisions have been made that are unfairly biased against certain subpopulations, for example those of a particular race, gender, or sexual orientation. Since this past data may be biased, machine learning predictors must account for this to avoid perpetuating or creating discriminatory practices. In this paper, we develop a framework for modeling fairness using tools from causal inference. Our definition of counterfactual fairness captures the intuition that a decision is fair towards an individual if it is the same in (a) the actual world and (b) a counterfactual world where the individual belonged to a different demographic group. We demonstrate our framework on a real-world problem of fair prediction of success in law school._

- Fairness Constraints: Mechanisms for Fair Classification
    <a name="Zafar:17"></a>
    [[Paper]](https://people.mpi-sws.org/~gummadi/papers/disparate_impact_AISTATS_2017.pdf)

    _Muhammad Bilal Zafar, Isabel Valera, Manuel Gomez Rodriguez, Krishna P. Gummadi (AISTATS 2017)_

    >_Algorithmic decision making systems are ubiquitous across a wide variety of online as well as offline services. These systems rely on complex learning methods and vast amounts of data to optimize the service functionality, satisfaction of the end user and profitability. However, there is a growing concern that these automated decisions can lead, even in the absence of intent, to a lack of fairness, i.e., their outcomes can disproportionately hurt (or, benefit) particular groups of people sharing one or more sensitive attributes (e.g., race, sex). In this paper, we introduce a flexible mechanism to design fair classifiers by leveraging a novel intuitive measure of decision boundary (un)fairness. We instantiate this mechanism with two well-known classifiers, logistic regression and support vector machines, and show on real-world data that our mechanism allows for a fine-grained control on the degree of fairness, often at a small cost in terms of accuracy. A Python implementation of our mechanism is available at fate-computing.mpi-sws.org_

- Learning Fair Classifiers: A Regularization-Inspired Approach
    <a name="Bechavod:17"></a>
    [[Paper]](https://arxiv.org/abs/1707.00044)

    _Yahav Bechavod, Katrina Ligett (ArXiv 2017)_

    >[Comments]: Presented as a poster at the 2017 Workshop on Fairness, Accountability, and Transparency in Machine Learning (FAT/ML 2017). Added acknowledgements

    >_We present a regularization-inspired approach for reducing bias in learned classifiers. In particular, we focus on binary classification tasks over individuals from two populations, where, as our criterion for fairness, we wish to achieve similar false positive rates in both populations, and similar false negative rates in both populations. As a proof of concept, we implement our approach and empirically evaluate its ability to achieve both fairness and accuracy, using the COMPAS scores data for prediction of recidivism._

- Identifying Significant Predictive Bias in Classifiers
    <a name="Zhang:17"></a>
    [[Paper]](https://arxiv.org/abs/1611.08292)

    _Zhe Zhang, Daniel B. Neill (ArXiv 2017)_

    >[Comments]:_Presented as a poster at the 2017 Workshop on Fairness, Accountability, and Transparency in Machine Learning (FAT/ML 2017); earlier version presented at NIPS 2016 Workshop on Interpretable Machine Learning in Complex_

    >_We present a novel subset scan method to detect if a probabilistic binary classifier has statistically significant bias -- over or under predicting the risk -- for some subgroup, and identify the characteristics of this subgroup. This form of model checking and goodness-of-fit test provides a way to interpretably detect the presence of classifier bias or regions of poor classifier fit. This allows consideration of not just subgroups of a priori interest or small dimensions, but the space of all possible subgroups of features. To address the difficulty of considering these exponentially many possible subgroups, we use subset scan and parametric bootstrap-based methods. Extending this method, we can penalize the complexity of the detected subgroup and also identify subgroups with high classification errors. We demonstrate these methods and find interesting results on the COMPAS crime recidivism and credit delinquency data._

- Inherent Trade-Offs in the Fair Determination of Risk Scores
    <a name="Kleinberg:17"></a>
    [[Paper]](https://arxiv.org/abs/1609.05807)

    _Jon Kleinberg, Sendhil Mullainathan, Manish Raghavan (ITCS 2017)_

    >_Recent discussion in the public sphere about algorithmic classification has involved tension between competing notions of what it means for a probabilistic classification to be fair to different groups. We formalize three fairness conditions that lie at the heart of these debates, and we prove that except in highly constrained special cases, there is no method that can satisfy these three conditions simultaneously. Moreover, even satisfying all three conditions approximately requires that the data lie in an approximate version of one of the constrained special cases identified by our theorem. These results suggest some of the ways in which key notions of fairness are incompatible with each other, and hence provide a framework for thinking about the trade-offs between them._

- On Fairness and Calibration 
    <a name="Pleiss:16"></a>
    [[Paper]](https://arxiv.org/pdf/1709.02012.pdf)

    _Geoff Pleiss, Manish Raghavan, Felix Wu, Jon Kleinberg, Kilian Q. Weinberger (NIPS 2017)_

    >_The machine learning community has become increasingly concerned with the potential for bias and discrimination in predictive models. This has motivated a growing line of work on what it means for a classification procedure to be “fair.” In this paper, we investigate the tension between minimizing error disparity across different population groups while maintaining calibrated probability estimates. We show that calibration is compatible only with a single error constraint (i.e. equal false-negatives rates across groups), and show that any algorithm that satisfies this relaxation is no better than randomizing a percentage of predictions for an existing classifier. These unsettling findings, which extend and generalize existing results, are empirically confirmed on several datasets._

- Equality of Opportunity in Supervised Learning
    <a name="Hardt:16"></a>
    [[Paper]](http://papers.nips.cc/paper/6373-equality-of-opportunity-in-supervised-learning)

    _Moritz Hardt, Eric Price, Nati Srebro (NIPS 2017)_

    >_We propose a criterion for discrimination against a specified sensitive attribute in supervised learning, where the goal is to predict some target based on available features. Assuming data about the predictor, target, and membership in the protected group are available, we show how to optimally adjust any learned predictor so as to remove discrimination according to our definition. Our framework also improves incentives by shifting the cost of poor classification from disadvantaged groups to the         decision maker, who can respond by improving the classification accuracy._

- A statistical framework for fair predictive algorithms
    <a name="Lum:16"></a>
    [[Paper]](https://arxiv.org/pdf/1610.08077.pdf)

    _Kristian Lum, James E. Johndrow (ArXiv 2016)_

    >_Predictive modeling is increasingly being employed to assist human decision-makers. One purported advantage of replacing human judgment with computer models in high stakes settings-- such as sentencing, hiring, policing, college admissions, and parole decisions-- is the perceived "neutrality" of computers. It is argued that because computer models do not hold personal prejudice, the predictions they produce will be equally free from prejudice. There is growing recognition that employing algorithms does not remove the potential for bias, and can even amplify it, since training data were inevitably generated by a process that is itself biased. In this paper, we provide a probabilistic definition of algorithmic bias. We propose a method to remove bias from predictive models by removing all information regarding protected variables from the permitted training data. Unlike previous work in this area, our framework is general enough to accommodate arbitrary data types, e.g. binary, continuous, etc. Motivated by models currently in use in the criminal justice system that inform decisions on pre-trial release and paroling, we apply our proposed method to a dataset on the criminal histories of individuals at the time of sentencing to produce "race-neutral" predictions of re-arrest. In the process, we demonstrate that the most common approach to creating "race-neutral" models-- omitting race as a covariate-- still results in racially disparate predictions. We then demonstrate that the application of our proposed method to these data removes racial disparities from predictions with minimal impact on predictive accuracy._
    
- Assessing Human Error Against a Benchmark of Perfection 
    <a name="Anderson:16"></a>
    [[Paper]](https://arxiv.org/pdf/1606.04956.pdf)

    _Ashton Anderson, Jon Kleinberg, Sendhil Mullainathan (KDD-2016)_

    >_An increasing number of domains are providing us with detailed trace data on human decisions in settings where we can evaluate the quality of these decisions via an algorithm. Motivated by this development an emerging line of work has begun to consider whether we can characterize and predict the kinds of decisions where people are likely to make errors. To investigate what a general framework for human error prediction might look like, we focus on a model system with a rich history in the behavioral sciences: the decisions made by chess players as they select moves in a game. We carry out our analysis at a large scale, employing datasets with several million recorded games, and using chess table bases to acquire a form of ground truth for a subset of chess positions that have been completely solved by computers but remain challenging even for the best players in the world. We organize our analysis around three categories of features that we argue are present in most settings where the analysis of human error is applicable: the skill of the decision-maker, the time available to make the decision, and the inherent difficulty of the decision. We identify rich structure in all three of these categories of features, and find strong evidence that in our domain, features describing the inherent difficulty of an instance are significantly more powerful than features based on skill or time._

- The Hidden Cost of Efficiency: Fairness and Discrimination 
    <a name="Adebayo:15"></a>
    [[Paper]](http://studyres.com/doc/7743082/the-hidden-cost-of-efficiency--fairness-and-discriminatio...)

    _Julius Adebayo, Lalana Kagal, and Alex Pentland (Predictive Modeling 2015)

    >_We present a data transformation procedure that completely eliminates all linear information regarding a sensitive at-tribute in a large scale individual level data with several correlated attributes. The algorithm presented here forms a component of a larger fairness rating system being developed. The goal of the rating system is to elucidate black-box models and bring interpretability to any predictive model no matter how complex. As part of the system, we learn lower dimensional interpretable versions of potentially complex models, attempt to learn a causal structure of the underlying data, and propose an augumentation to the underlying black-box algorithm as a way of reducing bias in predictive modeling.  This work is still ongoing, but here we highlight one component of the system: the orthogonal projection algorithm. The orthogonal projection algorithm combines principal components analysis of the data set with orthogonalization with respect to sensitive attribute(s). The orthogonalization algorithm presented is motivated by applications where there is a need to drastically ’sanitize’ a dataset of all information relating to sensitive(s) attribute(s) in the data, or that perhaps could be inferred from the data,before analysis of the data using a data mining algorithm.Our proposed methodology outperforms other privacy preserving methodologies by more than 20 percent in lowering the ability to reconstruct sensitive attribute from a sample large scale individual level data. In high stakes contexts such as determination of access to credit, employment, and insurance where discrimination based on sensitive attributes such as race, gender, and sexual orientation is prohibited by law,our proposed algorithm provides a way to help reduce the information content of such sensitive attributes in available data, hence limiting bias_

- Learning Fair Representations
    <a name="Zemel:13"></a>
    [[Paper]](http://proceedings.mlr.press/v28/zemel13.pdf)

    _Richard Zemel,Yu (Ledell) Wu, Kevin Swersky,  Toniann Pitassi (ICML 2013)_

    >_We propose a learning algorithm for fair classification that achieves both group fairness (the proportion of members in a protected group receiving positive classification is identical to the proportion in the population as a whole), and individual fairness (similar individuals should be treated similarly). We formulate fairness as an optimization problem of finding a good representation of the data with two competing goals: to encode the data as well as possible, while simultaneously obfuscating any information about membership in the protected group. We show positive results of our algorithm relative to other known techniques, on three datasets. Moreover, we demonstrate several advantages to our approach. First, our intermediate representation can be used for other classification tasks (i.e., transfer learning is possible); secondly, we take a step toward learning a distance metric which can find important dimensions of the data for classification._

- Fairness Through Awareness 
    <a name="Dwork:12"></a>
    [[Paper]](https://arxiv.org/pdf/1104.3913.pdf)

    _Cynthia Dwork, Moritz Hardt, Toniann Pitassi, Omer Reingold, Rich Zemel (ITCS 2012)_

    >_We study fairness in classification, where individuals are classified, e.g., admitted to a university, and the goal is to prevent discrimination against individuals based on their membership in some group, while maintaining utility for the classifier (the university). The main conceptual contribution of this paper is a framework for fair classification comprising (1) a (hypothetical) task-specific metric for determining the degree to which individuals are similar with respect to the classification task at hand; (2) an algorithm for maximizing utility subject to the fairness constraint, that similar individuals are treated similarly. We also present an adaptation of our approach to achieve the complementary goal of "fair affirmative action," which guarantees statistical parity (i.e., the demographics of the set of individuals receiving any classification are the same as the demographics of the underlying population), while treating similar individuals as similarly as possible. Finally, we discuss the relationship of fairness to privacy: when fairness implies privacy, and how tools developed in the context of differential privacy may be applied to fairness._

- Discrimination-aware Data Mining
    <a name="Pedreschi:08"></a>
    [[Paper]](http://pages.di.unipi.it/ruggieri/Papers/kdd2008.pdf)

    _Dino Pedreschi, Salvatore Ruggieri, Franco Turini (KDD 2008)_

    >_In the context of civil rights law, discrimination refers to unfair or unequal treatment of people based on membership to a category or a minority, without regard to individual merit. Rules extracted from databases by data mining techniques, such as classification or association rules, when used for decision tasks such as benefit or credit approval, can be discriminatory in the above sense. In this paper, the notion of discriminatory classification rules is introduced and studied. Providing a guarantee of non-discrimination is shown to be a non trivial task. A na¨ıve approach, like taking away all discriminatory attributes, is shown to be not enough when other background knowledge is available. Our approach leads to a precise formulation of the redlining problem along with a formal result relating discriminatory rules with apparently safe ones by means of background knowledge. An empirical assessment of the results on the German credit dataset is also provided._

## Other resources

### Video Lectures
[-] [Turing Lecture: Privacy-Preserving Data Analysis - Cynthia Dwork](https://www.youtube.com/watch?v=vsA4w3itxA0) YouTube video
- [Challenges in Ethics and Computing” at ACM Turing 50 Celebration](https://www.youtube.com/watch?v=Z45LI-NyLP0) YouTube video
- [Quantifying tradeoffs between fairness and accuracy in online learning - Aaron Roth](https://www.youtube.com/watch?v=tBpd4Ix4BYM&list=PLUPbk8hS1PnPwvwjJAhobt6kUHx4qkAJ6) YouTube video
- [Artificial Intelligence & Bias: Past, Present & Future](https://www.youtube.com/watch?v=uQJTtBPk7Qk) YouTube video
- [Artificial Intelligence & Bias: Past, Present & Future Q&A](https://www.youtube.com/watch?v=rRUGSlVOW1k) YouTube video
- [Algorithms and Bias](https://www.nytimes.com/2015/08/11/upshot/algorithms-and-bias-q-and-a-with-cynthia-dwork.html) Article


### Media-articles

- Google ads, black names and white names, racial discrimination, and click advertising
    [Paper](http://delivery.acm.org/10.1145/2470000/2460278/p10-sweeney.pdf?ip=68.40.62.108&id=2460278&acc=OPEN&key=4D4702B0C3E38B35%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35%2E6D218144511F3437&__acm__=1519430087_76b88b3e8b52bcbb475b0cb44e9536d7) 
