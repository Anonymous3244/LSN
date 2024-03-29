>**Q1:** The following work: Akhound-Sadegh et al. 2023 (Lie Point Symmetry an Physics Informed Neural Networks; ICML 2023 Workshop TAGML) also contributes to the idea of including Lie point symmetry into physics-informed neural networks but was not mentioned in the present work.

**A1:**  Thanks and addressed. We conducted a comparison experiment, which shows that our method has significant advantages in performance: Under the same experimental setup, experiment for the relative errors and the conservation errors of the LPS and LSN on the Testing Datat after 30,000 training steps are provided. 

####  Performance Comparison between Our LSN and LPS by Akhound-Sadegh et al. (2023)

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_1.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_2.png width=400 height=300 />

The equation parameters are set as follows: $\sigma = 0.4$, $r = 0.11$, $\Omega = (0,20)$, and $T = 1$. For network training, we employ the following specifications: $Iteration = 80000$, $depth = 4$, and $width = 50$. The dataset is configured as $Data = \\{N_r = 500, N_b = 200\\}$, where $N_r$ represents the internal points and $N_b$ denotes the boundary points. Additionally, the learning rate and learning rate decay rate are set to $lr = 0.001$ and $\gamma = 0.95$, respectively.


At the algorithmic level, LPS optimizes the residual of the determining equation associated with Lie symmetry, while our focus is on the further consequences of Lie symmetry, particularly on the residual of the conservation equations corresponding to Lie symmetry. From the experimental (with $G_2$ operator) provided above, it can be observed that LSN outperforms LPS.



>**Q6:**  Without loss of generality, the authors focus on the Lie symmetry operator $G_2$ in the Black-Scholes equation. What does that mean? Would it make no difference to include Lie symmetry operators other than $G_2$, or could we equip the LSN with even more complementary mechanisms that increase the neural network's awareness of symmetry?

**A6:** Thanks again for this interesting question! We fully agree. Other choices also work, and a combination has better performance. In this context, our work extends the algorithm to the Vasicek model while also conducting experiments involving various operator combinations, as shown in the following experiments,

#### Extension to Vasicek Model

Various combinations of different Lie symmetry operators $G$ have been performed. The Lie symmetry operators used in the first two experiments are  $G_3+G_6$.

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/Figure_4.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/Figure_5.png width=400 height=300 />

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />


This experiment validates two aspects:

1. The algorithm's generalization capability. We have successfully extended LSN to the Vasicek equation, as evidenced by the first two figures, where LSN demonstrates a 4.4-fold improvement in accuracy compared to the baseline.

2. The algorithm's scalability. We conduct experiments with various single Lie symmetry operators and their linear combinations. The results show that single operators alone can achieve high accuracy, while combined operators can even outperform them.



