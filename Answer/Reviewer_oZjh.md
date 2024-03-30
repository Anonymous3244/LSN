>**Q1:**  There does not seem to be anything structural about an architecture that guarantees the Lie symmetry during training. In that sense, the method is similar to PINNs in that an additional loss term is imposed to regularize the network but nothing in particular about the architecture guarantees the Lie symmetry is imposed.

**A1:** We fully agree that our method focuses on how to regularise the loss function to realise the Lie symmetry. 

We also sincerely note that our contribution is a universal, out-of-shelf solution, which is not limited with PINNs. We will add a new experiment with transformer as the backbone. 

#### Experiments on Transformer Model

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/lambda_j.png width=540 height=95 />

We employ a transformer model as the backbone to validate the performance of LSN across four hyperparameter setups: $\lambda_1 = 0.01$, $\lambda_2 = 1$, $\lambda_3 = 0.1$, and LSN with $\lambda_4 = 0.05$. 

The parameters of the Black-Scholes equation are set as follows: $\sigma = 0.5$, $r = 0.1$, $\Omega = (0,20)$, and $T = 1$. The dataset comprises $500$ internal points and $200$ boundary points.
The neural network architecture is designed with a depth of $4$ layers and a width of $50$ neurons.  The training iteration is $80,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.



<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/rel.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/mse.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/con.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/transformer/eq.png width=400 height=300 />

According to the experiments, LSN outperforms transformer across four  setups.

We sincerely note that our contribution is a universal, out-of-shelf solution, which is not limited with PINNs.

>**Q2:** The experimental results focus on the Black-Scholes equation, but it would be interesting to see studies for other choices of $\mu(x)\sigma(x)$ since the Lie group is stated to be general for these functions.

**A2:**Thanks and address. We have extended the application of our method to the Vasicek model with various operator combinations, as shown in the following experiments:

#### Extension to Vasicek Model



<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />

The experiments demonstrate that LSN is also applicable to Vasicek model.



