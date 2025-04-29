# csc4005---project-4-parallel-programming-with-machine-learning-solved
**TO GET THIS SOLUTION VISIT:** [CSC4005 – Project 4: Parallel Programming with Machine Learning Solved](https://www.ankitcodinghub.com/product/csc4005-project-4-parallel-programming-with-machine-learning-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;115819&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSC4005 - Project 4: Parallel Programming with Machine Learning Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
This project weights 12.5% for your final grade (4 Projects for 50%)

Mr. Xue Haonan for Implementation (haonanxue@link.cuhk.edu.cn)

Mr. Zhong Yebin for Implementation (yebinzhong@link.cuhk.edu.cn)

Mr. Chen Weibin for Writing Grading criteria (220019062@link.cuhk.edu.cn)

Prologue

In this project, you will have the opportunity to gain insight and practice in using OpenACC to accelerate machine learning algorithms. Specifically, you will be accelerating softmax regression and neural networks (NNs).

First, you will need to understand the basic principles and algorithms of softmax regression and neural networks. Then, you will work with OpenACC, a programming model for parallel computing that makes it easier for you to optimize your code to run on GPUs, thereby greatly increasing the speed of computation.

This assignment will help you understand the importance of parallel computing in machine learning, especially when working with large-scale data and complex models. You will learn how to effectively utilize hardware resources to improve the performance and efficiency of machine learning algorithms.

REMIND: Please start ASAP to avoid the peak period of cluster job submission.

Task0: Setup

Download the dataset from BB. Unzip dataset.zip to folder project4.

The structure of working directory should look like below:

“` $ tree . . â”œâ”€â”€ build â”‚ â”œâ”€â”€ nn â”‚ â”œâ”€â”€ nn_openacc â”‚ â”œâ”€â”€ softmax â”‚ â””â”€â”€ softmax_openacc â”œâ”€â”€ dataset â”‚ â”œâ”€â”€ testing â”‚ â”‚ â”œâ”€â”€ t10k-images.idx3-ubyte â”‚ â”‚ â””â”€â”€ t10k-labels.idx1-ubyte â”‚ â””â”€â”€ training â”‚ â”œâ”€â”€ train-images.idx3-ubyte â”‚ â””â”€â”€ train-labels.idx1-ubyte â”œâ”€â”€ README.md â”œâ”€â”€ sbatch.sh â”œâ”€â”€ src â”‚ â”œâ”€â”€ nn_classifier.cpp â”‚ â”œâ”€â”€ nn_classifier_openacc.cpp â”‚ â”œâ”€â”€ simple_ml_ext.cpp â”‚ â”œâ”€â”€ simple_ml_ext.hpp â”‚ â”œâ”€â”€ simple_ml_openacc.cpp â”‚ â”œâ”€â”€ simple_ml_openacc.hpp â”‚ â”œâ”€â”€ softmax_classifier.cpp â”‚ â””â”€â”€ softmax_classifier_openacc.cpp â””â”€â”€ test.sh

5 directories, 20 files “`

Task1: Train MNIST with softmax regression

Softmax regression (or multinomial logistic regression) is an extension of logistic regression that can handle multiclass classification problems. Softmax Regression, also known as Multinomial Logistic Regression, is an extension of Logistic Regression to the multi-class problem. The mathematical expression is as follows:

Suppose we have an input vector $x in R^n$, and we want to classify it into one of $K$ different classes.

For each class $j$, we have a weight vector $ heta_j in R^n$.

We can compute the unnormalized log probabilities $z_j$ for $x$ belonging to class $j$ as follows:

$$ z_j = x^T heta_j$$

This gives us an output vector $ heta in R^K$, where each element $z_j$ represents the unnormalized log probability of $x$ belonging to class $j$.

We can then convert these unnormalized log probabilities into probabilities using the softmax function. The softmax function is defined as follows:

$$ p(y=j|x) = rac{e^{z_j}}{Sigma_{k=1}^{K} e^{z_k}} $$

This gives us a probability vector $p in R^K$, where each element $p_j$ represents the probability of $x$ belonging to class $j$. This is the mathematical expression of softmax regression. It maps an input vector $x$ to a probability vector $p$, where each element $p_j$ represents the probability of $x$ belonging to class $j$.

This process is also known as softmax classification. In practice, we usually choose the class with the highest probability as the predicted class.

For a multi-class output that can take on values $y in {1,ldots,k}$, the softmax loss takes as input a vector of logits $z in mathbb{R}^k$, the true class $y in {1,ldots,k}$ returns a loss defined by:

$$ ell_{mathrm{softmax}}(z, y) = logsum_{i=1}^k exp z_i – z_y $$

Softmax gradient descent optimization algorithm: we need to compute the gradients of the loss function with respect to the weights and biases, and then update the weights and biases. We can also write this in the more compact notation we discussed in class. Namely, if we let $X in mathbb{R}^{m imes n}$ denote a design matrix of some $m$ inputs (either the entire dataset or a minibatch), $y in {1,ldots,k}^m$ a corresponding vector of labels, and overloading $ell_{mathrm{softmax}}$ to refer to the average softmax loss, then

$$ abla_Theta ell_{mathrm{softmax}}(X Theta, y) = rac{1}{m} X^T (Z – I_y) $$

$$ heta’ = heta – alpha abla_Theta ell_{mathrm{softmax}}(X Theta, y) $$ where

$$ Z = normalize(exp(X Theta)) quad mbox{(normalization applied row-wise)} $$

denotes the matrix of logits, $I_y in mathbb{R}^{m imes k}$ represents a concatenation of one-hot bases for the labels in $y$, and $alpha$ is the learning rate.

Here is the sample training code in Python:

python def softmax_regression_epoch(X, y, theta, lr=0.1, batch=100): for i in range(0, X.shape[0], batch): X_b = X[i : i + batch] h_X_exp = np.exp(np.dot(X_b, theta)) Z = h_X_exp / np.sum(h_X_exp, axis=1)[:, None] Y = np.zeros(Z.shape, np.float32) Y[np.arange(y[i : i + batch].size), y[i : i + batch]] = 1 gradients = np.dot(X_b.T, Z – Y) / batch * lr theta -= gradients

Note that for “real” implementation of softmax loss you would want to scale the logits to prevent numerical overflow, but we won’t worry about that here (the rest of the assignment will work fine even if you don’t worry about this).

There are some functions inside the softmax function that you also need to fill in the details:

| Function Declaration | What does the function do | | ———————————————————— | ———————————————————– | | matrix_dot(A, B, C, m, n, k) | perform a matrix multiplication operation between matrices $A$ and $B$, and the result is stored in matrix $C$ | | matrix_softmax_normalize(A, m, n) | apply the softmax activation function to the matrix $A$ | | vector_to_one_hot_matrix(y, Y, m, n) | convert a vector $y$ into a one-hot encoded matrix $Y$ with dimensions $m imes n$ | | matrix_minus(A, B, m, n) | perform element-wise subtraction between matrices A and B, with the result stored in matrix A | | matrix_dot_trans(A, B, C, n, m, k) | perform a matrix multiplication between the transpose of $A$ and $B$, with the result stored in matrix $C$ | | matrix_div_scalar(A, scalar, m, n) | divides all elements of matrix $A$ by the scalar value $scalar$ | | matrix_mul_scalar(A, scalar, m, n) | multiply all elements of matrix $A$ by the scalar value $scalar$ | | matrix_minus(A, B, m, n) | subtracts matrix $A$ from matrix $B$ element-wise, , with the result stored in matrix $A$ | | softmax_regression_epoch_cpp(X, y, theta, m, n, k, lr, batch) | train $ heta$ of softmax regression for 1 epoch | | train_softmax(train_data, test_data, num_classes, epochs, lr, batch) | train a softmax classifier |

In the implementation, you are allowed to define your variables and functions to facilitate your programming.

The outcome is like below:

| Epoch | Train Loss | Train Err | Test Loss | Test Err | | 0 | 0.35134 | 0.10182 | 0.33588 | 0.09400 | | 1 |

0.32142 | 0.09268 | 0.31086 | 0.08730 | | 2 | 0.30802 | 0.08795 | 0.30097 | 0.08550 | | 3 | 0.29987 | 0.08532

| 0.29558 | 0.08370 | | 4 | 0.29415 | 0.08323 | 0.29215 | 0.08230 | | 5 | 0.28981 | 0.08182 | 0.28973 |

0.08090 | | 6 | 0.28633 | 0.08085 | 0.28793 | 0.08080 | | 7 | 0.28345 | 0.07997 | 0.28651 | 0.08040 | | 8 |

0.28100 | 0.07923 | 0.28537 | 0.08010 | | 9 | 0.27887 | 0.07847 | 0.28442 | 0.07970 |

Task2: Accelerate softmax with OpenACC

You need to accelerate the train_softmax function and the functions inside the softmax_regression_epoch_cpp function with OpenACC. Hint: You can accelerate the program by applying OpenACC to each function.

Task3: Train MNIST with neural network

The inference and training process of a neural network can be described by the following formulas:

1. Forward Propagation (Inference) The forward propagation process of a neural network can be described by the following formula, where $a^{(l)}$ is the activation value of the $l$ th layer $W^{(l)}$ is the weight of the $l$ th layer, $b^{(l)}$ is the bias of the $l$ th layer, and $f$ is the activation function:

$$a^{(l)}=f(W^{(l)} a^{(lâˆ’1)}+b^{(l)})$$

This process starts from the input layer, through the calculation of each layerâ€™s weights and biases, as well as the activation function, and finally obtains the predicted value of the output layer.

2. Backward Propagation (Training) The training process of a neural network mainly updates the weights and biases through the backpropagation algorithm. First, we need to define a loss function $L$ to measure the gap between the predicted value and the true value. Then, we update the weights and biases by calculating the gradient of the loss function for the weights and biases:

$$ rac{partial{L}}{partial{W^{(l)}}} = rac{partial{L}}{partial{a^{(l)}}} rac{partial{a^{(l)}}}{partial{W^{(l)}}} $$

$$rac{partial{L}}{partial{b^{(l)}}} = rac{partial{L}}{partial{a^{(l)}}} rac{partial{a^{(l)}}}{partial{b^{(l)}}} $$

Here, $rac{partial{L}}{partial{a^{(l)}}}$ can be propagated from the next layer to the previous layer through the chain rule. Finally, we use the gradient descent method to update the weights and biases:

$$ W^{(l)} = W^{(l)} – alpha rac{partial{L}}{partial{W^{(l)}}} $$

$$ b^{(l)} = b^{(l)} – alpha rac{partial{L}}{partial{b^{(l)}}} $$

Here, $alpha$ is the learning rate, which controls the step size of the update.

In this project, we are going to implement a 2-layer NN without bias by using the SGD method. The target function is below:

$$ Z = W_2^T ReLU(W_1^T x) $$

where $W_1 in mathbb{R}^{n imes d}$ and $W_2 in mathbb{R}^{d imes k}$ represent the weights of the network (which has a $d$dimensional hidden unit), and where $z in mathbb{R}^k$ represents the logits output by the network. The formula of ReLU activation function is $f(x) = max(0,x)$. We again use the softmax / cross-entropy loss, meaning that we want to solve the optimization problem.

Using the chain rule, we can derive the backpropagation updates for this network (we’ll briefly cover these in class, on 9/8, but also provide the final form here for ease of implementation). Specifically, let

$$ Z_1 in mathbb{R}^{m imes d} = mathrm{ReLU}(X W_1) $$

$$ G_2 in mathbb{R}^{m imes k} = normalize(exp(Z_1 W_2)) – I_y $$

$$ G_1 in mathbb{R}^{m imes d} = mathrm{1}{Z_1 &gt; 0} circ (G_2 W_2^T) $$

where $mathrm{1}{Z_1 &gt; 0}$ is a binary matrix with entries equal to zero or one depending on whether each term in $Z_1$ is strictly positive and where $circ$ denotes elementwise multiplication. Then the gradients of the objective are given by:

$$ abla_{W_1} ell_{mathrm{softmax}}(mathrm{ReLU}(X W_1) W_2, y) = rac{1}{m} X^T G_1 $$ $$ abla_{W_2} ell_{mathrm{softmax}}(mathrm{ReLU}(X W_1) W_2, y) = rac{1}{m} Z_1^T G_2 $$

Here is the sample training code in Python:

python def nn_epoch(X, y, W1, W2, lr=0.1, batch=100): for i in range(0, X.shape[0], batch): X_b = X[i : i + batch] Z1 = np.maximum(0, np.dot(X_b, W1)) h_Z1_exp = np.exp(np.dot(Z1, W2)) Z2 = h_Z1_exp / np.sum(h_Z1_exp, axis=1)[:, None] Y = np.zeros(Z2.shape, np.float32) Y[np.arange(y[i : i + batch].size), y[i : i + batch]] = 1 G1 = np.dot(Z2 – Y, W2.T) * (Z1 &gt; 0) W1_l = np.dot(X_b.T, G1) / batch * lr W2_l = np.dot(Z1.T, Z2 – Y) / batch * lr W1 -= W1_l W2 -= W2_l

There are some new functions inside the NN function that you also need to fill in the details:

| Function Declaration | What does the function do | | ———————————————————— | ——————————-

—————————– | | matrix_trans_dot(A, B, C, m, n, k) | perform a matrix multiplication between $A$ and the transpose of $B$, with the result stored in matrix $C$ | | matrix_mul(A, B, size) | multiply matrix $A$ from matrix $B$ element-wise, with the result

stored in matrix $A$ | | nn_epoch_cpp(X, y, W1, W2, m, n, l, k, lr, batch) | train the 2-layer NN for 1 epoch | | train_nn(train_data, test_data, num_classes, hidden_dim, epochs, lr, batch) | train a 2-layer NN classifier | The outcome is like below:

| Epoch | Train Loss | Train Err | Test Loss | Test Err | | 0 | 0.13466 | 0.04023 | 0.14293 | 0.04240 | | 1 |

0.09653 | 0.03020 | 0.11593 | 0.03700 | | 2 | 0.07351 | 0.02227 | 0.10043 | 0.03170 | | 3 | 0.05862 | 0.01715

| 0.09091 | 0.02880 | | 4 | 0.04677 | 0.01298 | 0.08348 | 0.02650 | | 5 | 0.03878 | 0.01015 | 0.07878 |

0.02490 | | 6 | 0.03281 | 0.00822 | 0.07595 | 0.02470 | | 7 | 0.02796 | 0.00672 | 0.07341 | 0.02390 | | 8 |

0.02452 | 0.00558 | 0.07204 | 0.02280 | | 9 | 0.02133 | 0.00453 | 0.07076 | 0.02240 | | 10 | 0.01880 | 0.00365

| 0.07004 | 0.02200 | | 11 | 0.01675 | 0.00320 | 0.06925 | 0.02190 | | 12 | 0.01510 | 0.00265 | 0.06867 |

0.02190 | | 13 | 0.01345 | 0.00203 | 0.06821 | 0.02150 | | 14 | 0.01217 | 0.00150 | 0.06793 | 0.02080 | | 15 |

0.01136 | 0.00128 | 0.06787 | 0.02100 | | 16 | 0.01010 | 0.00098 | 0.06725 | 0.02060 | | 17 | 0.00949 |

0.00090 | 0.06736 | 0.02050 | | 18 | 0.00860 | 0.00068 | 0.06690 | 0.02020 | | 19 | 0.00793 | 0.00050 | 0.06666 | 0.02030 |

Task4: Accelerate neural network with OpenACC

You need to accelerate the train_nn function and the functions inside the nn_epoch_cpp function with OpenACC.

Since the calculating precisions on CPU and GPU platforms are different, there is a tiny gap between the outcome of sequential and OpenACC programs. Here is the sample output of OpenACC:

| Epoch | Train Loss | Train Err | Test Loss | Test Err | | 0 | 0.13466 | 0.04023 | 0.14293 | 0.04240 | | 1 |

0.09699 | 0.03037 | 0.11628 | 0.03700 | | 2 | 0.07349 | 0.02233 | 0.10028 | 0.03230 | | 3 | 0.05790 | 0.01675

| 0.09053 | 0.02800 | | 4 | 0.04668 | 0.01280 | 0.08374 | 0.02650 | | 5 | 0.03846 | 0.01003 | 0.07861 |

0.02520 | | 6 | 0.03255 | 0.00810 | 0.07542 | 0.02420 | | 7 | 0.02800 | 0.00678 | 0.07333 | 0.02410 | | 8 |

0.02444 | 0.00548 | 0.07163 | 0.02350 | | 9 | 0.02127 | 0.00447 | 0.07054 | 0.02290 | | 10 | 0.01869 | 0.00365

| 0.06941 | 0.02230 | | 11 | 0.01683 | 0.00318 | 0.06875 | 0.02200 | | 12 | 0.01501 | 0.00252 | 0.06818 |

0.02120 | | 13 | 0.01352 | 0.00200 | 0.06757 | 0.02080 | | 14 | 0.01241 | 0.00172 | 0.06769 | 0.02070 | | 15 |

0.01116 | 0.00120 | 0.06712 | 0.02050 | | 16 | 0.01014 | 0.00098 | 0.06664 | 0.02010 | | 17 | 0.00948 |

0.00088 | 0.06664 | 0.02030 | | 18 | 0.00856 | 0.00067 | 0.06628 | 0.01980 | | 19 | 0.00815 | 0.00057 | 0.06644 | 0.01970 |

Hint: You can accelerate the program by applying OpenACC to each function.

Extra Credit: Extend Neural Network to Convolutional Neural Network with OpenACC

You need to implement and accelerate the train_cnn function and the functions inside the cnn_epoch_cpp function with OpenACC. You can use any hyperparameters and filters as you like. Note that your performance of CNN should be better in accuracy than the previous 2-layer NN.

How to Execute the Program

Execute the bash script.

bash bash ./test.sh

Baseline

| Softmax Sequential | softmax OpenACC | NN Sequential | NN OpenACC | | —————— | ————— | ————- | ———- | | 9767 ms | 1066 ms | 683586 ms | 68563 ms |

NOTICE: the outcome of the classifier in training (including loss and error) should be the same as the sample outcome number by number.

Requirements &amp; Grading Policy

Machine Learning (50%)

Task1: Train MNIST with softmax regression (10%)

Task2: Accelerate softmax with OpenACC (20%)

Task3: Train MNIST with neural network (10%)

Task4: Accelerate neural network with OpenACC (10%)

Your programs should be able to compile &amp; execute to get the expected computation result to get the full grade in this part.

Performance of Your Program (30%)

7.5% for each Task

Try your best to do optimization on your parallel programs for higher speedup. If your programs show similar performance to the baseline performance, then you can get the full mark for this part. Points will be deducted if your parallel programs perform poorly while no justification can be found in the report.

One Report in PDF (20%, No Page Limit)

Regular Report (10%) The report does not have to be very long and beautiful to help you get a good grade, but you need to include what you have done and what you have learned in this project. The following components should be included in the report:

How to compile and execute your program to get the expected output on the cluster.

Explain clearly how you designed and implemented each algorithm

Show the experiment results you get, and do some numerical analysis, such as calculating the speedup and efficiency, demonstrated with tables and figures.

What kinds of optimizations have you tried to speed up your parallel program, and how do they work? Any interesting discoveries you found during the experiment?

Profiling OpenACC with nsys (10%) You are required to practice profiling OpenACC programs with nsys as we explained in the Instruction of profiling tools with perf and nsys. The command line profiling of nsys is mandatory while the GUI Nsight System is optional.

Extra Credits (10%)

Implement CNN (5%)

Accelerate CNN with OpenACC (5%)

The Extra Credit Policy

2. 10 Points deduction for each day after the DDL (11 minutes late will be considered as one day, so be careful)

File Structure to Submit on BlackBoard

“`bash .pdf # Report .zip # Codes â”œâ”€â”€ sbatch.sh â”œâ”€â”€ src â”‚ â”œâ”€â”€ nn_classifier.cpp â”‚ â”œâ”€â”€ nn_classifier_openacc.cpp â”‚ â”œâ”€â”€ simple_ml_ext.cpp â”‚ â”œâ”€â”€ simple_ml_ext.hpp â”‚ â”œâ”€â”€ simple_ml_openacc.cpp â”‚ â”œâ”€â”€ simple_ml_openacc.hpp â”‚ â”œâ”€â”€ softmax_classifier.cpp â”‚ â””â”€â”€ softmax_classifier_openacc.cpp â””â”€â”€ test.sh

5 directories, 20 files “`
