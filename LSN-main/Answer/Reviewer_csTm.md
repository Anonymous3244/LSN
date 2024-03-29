>**Q1:** The idea of incorporating domain knowledge into neural networks, while innovative in its application to Lie symmetries, is not entirely new within the broader context of physics-informed neural networks. The following work: Akhound-Sadegh et al. 2023 (Lie Point Symmetry an Physics Informed Neural Networks; ICML 2023 Workshop TAGML) also contributes to the idea of including Lie point symmetry into physics-informed neural networks but was not mentioned in the present work.

**A1:** Thanks and addressed. We have duly cited the paper, added a detailed discussion, and conducted comparison experiments as follows:

#### Performance Comparison between Our LSN and LPS by Akhound-Sadegh et al. (2023)

<img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/LSN_LPS/Figure_1.png width=400 height=300 /><img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/LSN_LPS/Figure_2.png width=400 height=300 />

The equation parameters are set as follows: $\sigma = 0.4$, $r = 0.11$, $\Omega = (0,20)$, and $T = 1$. For network training, we employ the following specifications: $Iteration = 80000$, $depth = 4$, and $width = 50$. The dataset is configured as $Data = \\{N_r = 500, N_b = 200\\}$, where $N_r$ represents the internal points and $N_b$ denotes the boundary points. Additionally, the learning rate and learning rate decay rate are set to $lr = 0.001$ and $\gamma = 0.95$, respectively.


At the algorithmic level, LPS optimizes the residual of the determining equation associated with Lie symmetry, while our focus is on the further consequences of Lie symmetry, particularly on the residual of the conservation equations corresponding to Lie symmetry. From the experimental (with $G_2$ operator) provided above, it can be observed that LSN outperforms LPS.

>**Q2:** Relies solely on simulation data for validation, raising questions about the model's performance in real-world financial market scenarios.

**A2:** Thanks. Following your suggestion, we conduct experiments on real data.

#### Experiments with Real-World Financial Data

Taking the option 'MEAT240328C00410000' from META AI company as an example, the stock prices (Adj Close**) for a period of one year from March 23, 2023, to March 22, 2024, were extracted from the Yahoo website. The volatility was 100.08%, the strike price was 410, and the risk-free rate was 4.202 for the experiment. After normalization, the relative error between the numerical solution obtained from the neural network and the true solution (BS numerical solution) is as follows:

<img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/realistic%20simulation/META_AI.png width=400 height=300 />

>**Q3:**I do not understand why "focusing on the Lie symmetry operator G2 in the Black-Scholes equation" is counted as"without loss of generality". My understanding is that, given the Lie symmetry operators listed Line 138 -- 148, it should be the same number of Empirical Lie symmetry risk (Eq. 8) functions, and including/excluding any will have a real influence on the trained model.

**A3:** Thanks again for this interesting question! We fully agree. Other choices also work, and a combination has better performance. In this context, our work extends the algorithm to the Vasicek model while also conducting experiments involving various operator combinations, as shown in the following experiments,


#### Extension to Vasicek Model

Various combinations of different Lie symmetry operators $G$ have been performed. The Lie symmetry operators used in the first two experiments are  $G_3+G_6$.

<img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/Vasicek/Figure_4.png width=400 height=300 /><img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/Vasicek/Figure_5.png width=400 height=300 />

<img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />


This experiment validates two aspects:

1. The algorithm's generalization capability. We have successfully extended LSN to the Vasicek equation, as evidenced by the first two figures, where LSN demonstrates a 4.4-fold improvement in accuracy compared to the baseline.

2. The algorithm's scalability. We conduct experiments with various single Lie symmetry operators and their linear combinations. The results show that single operators alone can achieve high accuracy, while combined operators can even outperform them.




