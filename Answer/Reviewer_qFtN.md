>**Q1:**  My main concern regarding this paper is mainly about originality. The authors' claim of their proposed method being "the first symmetry-aware AI-based method for solving SDEs" appears somewhat overstated due to the following reasons. 
And  utilizing the Lie point symmetry to regularize PINNs when solving parabolic PDEs is not entirely novel, as evidenced by a relevant work (not cited by the authors):[1]. The title of [1] explicitly suggests the introduction of a loss function that informs PINNs about how well their solutions adhere to Lie point symmetries when learning PDEs. [1] validates its proposed approach for the heat equation, which is closely related to the Black-Scholes equation. Therefore, I believe a comparison between the proposed LSN and [1] would be beneficial, along with a discussion of the pros and cons of the LSN in relation to existing approaches.

**A1:**  Thanks. We apologise that we overlooked this paper. We have duly cited the paper, added a detailed discussion, and conducted comparison experiments as follows.

#### Performance Comparison between Our LSN and LPS by Akhound-Sadegh et al. (2023)

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_1.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_2.png width=400 height=300 />

In the experiment, the parameters of the Black-Scholes equation are set as follows: $\sigma = 0.4$, $r = 0.11$, $\Omega = (0,20)$, and $T = 1$. The dataset comprises $500$ internal points and $200$ boundary points. The neural network architecture is designed with a depth of $4$ layers and a width of $50$ neurons. The training iteration is $100,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.

We respectfully note that our paper is the first work to realise the Lie symmetry by maintaining the corresponding conservation laws. This is in contrast with the approach of Akhound-Sadegh et al. (2023), which proposes to minimise the residual of the determining equation—criteria for the equation's symmetry. Compared with Akhound-Sadegh et al. (2023), our approach directly preserves the conservation laws, which are fundamental principles inherent to the physical system described by the differential equation.

>**Q2:**  The proposed LSN is only applicable to the Black-Scholes equation, which is a parabolic PDE. It should be noted that the derived Lie symmetry regularizer is based on the known Lie symmetry operators specific to the Black-Scholes equation. 

**A2:** Thanks again for this interesting question! We fully agree. We have extended the application of our method to the Vasicek model with various operator combinations, as shown in the following experiments:

#### Extension to Vasicek Model



<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />



The experiments demonstrate that LSN is also applicable to Vasicek model.
