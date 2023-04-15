## Data Utility and Fidelity Measures

We present the **fidelity** and **utility** measures for the synthetic data, where fidelity measures include various intrinsic properties of synthetic data, and utility measures refer to the performance of synthetic data when used for downstream applications.  

Let ``F`` denote *fidelity*, and ``A`` denote *application*.

We organize this section based on different data types.
For structured data, we study **tabular** data (``S1``), **trajectory** data (``S2``), and **graph** data (``S3``). 
For unstructured data, we consider **image** data (``U1``).

Note that ``[ ]`` contains the detailed evaluation protocol (usually a similarity/value function). 

### Tabular

- **S1-F1.** Similarity w.r.t. k-way marginals 

  - [$L_1$ distance (average error)]: [Zhang et al., 2014](http://dimacs.rutgers.edu/~graham/pubs/papers/PrivBayes.pdf), [Gaboardi et al., 2014](https://arxiv.org/pdf/1402.1526.pdf), [Bindschaedler et al., 2016](https://arxiv.org/pdf/1708.07975.pdf), [Asghar et al., 2019](https://arxiv.org/pdf/1902.01499.pdf), [McKenna et al., 2021](https://arxiv.org/pdf/2108.04978.pdf), [Zhang et al., 2021](https://arxiv.org/pdf/2012.15128.pdf), [Cai et al., 2021](http://www.vldb.org/pvldb/vol14/p2190-cai.pdf), [Liew et al., 2022](https://arxiv.org/pdf/2106.04590.pdf)

  - [$L_2$ distance]: [Chen et al., 2015](https://www.comp.hkbu.edu.hk/~xujl/Papers/kdd15.pdf)

  - [$L_\infty$ distance (max error)]: [Asghar et al., 2019](https://arxiv.org/pdf/1902.01499.pdf), [Vietri et al., 2020](https://arxiv.org/pdf/2007.05453.pdf), [Aydore et al., 2021](https://arxiv.org/pdf/2103.06641.pdf)

  - [Kullback-Leibler (KL) divergence]: [Hardt et al., 2012](https://arxiv.org/pdf/1012.4763.pdf)

  - [Kolmogorov-Smirnov distance ([Massey Jr, 1951](https://www.jstor.org/stable/2280095#metadata_info_tab_contents))]: [Gambs et al., 2021](https://petsymposium.org/popets/2021/popets-2021-0040.pdf)


* **S1-F2.** Similarity w.r.t. other queries [$L_1$ distance]

  - Random linear queries: [Xu et al., 2017](https://ieeexplore.ieee.org/ielaam/10206/8017695/8006304-aam.pdf)

  - Range queries: [Hardt et al., 2012](https://arxiv.org/pdf/1012.4763.pdf), [Li et al., 2014](http://www.openproceedings.org/EDBT/2014/paper_74.pdf), [Zhang et al., 2021](https://arxiv.org/pdf/2012.15128.pdf), [Liew et al., 2022](https://arxiv.org/pdf/2106.04590.pdf)

  - Parity queries: [Gaboardi et al., 2014](https://arxiv.org/pdf/1402.1526.pdf)

  - Aggregation queries: [Fan et al., 2020](https://arxiv.org/pdf/2008.12763.pdf)


* **S1-F3.** Similarity w.r.t. the matrix

  - [Frobenius distance]:[ Li et al., 2011](https://arxiv.org/pdf/1107.3350.pdf), [Jiang et al., 2013](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3883117/)

  - [Mean Correlation Delta]: [Gambs et al., 2021](https://petsymposium.org/popets/2021/popets-2021-0040.pdf), [Lu et al. 2017](https://dl.acm.org/doi/10.1145/3133956.3138823)


* **S1-F4.** Similarity w.r.t. pairwise $L_2$ distances: [Xu et al., 2017](https://ieeexplore.ieee.org/ielaam/10206/8017695/8006304-aam.pdf)

* **S1-F5.** Distinguishing game: [Bindschaedler et al., 2016](https://arxiv.org/pdf/1708.07975.pdf)

* **S1-F6.** Classification similarity [Matthews Correlation Coefficient (MCC) ([Matthews, 1975](https://www.sciencedirect.com/science/article/abs/pii/0005279575901099))]: [Gambs et al., 2021](https://petsymposium.org/popets/2021/popets-2021-0040.pdf)

* **S1-A1.** Classification [accuracy/misclassification rate/Area Under the Receiver Operating Characteristics(AUROC)]

  - SVM: [Zhang et al., 2014](http://dimacs.rutgers.edu/~graham/pubs/papers/PrivBayes.pdf), [Chen et al., 2015](https://www.comp.hkbu.edu.hk/~xujl/Papers/kdd15.pdf), [Xu et al., 2017](https://ieeexplore.ieee.org/ielaam/10206/8017695/8006304-aam.pdf), [Chanyaswad et al., 2019](https://www.princeton.edu/~pmittal/publications/ron-gauss-pets19.pdf), [Zhang et al., 2021](https://arxiv.org/pdf/2012.15128.pdf), [Cai et al., 2021](http://www.vldb.org/pvldb/vol14/p2190-cai.pdf), [Beaulieu-Jones et al., 2019](https://www.ahajournals.org/doi/full/10.1161/CIRCOUTCOMES.118.005122?rfr_dat=cr_pub++0pubmed&url_ver=Z39.88-2003&rfr_id=ori%3Arid%3Acrossref.org), [Astolfi et al., 2021](https://unece.org/sites/default/files/2021-12/SDC2021_Day2_Astolfi_AD.pdf), [Jordon et al., 2019](https://openreview.net/pdf?id=S1zk9iRqF7), [Harder et al., 2020](https://arxiv.org/pdf/2002.11603.pdf)

  - Boosting: [Bindschaedler et al., 2016](https://arxiv.org/pdf/1708.07975.pdf), [Gambs et al., 2021](https://petsymposium.org/popets/2021/popets-2021-0040.pdf), [Fan et al., 2020](https://arxiv.org/pdf/2008.12763.pdf), [Jordon et al., 2019](https://openreview.net/pdf?id=S1zk9iRqF7), [Long et al., 2021](https://papers.nips.cc/paper/2021/file/171ae1bbb81475eb96287dd78565b38b-Paper.pdf), [Harder et al., 2020](https://arxiv.org/pdf/2002.11603.pdf)

  - Random forest: [Bindschaedler et al., 2016](https://arxiv.org/pdf/1708.07975.pdf), [Fan et al., 2020](https://arxiv.org/pdf/2008.12763.pdf), [Beaulieu-Jones et al., 2019](https://www.ahajournals.org/doi/full/10.1161/CIRCOUTCOMES.118.005122?rfr_dat=cr_pub++0pubmed&url_ver=Z39.88-2003&rfr_id=ori%3Arid%3Acrossref.org), [Hyland et al., 2017](https://arxiv.org/pdf/1706.02633.pdf), [Jordon et al., 2019](https://openreview.net/pdf?id=S1zk9iRqF7), [Harder et al., 2020](https://arxiv.org/pdf/2002.11603.pdf)

  - Decision tree: [Bindschaedler et al., 2016](https://arxiv.org/pdf/1708.07975.pdf), [Fan et al., 2020](https://arxiv.org/pdf/2008.12763.pdf), [Jordon et al., 2019](https://openreview.net/pdf?id=S1zk9iRqF7), [Harder et al., 2020](https://arxiv.org/pdf/2002.11603.pdf)

  - Bagging: [Jordon et al., 2019](https://openreview.net/pdf?id=S1zk9iRqF7), [Long et al., 2021](https://papers.nips.cc/paper/2021/file/171ae1bbb81475eb96287dd78565b38b-Paper.pdf), [Harder et al., 2020](https://arxiv.org/pdf/2002.11603.pdf)

  - Multilayer Perceptron: [Jordon et al., 2019](https://openreview.net/pdf?id=S1zk9iRqF7), [Long et al., 2021](https://papers.nips.cc/paper/2021/file/171ae1bbb81475eb96287dd78565b38b-Paper.pdf), [Harder et al., 2020](https://arxiv.org/pdf/2002.11603.pdf)


* **S1-A2.** Regression [root mean square error (RMSE) ([Bishop, 2006](https://link.springer.com/book/9780387310732))/AUROC]

  - Kernel Ridge Regression: [Chanyaswad et al., 2019](https://www.princeton.edu/~pmittal/publications/ron-gauss-pets19.pdf) 

  - Linear regression: [Gambs et al., 2021](https://petsymposium.org/popets/2021/popets-2021-0040.pdf), [Fan et al., 2020](https://arxiv.org/pdf/2008.12763.pdf), [Beaulieu-Jones et al., 2019](https://www.ahajournals.org/doi/full/10.1161/CIRCOUTCOMES.118.005122?rfr_dat=cr_pub++0pubmed&url_ver=Z39.88-2003&rfr_id=ori%3Arid%3Acrossref.org), [Astolfi et al., 2021](https://unece.org/sites/default/files/2021-12/SDC2021_Day2_Astolfi_AD.pdf), [Jordon et al., 2019](https://openreview.net/pdf?id=S1zk9iRqF7), [Long et al., 2021](https://papers.nips.cc/paper/2021/file/171ae1bbb81475eb96287dd78565b38b-Paper.pdf), [Harder et al., 2020](https://arxiv.org/pdf/2002.11603.pdf)


* **S1-A3.** Clustering 

  - [Silhouette Coefficient ([Rousseeuw, 1987](https://reader.elsevier.com/reader/sd/pii/0377042787901257?token=E6952FD6817ABB851AE66680D20AB0F496819B18A7B225E4ADFE95E022D885F8E6198433C8DB5AE63BA5DD19DE765D10&originRegion=us-east-1&originCreation=20220822164001))]: [Chanyaswad et al., 2019](https://www.princeton.edu/~pmittal/publications/ron-gauss-pets19.pdf)

  - [Normalized Mutual Information]: [Fan et al., 2020](https://arxiv.org/pdf/2008.12763.pdf)


### **Trajectory**

- **S2-F1.** Similarity w.r.t. count queries [relative error]: [Chen et al., 2012a](https://dmas.lab.mcgill.ca/fung/pub/CFDS12kdd.pdf), [Chen et al., 2012b](https://hal.inria.fr/hal-00747830/PDF/Differentially_private_sequential_data_publication_via_n-grams.pdf), [Zhang et al., 2016](https://arxiv.org/pdf/1601.03229.pdf), [Roy et al., 2016](https://hal.inria.fr/hal-01633671/document), [Gursoy et al., 2018a](https://ieeexplore.ieee.org/ielaam/7755/8821494/8481494-aam.pdf), [Gursoy et al., 2018b](https://mysite.ku.edu.tr/emregursoy/wp-content/uploads/sites/263/2020/09/gursoy-ccs18.pdf), [Gursoy et al., 2020](https://arxiv.org/pdf/2009.06505.pdf)

- **S2-F2.** Similarity w.r.t. frequent patterns
  - [True/false positive]: [Chen et al., 2012a](https://dmas.lab.mcgill.ca/fung/pub/CFDS12kdd.pdf), [Roy et al., 2016](https://hal.inria.fr/hal-01633671/document)
  - [Precision]: [Chen et al., 2012b](https://hal.inria.fr/hal-00747830/PDF/Differentially_private_sequential_data_publication_via_n-grams.pdf), [Zhang et al., 2016](https://arxiv.org/pdf/1601.03229.pdf)
  - [Average relative error]: [Chen et al., 2012b](https://hal.inria.fr/hal-00747830/PDF/Differentially_private_sequential_data_publication_via_n-grams.pdf), [Gursoy et al., 2018a](https://ieeexplore.ieee.org/ielaam/7755/8821494/8481494-aam.pdf), [Gursoy et al., 2018b](https://mysite.ku.edu.tr/emregursoy/wp-content/uploads/sites/263/2020/09/gursoy-ccs18.pdf), [Gursoy et al., 2020](https://arxiv.org/pdf/2009.06505.pdf)
  - [$F_1$ score]: [He et al., 2015](http://www.vldb.org/pvldb/vol8/p1154-he.pdf), [Gursoy et al., 2018b](https://mysite.ku.edu.tr/emregursoy/wp-content/uploads/sites/263/2020/09/gursoy-ccs18.pdf)
  - Locations’ popularity ranking [Kendall-tau coefficient]: [Gursoy et al., 2018a](https://ieeexplore.ieee.org/ielaam/7755/8821494/8481494-aam.pdf), [Gursoy et al., 2018b](https://mysite.ku.edu.tr/emregursoy/wp-content/uploads/sites/263/2020/09/gursoy-ccs18.pdf)
- **S2-F3.** Longest common subsequence (LCSS) ([Vlachos et al., 2002](http://alumni.cs.ucr.edu/~mvlachos/pubs/icde02.pdf)): [Wang and Sinnott, 2017](https://rest.neptune-prod.its.unimelb.edu.au/server/api/core/bitstreams/89860bd8-54a1-58d6-96be-b09ebf7491f6/content)

- **S2-F4.** Similarity w.r.t. spatial location
  - [Earth Mover’s Distance (EMD) ([Rubner et al., 2000](https://www.cs.cmu.edu/~efros/courses/LBMV07/Papers/rubner-jcviu-00.pdf))]: [Mir et al., 2013](https://mrmgroup.cs.princeton.edu/papers/bigdata13.pdf), [Roy et al., 2016](https://hal.inria.fr/hal-01633671/document)
  - [Euclidean distance]: [Wang and Sinnott, 2017](https://rest.neptune-prod.its.unimelb.edu.au/server/api/core/bitstreams/89860bd8-54a1-58d6-96be-b09ebf7491f6/content)
  - [Dynamic Time Warping (DTW)]: [Wang and Sinnott, 2017](https://rest.neptune-prod.its.unimelb.edu.au/server/api/core/bitstreams/89860bd8-54a1-58d6-96be-b09ebf7491f6/content)
  - [Edit Distance on Real sequence (EDR) ([Chen et al., 2005](https://dl.acm.org/doi/10.1145/1066157.1066213))]: [Wang and Sinnott, 2017](https://rest.neptune-prod.its.unimelb.edu.au/server/api/core/bitstreams/89860bd8-54a1-58d6-96be-b09ebf7491f6/content)
- **S2-F5.** Similarity w.r.t. length distribution 
  - [Jenson-Shannon divergence ([Fuglede and Topsoe, 2004](https://ieeexplore.ieee.org/document/1365067/))]: [Gursoy et al., 2018a](https://ieeexplore.ieee.org/ielaam/7755/8821494/8481494-aam.pdf), [Gursoy et al., 2018b](https://mysite.ku.edu.tr/emregursoy/wp-content/uploads/sites/263/2020/09/gursoy-ccs18.pdf), [Gursoy et al., 2020](https://arxiv.org/pdf/2009.06505.pdf)
  - [$L_1$ distance]: [Zhang et al., 2016](https://arxiv.org/pdf/1601.03229.pdf)
- **S2-F6.** Similarity w.r.t. diameter distribution
  - [Jenson-Shannon divergence]: [He et al., 2015](http://www.vldb.org/pvldb/vol8/p1154-he.pdf), [Gursoy et al., 2018a](https://ieeexplore.ieee.org/ielaam/7755/8821494/8481494-aam.pdf), [Gursoy et al., 2018b](https://mysite.ku.edu.tr/emregursoy/wp-content/uploads/sites/263/2020/09/gursoy-ccs18.pdf)
  - [Histogram]: [Mir et al., 2013](https://mrmgroup.cs.princeton.edu/papers/bigdata13.pdf)
- **S2-F7.** Similarity w.r.t. trip distribution [Jenson-Shannon divergence]: [He et al., 2015](http://www.vldb.org/pvldb/vol8/p1154-he.pdf), [Gursoy et al., 2018a](https://ieeexplore.ieee.org/ielaam/7755/8821494/8481494-aam.pdf), [Gursoy et al., 2018b](https://mysite.ku.edu.tr/emregursoy/wp-content/uploads/sites/263/2020/09/gursoy-ccs18.pdf), [Gursoy et al., 2020](https://arxiv.org/pdf/2009.06505.pdf)

### **Graph**

- **S3-F1.** (Joint) degree distribution: [Sala et al., 2011](https://conferences.sigcomm.org/imc/2011/docs/p81.pdf), [Mir and Wright, 2012](https://www.cs.columbia.edu/~rwright/Publications/pais12.pdf), [Xiao et al., 2014](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.710.2926&rep=rep1&type=pdf), [Jorgensen et al., 2016](http://dimacs.rutgers.edu/~graham/pubs/papers/attributedgraph.pdf), [Chen et al., 2020](https://arxiv.org/pdf/1909.00280.pdf), [Zhang et al., 2021](https://www.sciencedirect.com/science/article/pii/S0167404821001097), [Yang et al., 2020](https://arxiv.org/pdf/2005.00455.pdf)

- **S3-F2.** Assortativity: [Sala et al., 2011](https://conferences.sigcomm.org/imc/2011/docs/p81.pdf), [Wang and Wu, 2013](http://aimlab.cs.uoregon.edu/SMASH/papers/TDP13.pdf)

- **S3-F3.** Shortest/average/weighted path distance: [Sala et al., 2011](https://conferences.sigcomm.org/imc/2011/docs/p81.pdf), [Wang and Wu, 2013](http://aimlab.cs.uoregon.edu/SMASH/papers/TDP13.pdf), [Xiao et al., 2014](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.710.2926&rep=rep1&type=pdf)

- **S3-F4.** Global/local clustering coefficients: [Mir and Wright, 2012](https://www.cs.columbia.edu/~rwright/Publications/pais12.pdf), [Wang and Wu, 2013](http://aimlab.cs.uoregon.edu/SMASH/papers/TDP13.pdf), [Jorgensen et al., 2016](http://dimacs.rutgers.edu/~graham/pubs/papers/attributedgraph.pdf), [Chen et al., 2020](https://arxiv.org/pdf/1909.00280.pdf)

- **S3-F5.** Attribute-edge correlations [Hellinger distance]: [Jorgensen et al., 2016](http://dimacs.rutgers.edu/~graham/pubs/papers/attributedgraph.pdf), [Chen et al., 2020](https://arxiv.org/pdf/1909.00280.pdf)

- **S3-F6.** Community stucture

  - [Modularity]: [Wang and Wu, 2013](http://aimlab.cs.uoregon.edu/SMASH/papers/TDP13.pdf)
  - [Precision and recall]: [Chen et al., 2020](https://arxiv.org/pdf/1909.00280.pdf)

- **S3-F7.** Parameter estimation: [Lu and Miklau, 2014](https://people.cs.umass.edu/~miklau/assets/pubs/dp/Lu14Exponential-revised.pdf)

- **S3-F8.** Number of statistics

  - Nodes: [Wang and Wu, 2013](http://aimlab.cs.uoregon.edu/SMASH/papers/TDP13.pdf)
  - Edges: [Wang and Wu, 2013](http://aimlab.cs.uoregon.edu/SMASH/papers/TDP13.pdf), [Jorgensen et al., 2016](http://dimacs.rutgers.edu/~graham/pubs/papers/attributedgraph.pdf), [Chen et al., 2020](https://arxiv.org/pdf/1909.00280.pdf), [Zheng et al., 2021](https://arxiv.org/pdf/2111.09085.pdf)

  - Reachable pairs of nodes within $h$ hopes: [Mir and Wright, 2012](https://www.cs.columbia.edu/~rwright/Publications/pais12.pdf)
  - Average degree: [Wang and Wu, 2013](http://aimlab.cs.uoregon.edu/SMASH/papers/TDP13.pdf)
  - Max degree: [Zheng et al., 2021](https://arxiv.org/pdf/2111.09085.pdf)
  - Triangle: [Wang and Wu, 2013](http://aimlab.cs.uoregon.edu/SMASH/papers/TDP13.pdf), [Jorgensen et al., 2016](http://dimacs.rutgers.edu/~graham/pubs/papers/attributedgraph.pdf), [Chen et al., 2020](https://arxiv.org/pdf/1909.00280.pdf), [Zheng et al., 2021](https://arxiv.org/pdf/2111.09085.pdf)
  - Other alternating statistics: [Lu and Miklau, 2014](https://people.cs.umass.edu/~miklau/assets/pubs/dp/Lu14Exponential-revised.pdf), [Zheng et al., 2021](https://arxiv.org/pdf/2111.09085.pdf)

- **S3-F9.** Spectrum (node) analysis 

  - Similarity w.r.t. eigenvector centrality: [Xiao et al., 2014](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.710.2926&rep=rep1&type=pdf)
  - Largest eigenvalue of the adjacent matrix: [Wang and Wu, 2013](http://aimlab.cs.uoregon.edu/SMASH/papers/TDP13.pdf)
  - Leading eigenvector of the adjacent matrix: [Mir and Wright, 2012](https://www.cs.columbia.edu/~rwright/Publications/pais12.pdf)
  - Spectrum of the adjacent matrix: [Mir and Wright, 2012](https://www.cs.columbia.edu/~rwright/Publications/pais12.pdf)

- **S3-A1.** Reliable Email ([Garriss et al., 2006](https://www.usenix.org/legacy/event/nsdi06/tech/full_papers/garriss/garriss.pdf)): [Sala et al., 2011](https://conferences.sigcomm.org/imc/2011/docs/p81.pdf)

- **S3-A2.** Influence maximization ([Chen et al., 2009](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/weic-kdd09_influence.pdf)): [Sala et al., 2011](https://conferences.sigcomm.org/imc/2011/docs/p81.pdf)

- **S3-A3.** Link prediction: [Zheng et al., 2021](https://arxiv.org/pdf/2111.09085.pdf), [Yang et al., 2020](https://arxiv.org/pdf/2005.00455.pdf)

The readers can refer to ([Costa et al., 2007](https://www.researchgate.net/publication/232874573_Characterization_of_Complex_Networks_A_Survey_of_measurements)) for a comprehensive survey of the common utility metrics in graph. 

### **Image data**

- **U1-F1**. Inception Score (IS) ([Salimans et al., 2016](https://arxiv.org/abs/1606.03498)): [Liu et al. 2019](https://arxiv.org/pdf/1910.02007.pdf), [Wang et al., 2020](https://link.springer.com/chapter/10.1007/978-3-030-61609-0_46), [Zhang et al., 2018](https://arxiv.org/pdf/1801.01594.pdf), [Xu et al., 2019](https://ieeexplore.ieee.org/document/8636556), [Yang et al., 2020](https://ieeexplore.ieee.org/document/9343179), [Schwabedal et al., 2020](https://arxiv.org/pdf/2005.00783.pdf), [Chen et al., 2020](https://arxiv.org/pdf/2006.08265.pdf), [Long et al., 2021](https://papers.nips.cc/paper/2021/file/171ae1bbb81475eb96287dd78565b38b-Paper.pdf), [Zhang et al., 2019](https://ieeexplore.ieee.org/document/9014134), [Chen et al., 2022](https://openaccess.thecvf.com/content/CVPR2022/papers/Chen_DPGEN_Differentially_Private_Generative_Energy-Guided_Network_for_Natural_Image_Synthesis_CVPR_2022_paper.pdf), [Xin et al., 2022](https://www.sciencedirect.com/science/article/pii/S0925231221015058)

- **U1-F2.** Frechet Inception Distance (FID) ([Heusel el al., 2017](https://proceedings.neurips.cc/paper/2017/hash/8a1d694707eb0fefe65871369074926d-Abstract.html)): [Schwabedal et al., 2020](https://arxiv.org/pdf/2005.00783.pdf), [Chen et al., 2020](https://arxiv.org/pdf/2006.08265.pdf), [Long et al., 2021](https://papers.nips.cc/paper/2021/file/171ae1bbb81475eb96287dd78565b38b-Paper.pdf), [Liew et al., 2022](https://arxiv.org/pdf/2106.04590.pdf), [Chen et al., 2022](https://openaccess.thecvf.com/content/CVPR2022/papers/Chen_DPGEN_Differentially_Private_Generative_Energy-Guided_Network_for_Natural_Image_Synthesis_CVPR_2022_paper.pdf), [Xin et al., 2022](https://www.sciencedirect.com/science/article/pii/S0925231221015058)

- **U1-F3.** Kernel Inception Distance (KID) ([Bińkowski et al., 2018](https://arxiv.org/abs/1801.01401)): [Liew et al., 2022](https://arxiv.org/pdf/2106.04590.pdf)

- **U1-F4.** Jensen-Shannon Scores ([Fuglede et al., 2004](https://ieeexplore.ieee.org/abstract/document/1365067)): [Zhang et al., 2018](https://arxiv.org/pdf/1801.01594.pdf), [Xu et al., 2019](https://ieeexplore.ieee.org/document/8636556), [Yang et al., 2020](https://ieeexplore.ieee.org/document/9343179)

- **U1-A1.** Classification [accuracy/error]: [Liu et al. 2019](https://arxiv.org/pdf/1910.02007.pdf), [Xie et al. 2018](https://arxiv.org/pdf/1802.06739.pdf), [Frigerio et al. 2019](https://link.springer.com/chapter/10.1007/978-3-030-22312-0_11), [Zhang et al., 2018](https://arxiv.org/pdf/1801.01594.pdf), [Xu et al., 2019](https://ieeexplore.ieee.org/document/8636556), [Yang et al., 2020](https://ieeexplore.ieee.org/document/9343179), [Chen et al., 2020](https://arxiv.org/pdf/2006.08265.pdf), [Torkzadehmahani et al., 2019](https://arxiv.org/pdf/2001.09700.pdf), [Triastcyn et al., 2020](https://arxiv.org/pdf/2003.00997.pdf), [Long et al., 2021](https://papers.nips.cc/paper/2021/file/171ae1bbb81475eb96287dd78565b38b-Paper.pdf), [Wang et al., 2021](https://arxiv.org/abs/2103.11109), [Ma et al., 2020](https://arxiv.org/pdf/2007.02056.pdf), [Imtiaz et al., 2021](https://ieeexplore.ieee.org/document/9522203), [Harder et al., 2020](https://arxiv.org/pdf/2002.11603.pdf), [Chen et al., 2022](https://openaccess.thecvf.com/content/CVPR2022/papers/Chen_DPGEN_Differentially_Private_Generative_Energy-Guided_Network_for_Natural_Image_Synthesis_CVPR_2022_paper.pdf), [Zhang et al., 2021](https://arxiv.org/abs/2104.12581), [Triastcyn et al., 2020](https://ieeexplore.ieee.org/document/9091604)

- **U1-A2.** Segmentation [Hausdorﬀ distance]: [Schwabedal et al., 2020](https://arxiv.org/pdf/2005.00783.pdf)

- **U1-A3.** Data Debugging [visualization]: [Chen et al., 2020](https://arxiv.org/pdf/2006.08265.pdf), [Triastcyn et al., 2020](https://arxiv.org/pdf/2003.00997.pdf), [Augenstein et al., 2020](
