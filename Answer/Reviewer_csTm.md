>**Q1:** The idea of incorporating domain knowledge into neural networks, while innovative in its application to Lie symmetries, is not entirely new within the broader context of physics-informed neural networks. The following work: Akhound-Sadegh et al. 2023 (Lie Point Symmetry an Physics Informed Neural Networks; ICML 2023 Workshop TAGML) also contributes to the idea of including Lie point symmetry into physics-informed neural networks but was not mentioned in the present work.

**A1:** Thanks and addressed. We have duly cited the paper, added a detailed discussion, and conducted comparison experiments as follows:

#### Performance Comparison between Our LSN and LPS by Akhound-Sadegh et al. (2023)


<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_1.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/LSN_LPS/Figure_2.png width=400 height=300 />

In the experiment, the parameters of the Black-Sholes equation are set as follows: $\sigma = 0.05$, $r = 0.1$, $\Omega = (0,20)$, and $T = 1$. The dataset comprises $500$ internal points and $200$ boundary points. The neural network architecture is designed with a depth of $9$ layers and a width of $50$ neurons. The training iteration is $30,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.

>**Q2:** Relies solely on simulation data for validation, raising questions about the model's performance in real-world financial market scenarios.

**A2:** Thanks. Following your suggestion, we conduct experiments on real data.

#### Experiments with Real-World Financial Data

The experiment is on the call option with contract ‘MEAT240328C00410000’ for the Meta Platforms, Inc. (META) listed on the Nasdaq. We used the data for a period of one year from 22nd March 2023 to 21st March 2024. The volatility is 100.08%, the strike price is 410, and the risk-free rate is 4.202%. An easy access to the data for interested reader is perhaps Yahoo! Finance: https://finance.yahoo.com/quote/META/options/.
The relative error of PINN and LSN are shown below:

<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/realistic%20simulation/META_AI.png width=400 height=300 />


>**Q3:**I do not understand why "focusing on the Lie symmetry operator G2 in the Black-Scholes equation" is counted as"without loss of generality". My understanding is that, given the Lie symmetry operators listed Line 138 -- 148, it should be the same number of Empirical Lie symmetry risk (Eq. 8) functions, and including/excluding any will have a real influence on the trained model.

**A3:** Thanks again for this interesting question! We fully agree. Other choices also work, and a combination has better performance. In this context, we conducted experiments involving various operator combinations, as shown in the following experiments:

#### Extension to Vasicek Model

The results of additional experiments on other operator combinations are shown below. 



<img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Anonymous3244/LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />

The experiments demonstrate that LSN with various combinations of symmetry operators consistently outperform PINN.



