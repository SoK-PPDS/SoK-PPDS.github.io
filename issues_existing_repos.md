## Issues with Existing Repositories

### A Common Issue

We idendify a common flaw in the experimental evaluation in several works---when comparing with the baselines, they would directly copy the results from the prior works instead of re-running their code. What's worse, errors can happen during the copy-paste. For example, the table 3 of DPGEN copied results from Table 1 of DataLens, which copied results from Table 1(c) of G-PATE. The result for CelebA-Gender under $\varepsilon=1$ by DataLens was 0.7058 in DataLens paper but changed to 0.6996 in DPGEN paper. 

We strongly advocate re-running the code from the prior works to one's best ability for academic rigor. Whether one can reproduce the results that are similar to those reported in the prior works, the practice of trying to reproducing the results can further consolidate the community's understanding of the prior works, and the findings will invariably be of great significance.

### DPGEN

Paper url: [https://openaccess.thecvf.com/content/CVPR2022/html/Chen_DPGEN_Differentially_Private_Generative_Energy-Guided_Network_for_Natural_Image_Synthesis_CVPR_2022_paper.html](https://openaccess.thecvf.com/content/CVPR2022/html/Chen_DPGEN_Differentially_Private_Generative_Energy-Guided_Network_for_Natural_Image_Synthesis_CVPR_2022_paper.html)

Repository url: [https://github.com/chiamuyu/DPGEN](https://github.com/chiamuyu/DPGEN)

- **Missing documentation and unprofessional repository**: The repository contains a ``README.md`` file with no actual content in it. The code is provided in ``DPGEN-SIMPLE.zip`` which is not very professional.
- **Un-runnable code**: Extracting the content from ``DPGEN-SIMPLE.zip`` gives code that is not runnable. There’s a ``NCSNRunner`` in line 161 of ``main.py``, but there’s no ``NCSNRunner`` class anywhere in the code. Changing ``NCSNRunner`` to ``Runner`` can fix the issue. In addition, the ``Runner`` class does not contain a ``test`` function which was required in ``main.py``.
- **Incorrect configuration**: The authors set ``random_flip: true`` for MNIST in ``./configs/mnist.yml``, which does not make sense. We never want our generator to produce digits that are flipped. 
- **Missing configurations for $\varepsilon=1$ and $\varepsilon=0.2$**: The paper reported results for MNIST and Fashion-MNIST on $\varepsilon=1$ and $\varepsilon=0.2$ in Tables 3 and 4, but neither the paper nor the repository provided the hyper-parameters for these two settings. Similarly, the paper reported results on two other datasets CelebA and LSUN-bedroom, but the associated code and configurations are missing in the repository. 
- **Severe limitation of the approach**: DPGEN can only generate images but not labels. The authors didn't mention this in their paper. From our email communication with them, we learned that the way they produce labels is through training a classifier to produce labels. This was not clarified in the paper as well. 
- **Potential privacy leakage**: Training a classifier on the private dataset to label the generated data exhibits privacy concerns. We inquired the authors about the issue, and the authors confirmed the issue and further clarified that "To address this, we suggest training the classifier on a dataset different from the one used to train DPGEN. For instance, some studies split their dataset into public and private parts, and only the private dataset needs to be trained with DPGEN." However, upon examining their code, we found that ``train_fashion_mnist_cls.ipynb`` actually trains a classifier on the private dataset, meaning that the results in the paper may not strictly respect the reported $\varepsilon$ values. 
- **Failure to offer due credit**: In fact, the approach for data generation comes from the paper [*Improved Techniques for Training Score-Based Generative Models*](http://arxiv.org/abs/2006.09011) and the repository is adapted upon [theirs](https://github.com/ermongroup/ncsnv2). But the authors didn't even cite this work in their paper; nor did they cite the repository in their repository.

### PATE-GAN

Paper url: [https://openreview.net/forum?id=S1zk9iRqF7](https://openreview.net/forum?id=S1zk9iRqF7)

Repository url: [https://github.com/vanderschaarlab/mlforhealthlabpub/tree/main/alg/pategan](https://github.com/vanderschaarlab/mlforhealthlabpub/tree/main/alg/pategan)


- In ``pate_gan.py``
  - **Variable value error**: Line 190 goes as ``for _ in range(k):``, yet the code needs to extract the corresponding segment in data by index, i.e., ``temp_x = x_partition[i]`` in line 195. The loop variable ``i`` here does not get updated; its value is inherited from the loop from line 106-109.
  - **Exceeding the privacy budget**: Line 185 goes as ``while epsilon_hat < epsilon``, which means that the accumulated privacy cost ``epsilon_hat`` has already exceeded the budget ``epsilon`` at the time of breaking out of the loop, presenting a privacy violation.
- In ``main_pategan_experiment.py``
  - **Variable type error**: Line 171-175 specifies the argument "the number of teachers" $k$. Its type should be ``int`` instead of ``float`` as written in line 175.
- **Inapplicability to image datasets**: PATE-GAN was proposed and evaluated on tabular data only in their paper. Although G-PATE evaluated PATE-GAN and reported non-trivial results, we had similar findings as what GS-WGAN reported in their Appendix C.4 --- “the generated samples are classiﬁed as fake by all teacher discriminators and the learning signals (gradients) for student discriminator and the generator vanish.”