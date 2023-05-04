Download Link: https://assignmentchef.com/product/solved-cs596-homework-4
<br>
<strong>Problem 1: </strong>We would like to test the ability of the first kernel method (discussed in the class) to approximate pdfs. Therefore we generate 1000 realizations of a random variable uniformly distributed in [0<em>,</em>1]. a) Approximate the corresponding pdf using the Gaussian kernel

K<em>.</em>

Plot the resulting approximations for different values of <em>h</em>. Do not limit your graph in [0<em>,</em>1] but extend it beyond the two boundaries. What do you observe as far as capturing the support of the random variable (the interval [0<em>,</em>1]) and the constant value of the pdf (equal to 1 in [0<em>,</em>1]) is concerned? b) Complete the same steps for the Laplacian kernel

K<em>.</em>

<strong>Problem 2: </strong>The Matlab data file hw4-2data.mat contains two matrices: stars and circles each being a list of 2 dimensional (2-D) vectors. Each 2-D vector identifies a point in the 2-D space which is labeled either as star or circle. We are interested in developing a classifier that distinguishes between the two sets. We would like to use the kernel method to find a nonlinear separating boundary. To achieve this we assign the label “1” to stars and the label “−1” to circles and if <em>φ</em>(<em>X</em>)<em>,X </em>= [<em>x</em><sub>1</sub><em>,x</em><sub>2</sub>]<sup>| </sup>is the transformation we would like to apply to the data then we want to solve the following minimization problem to find the optimum <em>φ</em>(<em>X</em>)

<em>,                                       </em>(1)

where V is the vector space of functions generated by the Gaussian kernel

K(<em>X,Y </em>) = <em><sub>e</sub></em>−<em><sub>h</sub></em><u><sup>1</sup></u>k<em>X</em>−<em>Y </em>k<sup>2 </sup>= <em><sub>e</sub></em>−<em><sub>h</sub></em><u><sup>1</sup></u>{(<em>x</em><sub>1</sub>−<em>y</em><sub>1</sub>)<sup>2</sup>+(<em>x</em><sub>2</sub>−<em>y</em><sub>2</sub>)<sup>2</sup>}<em>.</em>

<ol>

 <li>Use the Representer theorem to prove that for the first two sums we can replace <em>φ</em>(<em>X</em>) by its orthogonal projection <em>φ</em><sup>ˆ</sup>(<em>X</em>) onto the linear subspace generated by K(<em>X,X<sub>i</sub></em>)<em>,X<sub>i </sub></em>∈ stars and K(<em>X,X<sub>j</sub></em>)<em>,X<sub>j </sub></em>∈ circles where</li>

</ol>

<em>φ</em><sup>ˆ</sup>(<em>X</em>) = <sup>X </sup><em>α<sub>i</sub></em>K(<em>X,X<sub>i</sub></em>) + <sup>X </sup><em>β<sub>j</sub></em>K(<em>X,X<sub>j</sub></em>)<em>.                                                                              </em>(2)

<em>X<sub>i</sub></em>∈stars                                    <em>X<sub>j</sub></em>∈circles

<ol>

 <li>For the term k<em>φ</em>(<em>X</em>)k<sup>2 </sup>use the orthogonality principle to show that</li>

</ol>

k<em>φ</em>(<em>X</em>)k<sup>2 </sup>= k<em>φ</em><sup>ˆ</sup>(<em>X</em>)k<sup>2 </sup>+ k<em>φ</em>(<em>X</em>) − <em>φ</em><sup>ˆ</sup>(<em>X</em>)k<sup>2 </sup>≥k<em>φ</em><sup>ˆ</sup>(<em>X</em>)k<sup>2</sup><em>.</em>

Does this suggest that we can replace <em>φ</em>(<em>X</em>) with <em>φ</em><sup>ˆ</sup>(<em>X</em>) everywhere in the original cost function in (1)? If yes, then WHY? c) Using the form of <em>φ</em><sup>ˆ</sup>(<em>X</em>) defined in (2), find the optimum coefficients <em>α<sub>i</sub>,β<sub>j</sub></em>. d) Once you identify the optimum <em>φ</em><sup>ˆ</sup>(<em>X</em>) explain how you are going to use it to classify a new point <em>X</em><sub>new </sub>as “star” or

“circle” given, of course, that <em>φ</em><sup>ˆ</sup>(<em>X</em><sub>new</sub>) will not be exactly equal to 1 or −1. e) After you have specified your final classification rule in d) find (numerically) the separating boundary for the two classes in the 2-D space (also place the training points on the 2-D plane to verify the quality of your boundary). Repeat the process for different values of <em>h </em>and <em>λ</em>.

<strong>Problem 3: </strong>Suppose that the scalar random variable <em>y </em>and the random vector <em>X </em>are related through the following model

<em>y </em>= <em>θ</em><sub>∗</sub><sup>|</sup><em>X </em>+ <em>w,                                                                                                  </em>(3)

where <em>w </em>is a scalar random variable with mean 0 and independent from <em>X </em>and <em>θ</em><sub>∗ </sub>a deterministic vector. Assuming that we have knowledge of the statistical behavior of the random pair (<em>y,X</em>) we would like to <em>estimate θ</em><sub>∗ </sub>by solving the following minimization problem

minE[(<em>y </em>− <em>θ</em><sup>|</sup><em>X</em>)<sup>2</sup>]<em>.            </em>(4) <em>θ</em>

<ol>

 <li>a) Find the optimum <em>θ </em>and prove that it is equal to <em>θ</em><sub>∗</sub>. b) Assume now that the statistical behavior of the pair (<em>y,X</em>) is not available and, instead, you are observing pairs (<em>y<sub>t</sub>,X<sub>t</sub></em>) that are independent realizations of (<em>y,X</em>). Find the learning (adaptive) algorithm that provides a new estimate <em>θ<sub>t </sub></em>every time a new pair (<em>y<sub>t</sub>,X<sub>t</sub></em>) becomes available. The resulting algorithm is known as <em>Least Mean Squares </em>(LMS) and constitutes the most well known algorithm in Adaptive Signal Processing. c) Use your own favorite <em>θ</em><sub>∗</sub>, of length 5, generate pairs (<em>y<sub>t</sub>,X<sub>t</sub></em>) using the model in (3), where <em>X<sub>t </sub></em>is a Gaussian vector of length 5 with independent and identically distributed elements of mean 0 and variance 1 and <em>w<sub>t </sub></em>is again Gaussian independent from <em>X<sub>t </sub></em>with mean 0 and variance 0.1. Apply your algorithm from b) and verify its convergence towards <em>θ</em><sub>∗</sub>. Select a small learning rate so that your estimates are not very “noisy”. Plot the squared norm k<em>θ<sub>t </sub></em>− <em>θ</em><sub>∗</sub>k<sup>2 </sup>as a function of the iteration <em>t </em>and examine whether it converges to something small. Use logarithmic scale (“semilogy” in Matlab) to be able to observe differences between small quantities. d) Repeat the previous simulation but with a learning rate which is half the learning rate you used in question c). What do you observe as far as convergence rate and steady state error is concerned? Can you compare the performance in the two cases and claim that one is “better” than the other?</li>

</ol>