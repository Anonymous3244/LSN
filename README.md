The repository contains the source code and additional experimental results of our LSN paper.



### 1. Performance Comparison between Our LSN and LPS by Akhound-Sadegh et al. (2023)

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_1.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_2.png width=400 height=300 />


In the experiment, the parameters of the Black-Sholes equation are set as follows: $\sigma = 0.05$, $r = 0.1$, $\Omega = (0,20)$, and $T = 1$. The dataset comprises $500$ internal points and $200$ boundary points. The neural network architecture is designed with a depth of $9$ layers and a width of $50$ neurons. The training iteration is $100,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.

We respectfully note that our paper is the first work to realise the Lie symmetry by maintaining the corresponding conservation laws. This is in contrast with the approach of Akhound-Sadegh et al. (2023), which proposes to minimise the residual of the determining equation—criteria for the equation's symmetry. Compared with Akhound-Sadegh et al. (2023), our approach directly preserves the conservation laws, which are fundamental principles inherent to the physical system described by the differential equation.

### 2. Extension to Vasicek Model

The results of additional experiments on other operator combinations are shown below. 



<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />

In the experiment, the parameters of the Vasicek Model are set as follows: $\alpha = 0.03$, $\beta = 0.08$, $\Gamma = -1$, $\sigma = 0.03$, $\Omega = 1$ and $T = 1$. The dataset comprises $500$ internal points and $200$ boundary points. The neural network architecture is designed with a depth of $2$ layers and a width of $10$ neurons. The training iteration is $100,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.

The experiments demonstrate that LSN with various combinations of symmetry operators consistently outperform PINN.


### 3. Experiments with Real-World Financial Data

The experiment is on the call option with contract ‘MEAT240328C00410000’ for the Meta Platforms, Inc. (META) listed on the Nasdaq. We used the data for a period of one year from 22nd March 2023 to 21st March 2024. The volatility is 100.08%, the strike price is 410, and the risk-free rate is 4.202%. An easy access to the data for interested reader is perhaps Yahoo! Finance: https://finance.yahoo.com/quote/META/options/.
The relative error of PINN and LSN are shown below:

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/realistic%20simulation/META_AI.png width=400 height=300 />


The experiments show that LSN outperform PINN with real-world financial data.

### 4. Experiments on Transformer Model

We employ a transformer model as the backbone to validate the performance of LSN across four hyperparameter setups: $\lambda_1 = 0.01$, $\lambda_2 = 1$, $\lambda_3 = 0.1$, and LSN with $\lambda_4 = 0.05$. 

The parameters of the Black-Sholes equation are set as follows: $\sigma = 0.5$, $r = 0.1$, $\Omega = (0,20)$, and $T = 1$. The dataset comprises $500$ internal points and $200$ boundary points.
The neural network architecture is designed with a depth of $4$ layers and a width of $50$ neurons.  The training iteration is $80,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.


<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/rel.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/mse.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/con.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/eq.png width=400 height=300 />


According to the experiments, LSN outperforms PINN across four  setups.

We sincerely note that our contribution is a universal, out-of-shelf solution, which is not limited with PINNs.
