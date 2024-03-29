# LSN

The repository contains the source code and additional experimental results of our LSN paper.

### 1. Performance Comparison between Our LSN and LPS by Akhound-Sadegh et al. (2023)

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_1.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_1.png width=400 height=300 />

The equation parameters are set as follows: $\sigma = 0.4$, $r = 0.11$, $\Omega = (0,20)$, and $T = 1$. For network training, we employ the following specifications: $Iteration = 80000$, $depth = 4$, and $width = 50$. The dataset is configured as $Data = \\{N_r = 500, N_b = 200\\}$, where $N_r$ represents the internal points and $N_b$ denotes the boundary points. Additionally, the learning rate and learning rate decay rate are set to $lr = 0.001$ and $\gamma = 0.95$, respectively.


At the algorithmic level, LPS optimizes the residual of the determining equation associated with Lie symmetry, while our focus is on the further consequences of Lie symmetry, particularly on the residual of the conservation equations corresponding to Lie symmetry. From the experimental (with $G_2$ operator) provided above, it can be observed that LSN outperforms LPS.


### 2. Extension to Vasicek Model

Various combinations of different Lie symmetry operators $G$ have been performed. The Lie symmetry operators used in the first two experiments are  $G_3+G_6$.

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/Figure_4.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/Figure_5.png width=400 height=300 />

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />


This experiment validates two aspects:

1. The algorithm's generalization capability. We have successfully extended LSN to the Vasicek equation, as evidenced by the first two figures, where LSN demonstrates a 4.4-fold improvement in accuracy compared to the baseline.

2. The algorithm's scalability. We conduct experiments with various single Lie symmetry operators and their linear combinations. The results show that single operators alone can achieve high accuracy, while combined operators can even outperform them.








### 3. Experiments with Real-World Financial Data

The experiment is on the call option with contract ‘MEAT240328C00410000’ for the Meta Platforms, Inc. (META) listed on the Nasdaq. We used the data for a period of one year from 22nd March 2023 to 21st March 2024. The volatility is 100.08%, the strike price is 410, and the risk-free rate is 4.202%. An easy access to the data for interested reader is perhaps Yahoo! Finance: https://finance.yahoo.com/quote/META/options/.
The results are as follows:

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/realistic%20simulation/META_AI.png width=400 height=300 />


### 4. Experiments on Transformer Model

Algorithm weights are set as follows: $\lambda_1 = 0.01$, $\lambda_2 = 1$, $\lambda_3 = 0.1$, and LSN with $\lambda_4 = 0.05$. Training steps and network architecture parameters are configured as $Epoch = 80000$, $depth = 4$, $width = 50$.  And the learning rate of the network, along with equation parameters, is set to $lr = 0.001$, with $\sigma = 0.5$ and $r = 0.1$. The dataset consists of $Data = \\{N_r = 500, N_b = 200\\}$, where $N_r$ represents internal points and $N_b$ denotes boundary points.



<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/rel.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/mse.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/con.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/eq.png width=400 height=300 />

We employ a transformer as the backbone and validate the performance of LSN across the aforementioned four evaluation metrics. According to the experiments, it is evident that LSN outperforms the baseline across four metrics.


