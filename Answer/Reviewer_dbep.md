>**Q1:** The following work: Akhound-Sadegh et al. 2023 (Lie Point Symmetry an Physics Informed Neural Networks; ICML 2023 Workshop TAGML) also contributes to the idea of including Lie point symmetry into physics-informed neural networks but was not mentioned in the present work.

**A1:**  Thanks and addressed. We conducted a comparison experiment, which shows that our method has significant advantages in performance: Under the same experimental setup, experiment for the relative errors and the conservation errors of the LPS and LSN on the Testing Datat after 30,000 training steps are provided. 

####  Performance Comparison between Our LSN and LPS by Akhound-Sadegh et al. (2023)

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_11.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_22.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_33.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_44.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_55.png width=400 height=300 />


In the experiment, the parameters of the Black-Scholes equation are set as follows:   $\Omega = (0,20)$, and $T = 1$. The dataset comprises $500$ internal points and $200$ boundary points. The neural network architecture is designed with a depth of $9$ layers and a width of $50$ neurons. The Lie symmtery operator is $G_2$. The training iteration is $80,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.


We respectfully note that our paper is the first work to realise the Lie symmetry by maintaining the corresponding conservation laws. This is in contrast with the approach of Akhound-Sadegh et al. (2023), which proposes to minimise the residual of the determining equation—criteria for the equation's symmetry. Compared with Akhound-Sadegh et al. (2023), our approach directly preserves the conservation laws, which are fundamental principles inherent to the physical system described by the differential equation.

>**Q6:**  Without loss of generality, the authors focus on the Lie symmetry operator $G_2$ in the Black-Scholes equation. What does that mean? Would it make no difference to include Lie symmetry operators other than $G_2$, or could we equip the LSN with even more complementary mechanisms that increase the neural network's awareness of symmetry?

**A6:** Thanks again for this interesting question! We fully agree. Other choices also work, and a combination has better performance. In this context, we  conducted experiments involving various operator combinations, as shown in the following experiments:

#### Extension to Vasicek Model




<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />


The experiments demonstrate that LSN with various combinations of symmetry operators consistently outperform PINN.


