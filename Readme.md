
# Restricted Boltzmann Machine (RBM)

A toy implementation of Restricted Boltzmann Machine (RBM) in PyTorch. Learning parameters of RBM <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/cc99dd1c3fafcb6dc9d0ce9ad866e70d.svg?raw=true?raw=true?invert_in_darkmode" align=middle width=77.34976424999998pt height=24.65753399999998pt/> are estimated using <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/63bb9849783d01d91403bc9a5fea12a2.svg?raw=true?invert_in_darkmode" align=middle width=9.075367949999992pt height=22.831056599999986pt/>-step Contrastive Divergence (CD-<img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/63bb9849783d01d91403bc9a5fea12a2.svg?raw=true?invert_in_darkmode" align=middle width=9.075367949999992pt height=22.831056599999986pt/>) algorithm according to the update rule:

<p align="center"><img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/93301a14c9c4a60ded4849330c86ebc5.svg?raw=true?invert_in_darkmode" align=middle width=330.54585134999996pt height=21.07942155pt/></p>

<p align="center"><img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/41c557a88943c67f54ace2fdc3ffcdf9.svg?raw=true?invert_in_darkmode" align=middle width=278.69063969999996pt height=19.9563243pt/></p>


<p align="center"><img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/7918a69f0637d71970faf6fadb2a6444.svg?raw=true?invert_in_darkmode" align=middle width=151.47997425pt height=21.07942155pt/></p>

where <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/ae4fb5973f393577570881fc24fc2054.svg?raw=true?invert_in_darkmode" align=middle width=10.82192594999999pt height=14.15524440000002pt/> is a matrix of the weights between visible and hidden units, <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/b2585b5c81c97deeac55c46eb718b023.svg?raw=true?invert_in_darkmode" align=middle width=14.793662399999992pt height=14.15524440000002pt/> (<img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/a4bd6a03f34c02be448007a65da5f451.svg?raw=true?invert_in_darkmode" align=middle width=11.705695649999988pt height=22.831056599999986pt/>) are biases for visible (hidden) units. The activation probabilities <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/c9ea84eb1460d2895e0cf5125bd7f7b5.svg?raw=true?invert_in_darkmode" align=middle width=30.450987599999987pt height=24.65753399999998pt/> of the visible <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/7f94fa77c3eb4def896a173bac4d35a9.svg?raw=true?invert_in_darkmode" align=middle width=41.42205044999999pt height=23.488575000000026pt/> and hidden <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/be368bacc9f66da3cf2911e079cf701c.svg?raw=true?invert_in_darkmode" align=middle width=40.96541459999999pt height=32.16441360000002pt/> units can be calculated as: 

<p align="center"><img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/9c3cd0a25a653816f0c55a2e742fb481.svg?raw=true?invert_in_darkmode" align=middle width=239.73630945pt height=49.315569599999996pt/></p>

and 

<p align="center"><img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/3be1a11585b4d12f82871188e6aa7aed.svg?raw=true?invert_in_darkmode" align=middle width=245.7806274pt height=59.1786591pt/></p>

where <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/b9b27f3deff0db82f962a8505706e620.svg?raw=true?invert_in_darkmode" align=middle width=32.16330314999999pt height=24.65753399999998pt/> is the sigmoid function. The training example is denoted as <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/9e7d7acc7ebd735a215bd4a16d9d4be8.svg?raw=true?invert_in_darkmode" align=middle width=15.748698899999999pt height=26.76175259999998pt/> and the sample after <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/63bb9849783d01d91403bc9a5fea12a2.svg?raw=true?invert_in_darkmode" align=middle width=9.075367949999992pt height=22.831056599999986pt/> Gibbs sampling steps as <img src="https://github.com/vladimirprotsenko/Restricted_Boltzmann_Machine_on_MNIST/blob/main/svgs/1033789f828f05084c57b20f19f09ac3.svg?raw=true?invert_in_darkmode" align=middle width=16.462182pt height=27.91243950000002pt/>. 

As an example, the RBM model is applied to generate digits from the MNIST dataset.

## References
1. [Fischer, Asja, and Christian Igel. An introduction to restricted Boltzmann machines.](https://link.springer.com/content/pdf/10.1007/978-3-642-33275-3_2.pdf)
2. [Hinton, Geoffrey E. A practical guide to training restricted Boltzmann machines.](https://www.csrc.ac.cn/upload/file/20170703/1499052743888438.pdf)
3. [Yue Li Review of Boltzmann machines and simulated annealing.](http://www.cs.utoronto.ca/~yueli/CSC321_UTM_2014_files/tut9.pdf)

