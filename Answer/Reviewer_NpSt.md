>**Q5.2:** The authors use a lot of doubtful 'without loss of generality'.

**A5.2:** Thanks and address. We have extended the application of our method to the Vasicek model while also conducting experiments involving various operator combinations, as shown in the following experiments,


#### Extension to Vasicek Model

Various combinations of different Lie symmetry operators $G$ have been performed. The Lie symmetry operators used in the first two experiments are  $G_3+G_6$.

<img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/Vasicek/Figure_4.png width=400 height=300 /><img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/Vasicek/Figure_5.png width=400 height=300 />

<img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/Vasicek/nG_Figure_6.png width=400 height=300 /><img src=https://github.com/Jxl163/ICML-2024-LSN/blob/main/Figure/Vasicek/nG_Figure_10.png width=400 height=300 />


This experiment validates two aspects:

1. The algorithm's generalization capability. We have successfully extended LSN to the Vasicek equation, as evidenced by the first two figures, where LSN demonstrates a 4.4-fold improvement in accuracy compared to the baseline.

2. The algorithm's scalability. We conduct experiments with various single Lie symmetry operators and their linear combinations. The results show that single operators alone can achieve high accuracy, while combined operators can even outperform them.


