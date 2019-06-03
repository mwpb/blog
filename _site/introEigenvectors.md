# Introduction to Eigenvectors and Eigenvalues Without Determinants

<script type="text/javascript" src="{{ base.url | prepend: site.url }}/assets/miniMathJax/MathJax.js?config=TeX-AMS_SVG"></script>

## Introduction

In the textbook 'Linear Algebra Done Right' Sheldon Axler presents the abstract theory of linear algebra in a way that eschews the use of determinants until the final chapter.
The cornerstone of this approach is a straightforward iterative argument that proves that every linear operator has at least one complex eigenvalue.
This proof is however more than just a theoretical tool.
In fact in the paper 'Computing Eigenvalues and Eigenvectors Without Determinants' William A. McWorter, Jr. and Leroy F. Meyers extend this idea to produce an algorithm for finding eigenvectors and eigenvalues.
For a brief summary of the historical context of this idea please see the introduction to that paper.


The purpose of the following series of notes is to present the ideas in McWorter and Meyers in a more relaxed fashion.


## Discrete Linear Dynamical Systems

A *dynamical system* consists of an initial state $$x_0$$ and a function $$\alpha$$ that prescribes how the state of the system changes over time.
For instance if we release from rest a hammer (or a feather) $$1$$ metre above the ground Newton's second law tells us that the distance $$\alpha$$ above the ground at time $$t$$ is:

$$\alpha(t)=1-g \frac{t^2}{2}$$

where we have assumed that we can neglect resistance forces.
If we instead only measure the system at discrete time intervals then the resulting system is called a <i>discrete dynamical system</i>.
The case that we are interested in is even simpler: we assume that the function $$\alpha$$ is a linear operator.

A *discrete linear dynamical system* consists of a sequence of vectors

$$\vec{x}_0,\vec{x}_1,\vec{x}_2,...,\vec{x}_n,...$$

such that $$\vec{x}_{i+1} = \alpha \vec{x}_{i}$$ for some linear operator $$\alpha$$.

This means that the sequence is equivalently described as:

$$\vec{x}_0,\alpha\vec{x}_0,\alpha^2\vec{x}_0,...,\alpha^n\vec{x}_0,...$$

where $$\alpha^n$$ denotes the $$n$$-fold action of $$\alpha$$.


#### Long Term Behaviour from Eigenvectors and Eigenvalues

Recall that $$v$$ is a <i>eigenvector</i> with <i>eigenvalue</i> $$\lambda$$ for the linear operator $$\alpha$$ iff

$$\alpha v = \lambda v$$

and $$v\neq 0$$.

Eigenvectors and eigenvalues give us valuable information about the long-term behaviour of discrete linear dynamical systems.
For instance, suppose that $$\alpha:\mathbb{R}^2 \rightarrow \mathbb{R}^2$$ is a linear operator and we are in the nicest possible situation:
$$\alpha$$ has two (linearly independent) eigenvectors $$v_1$$ and $$v_2$$ with eigenvalues $$\lambda_1$$ and $$\lambda_2$$ respectively.
Then we can find real numbers $$a_1$$ and $$a_2$$ such that $$x_0=a_1v_1+a_2v_2$$ whence:

$$\alpha^n (x_0) = \alpha^n(a_1v_1+a_2v_2)=a_1\alpha^n(v_1)+a_2\alpha^n(v_2)=a_1(\lambda_1)^n v_1 + a_2(\lambda_2)^n v_2.$$

Now this expression is simple enough that we can read off the long-term behaviour of this system once we have worked out the values of $$\lambda_1$$ and $$\lambda_2$$.
For instance if $$\lambda_1$$ and $$\lambda_2$$ have magnitude less than one the system will converge to zero.
If instead $$\| \lambda_1 \| < 1 $$ and $$\lambda_2 = -1$$ the system will eventually oscillate between the vectors $$a_2 v_2$$ and $$-a_2 v_2$$.

#### Dependence on Initial Conditions

Clearly the evolution of a dynamical system depends on its initial conditions.
If we return to the example of the falling hammer:
throwing the hammer gently up into the air will result in a different trajectory than just dropping it.
However, provided that the throw is not too strong, the long-term behaviour of the system is similar:
the hammer eventually falls down to the ground.
When we consider the long-term behaviour of the system we think of these outcomes as equivalent.
By contrast, if we accelerate the hammer with so much force that it escapes the Earth's gravitational field then the long-term behaviour will be different.
In this way we obtain different initial conditions that produce non-equivalent long-term behaviours.

Unsurprisingly the long-term behaviour of a general discrete linear dynamical system also depends on its initial conditions.
We will exploit this fact to simplify our calculations of eigenvalues and eigenvectors.
In fact the initial vectors can be collected into linear subspaces with the property that vectors in the same subspace induce the same long-term behaviour.


### From Proof to Method

We have seen that a knowledge of the eigenvalues and eigenvectors tells us about the long-term behaviour of a discrete linear dynamical system.
But how do we know if a given linear operator has any eigenvectors?
As a first step, let us recall the following proof which is for instance Theorem 5.10 on page 81 in 'Linear Algebra Done Right' by Sheldon Axler.

Theorem:
Every linear operator $$\alpha:\mathbb{R}^n \rightarrow \mathbb{R}^n$$ has a complex eigenvalue when $$n>0$$.

Proof:
Starting with an arbitrary non-zero initial vector $$x_0$$ consider the sequence

$$\vec{x}_0,\alpha\vec{x}_0,\alpha^2\vec{x}_0,...,\alpha^n\vec{x}_0,...$$

and ask the question: are there any dependence relations between the vectors in this sequence?

Of course since the dimension of $$\mathbb{R}^n$$ is $$n$$ we see that <i>at the very least</i> the first $$(n+1)$$ vectors in the sequence must necessarily be linearly dependent.
Hence we can find real numbers $$c_i$$ such that

$$c_0 x_0 + c_1 \alpha x_0 + c_2 \alpha^2 x_0 + ... + c_n \alpha^n x_0 = 0 $$

which we can rewrite as

$$(c_0 I + c_1 \alpha + c_2 \alpha^2 + ... + c_n \alpha^n) x_0 = 0 $$

where $$I$$ is the $$(n\times n)$$ identity matrix.
By factorising the polynomial we can find $$n$$ <i>complex</i> numbers $$\lambda_i$$ such that

$$(\alpha-\lambda_1 I)(\alpha - \lambda_2 I)...(\alpha - \lambda_n I )x_0=0$$

from which we find at least one eigenvalue and eigenvector for $$\alpha$$ as follows:

* if $$(\alpha-\lambda_n I)x_0=0$$ then $$x_0$$ is an eigenvector with eigenvalue $$\lambda_n$$;
* if $$(\alpha-\lambda_n I)x_0\neq 0$$ then check if $$(\alpha - \lambda_{n-1} I)(\alpha - \lambda_n I)x_0 =0$$:
    * if so then $$(\alpha - \lambda_n)x_0$$ is an eigenvector with eigenvalue $$\lambda_{n-1}$$;
* if not then iterate this process until you find an eigenvalue or conclude that
    $$v= (\alpha - \lambda_2 I)...(\alpha - \lambda_n I )x_0\neq 0$$
    from which we conclude that $$v$$ is an eigenvector with eigenvalue $$\lambda_1$$.
    $$\blacksquare$$

Note that the use of complex numbers was only necessary to factorise the polynomial into linear factors.
If we wanted to work only with real numbers then at this stage we could only factorise the polynomial into a mixture of linear and irreducible quadratic factors.
If all the factors were irreducible quadratic factors then we would not obtain any real eigenvalues.

Note further that although we are guaranteed to have a dependence relation between the first $$(n+1)$$ terms in the sequence

$$\vec{x}_0,\alpha\vec{x}_0,\alpha^2\vec{x}_0,...,\alpha^n\vec{x}_0,...$$

it is quite possible that a smaller subset of these vectors are linearly dependent.
If this happens it is advantageous to use the smaller subset.
This is because the polynomial we then need to factorise will be of lower degree.
Contrast this with the method of finding eigenvalues using a determinant:
with that method one always needs to calculate an $$n\times n$$ determinant and then solve a degree $$n$$ polynomial.