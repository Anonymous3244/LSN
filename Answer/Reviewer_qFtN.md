>**Q1:**  My main concern regarding this paper is mainly about originality. The authors' claim of their proposed method being "the first symmetry-aware AI-based method for solving SDEs" appears somewhat overstated due to the following reasons. 
And  utilizing the Lie point symmetry to regularize PINNs when solving parabolic PDEs is not entirely novel, as evidenced by a relevant work (not cited by the authors):[1]. The title of [1] explicitly suggests the introduction of a loss function that informs PINNs about how well their solutions adhere to Lie point symmetries when learning PDEs. [1] validates its proposed approach for the heat equation, which is closely related to the Black-Scholes equation. Therefore, I believe a comparison between the proposed LSN and [1] would be beneficial, along with a discussion of the pros and cons of the LSN in relation to existing approaches.

**A1:**  Thanks. We apologise that we overlooked this paper. We have duly cited the paper, added a detailed discussion, and conducted comparison experiments as follows.

#### Performance Comparison between Our LSN and LPS by Akhound-Sadegh et al. (2023)

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_1.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_2.png width=400 height=300 />

The equation parameters are set as follows: $\sigma = 0.4$, $r = 0.11$, $\Omega = (0,20)$, and $T = 1$. For network training, we employ the following specifications: $Iteration = 80000$, $depth = 4$, and $width = 50$. The dataset is configured as $Data = \\{N_r = 500, N_b = 200\\}$, where $N_r$ represents the internal points and $N_b$ denotes the boundary points. Additionally, the learning rate and learning rate decay rate are set to $lr = 0.001$ and $\gamma = 0.95$, respectively.


At the algorithmic level, LPS optimizes the residual of the determining equation associated with Lie symmetry, while our focus is on the further consequences of Lie symmetry, particularly on the residual of the conservation equations corresponding to Lie symmetry. From the experimental (with $G_2$ operator) provided above, it can be observed that LSN outperforms LPS.

>**Q2:**  The proposed LSN is only applicable to the Black-Scholes equation, which is a parabolic PDE. It should be noted that the derived Lie symmetry regularizer is based on the known Lie symmetry operators specific to the Black-Scholes equation. 

**A2:** Thanks again for this interesting question! We fully agree. We have extended the LSN algorithm to the Vasicek model while also conducting experiments involving various operator combinations, as shown in the following experiments. 

#### Extension to Vasicek Model

Various combinations of different Lie symmetry operators $G$ have been performed. The Lie symmetry operators used in the first two experiments are  $G_3+G_6$.

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/Figure_4.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/Figure_5.png width=400 height=300 />

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />


This experiment validates two aspects:

1. The algorithm's generalization capability. We have successfully extended LSN to the Vasicek equation, as evidenced by the first two figures, where LSN demonstrates a 4.4-fold improvement in accuracy compared to the baseline.

2. The algorithm's scalability. We conduct experiments with various single Lie symmetry operators and their linear combinations. The results show that single operators alone can achieve high accuracy, while combined operators can even outperform them.


>**Q7:** Possible generalizations?

**A7:** Please kindly see response A2.

