>**Q1:**  There does not seem to be anything structural about an architecture that guarantees the Lie symmetry during training. In that sense, the method is similar to PINNs in that an additional loss term is imposed to regularize the network but nothing in particular about the architecture guarantees the Lie symmetry is imposed.

**A1:** We fully agree that our method focuses on how to regularise the loss function to realise the Lie symmetry. 

We also sincerely note that our contribution is a universal, out-of-shelf solution, which is not limited with PINNs. We will add a new experiment with transformer as the backbone. 

#### Experiments on Transformer Model

Algorithm weights are set as follows: $\lambda_1 = 0.01$, $\lambda_2 = 1$, $\lambda_3 = 0.1$, and LSN with $\lambda_4 = 0.05$. Training steps and network architecture parameters are configured as $Epoch = 80000$, $depth = 4$, $width = 50$.  And the learning rate of the network, along with equation parameters, is set to $lr = 0.001$, with $\sigma = 0.5$ and $r = 0.1$. The dataset consists of $Data = \\{N_r = 500, N_b = 200\\}$, where $N_r$ represents internal points and $N_b$ denotes boundary points.



<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/rel.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/mse.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/con.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/eq.png width=400 height=300 />

We employ a transformer as the backbone and validate the performance of LSN across the aforementioned four evaluation metrics. According to the experiments, it is evident that LSN outperforms the baseline across four metrics.

>**Q2:** The experimental results focus on the Black-Scholes equation, but it would be interesting to see studies for other choices of $\mu(x)\sigma(x)$ since the Lie group is stated to be general for these functions。

**A2:**Thanks and address. We have extended the application of our method to the Vasicek model while also conducting experiments involving various operator combinations, as shown in the following experiments,


#### Extension to Vasicek Model

Various combinations of different Lie symmetry operators $G$ have been performed. The Lie symmetry operators used in the first two experiments are  $G_3+G_6$.

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/Figure_4.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/Figure_5.png width=400 height=300 />

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />


This experiment validates two aspects:

1. The algorithm's generalization capability. We have successfully extended LSN to the Vasicek equation, as evidenced by the first two figures, where LSN demonstrates a 4.4-fold improvement in accuracy compared to the baseline.

2. The algorithm's scalability. We conduct experiments with various single Lie symmetry operators and their linear combinations. The results show that single operators alone can achieve high accuracy, while combined operators can even outperform them.

>**Q3:**  The empirical study is a bit weak since it only compares to PINNs and only considers the Black-Scholes equation under a vanilla payoff. The appendix also contains an example of a PDE with given by an OU-type process. Additionally all the examples are 1 spatial dimension and in this case a comparable finite difference method would probably be faster/more accurate.

**A3:** Thanks and address. We sincerely note that our contribution is a universal, out-of-shelf solution, which is not limited with PINNs. We will add a new experiment with transformer as the backbone.   Please kindly see response A1 (non-PINN).




