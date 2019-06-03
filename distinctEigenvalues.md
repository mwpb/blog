# Worked Examples: Distinct Real Eigenvalues

<script type="text/javascript" src="{{ base.url | prepend: site.url }}/assets/miniMathJax/MathJax.js?config=TeX-AMS_SVG"></script>

## Two Dimensional Example

Let

$$
    A = \left( \begin{array}{cc}
        1 & 2\\
        4 & 3
    \end{array} \right)
$$

and choose

$$
    x_0 = \left( \begin{array}{c}
        1\\
        0
    \end{array} \right)
$$

Then 

$$
    x_0 = \left( \begin{array}{c}
        1\\
        0
    \end{array} \right),
Ax_0 = \left( \begin{array}{c}
        1\\
        4
    \end{array}
    \right),
    A^2 x_0 = \left( \begin{array}{c}
        9\\
        16
    \end{array} \right)
$$

and hence there exist $$c_i$$ such that

$$
    c_1 \left( \begin{array}{c}
        1\\
        0
    \end{array} \right) +
c_2 \left( \begin{array}{c}
        1\\
        4
    \end{array}
    \right) +
    c_3 \left( \begin{array}{c}
        9\\
        16
    \end{array} \right) = 0
$$

Now solving the simultaneous equations 

$$c_1 + c_2 + 9 c_3 = 0$$

$$0c_1 + 4c_2 +16c_3 = 0$$

we obtain for instance $$c_3=1$$, $$c_2=-4$$ and $$c_1=-5$$.
Hence

$$
    A^2 x_0 -4A x_0 -5 x_0 = -5\left( \begin{array}{c}
        1\\
        0
    \end{array}\right) -4\left( \begin{array}{c}
        1\\
        4
    \end{array} \right) + \left( \begin{array}{c}
        9\\
        16
    \end{array} \right) = 0
$$

and so 

$$
    (A-5I)(A+I)x_0 = (A^2 -4A -5 I )x_0 = 0
$$

Therefore letting

$$
    v_1 = (A+I)x_0 = \left( \begin{array}{c}
        2\\
        4
    \end{array} \right)
$$

we see that 

$$
    (A-5I)v_1=0 \implies Av_1=5v_1
$$

Also letting 

$$
    v_2 = (A-5I)x_0 = \left( \begin{array}{c}
        -4\\
        4
    \end{array} \right)
$$

we see that 

$$
    (A+I)v_2 = 0 \implies Av_2 = -v_2
$$

For

$$
    A = \left( \begin{array}{cc}
        1 & 2\\
        4 & 3
    \end{array} \right)
$$

then

$$
    \left( \begin{array}{c}
        2\\
        4
    \end{array} \right)
$$

is an eigenvector with eigenvalue $$5$$ and 

$$
    \left( \begin{array}{c}
        -4\\
        4
    \end{array} \right)
$$

is an eigenvector with eigenvalue $$-1$$.

## Three Dimensional Example
Now we find the eigenvalues and eigenvectors of the matrix

$$A=\left(\begin{array}{ccc}
3&-1&1\\
2&0&-2\\
3&-3&1
\end{array}\right)$$

Since the second column appears to be the simplest we choose our initial vector to be

$$e_2=\left(\begin{array}{c}
0\\
1\\
0
\end{array}\right)$$

and then we calculate

$$Ae_2=\left(\begin{array}{c}
-1\\
0\\
-3
\end{array}\right),
A^{2}e_2=\left(\begin{array}{c}
-6\\
4\\
-6
\end{array}\right),
A^{3}e_2=\left(\begin{array}{c}
-28\\
0\\
-36
\end{array}\right).
$$

There are no obvious dependence relations between three of the vectors $$e_2$$, $$Ae_2$$, $$A^{2}e_2$$ and $$A^{3}e_2$$.
However we are certain that there is a dependence relation between all four:

$$
a\left(\begin{array}{c}
0\\
1\\
0
\end{array}\right)+
b\left(\begin{array}{c}
-1\\
0\\
-3
\end{array}\right)+
c\left(\begin{array}{c}
-6\\
4\\
-6
\end{array}\right)+
d\left(\begin{array}{c}
-28\\
0\\
-36
\end{array}\right)
=0
$$

and so we solve the system:

$$-b-6c-28d=0$$

$$a+4c=0$$

$$-3b-6c-36d=0$$

for which one solution is $$d=1$$, $$c=-4$$, $$b=-4$$ and $$a=16$$.
Therefore

$$\left(\alpha^{3}-4\alpha^{2}-4\alpha+16I\right)e_2=0$$

and we notice that this cubic has a factor of $$(\alpha -2I)$$ so

$$\left(\alpha - 2I\right)\left(\alpha^{2} -2\alpha -8I\right)e_2=0$$

$$\left(\alpha - 2I\right)\left(\alpha +2I)(\alpha -4I\right)e_2=0$$

This means that $$\alpha$$ has an eigenvalue $$\lambda_1 = 2$$ with eigenvector


$$(\alpha^{2}-2\alpha-8I)e_2=\left(\begin{array}{c}
-4\\
-4\\
0
\end{array}\right)$$

an eigenvalue $$\lambda_2=-2$$ with eigenvector

$$(\alpha^{2}-6\alpha+8I)e_2=\left(\begin{array}{c}
0\\
12\\
12
\end{array}\right)$$

and an eigenvalue $$\lambda_3=4$$ with eigenvector

$$(\alpha^{2}-4I)e_2=\left(\begin{array}{c}
-6\\
0\\
-6
\end{array}\right)$$

## Example of Obtaining a Subset of the Eigenvalues Quickly

Let $$A$$ be the matrix

$$\left(\begin{array}{ccc}
1 & -2 & 1\\
-4&-1&2.5\\
0&0&1.5
\end{array}\right)$$

If we choose the initial vector to be 

$$e_1=\left(\begin{array}{c}
1\\
0\\
0
\end{array}\right)$$

then

$$Ae_1= \left(\begin{array}{c}
1\\
-4\\
0
\end{array}\right)\text{ and }
A^{2}e_1=\left(\begin{array}{c}
9\\
0\\
0
\end{array}\right)$$

and so immediately we see that

$$\left(A^{2}-9I\right)e_1 = 0$$

$$\left(A-3I\right)\left(A+3I\right)e_1=0$$

Therefore 

$$(A+3I)e_1 = \left(\begin{array}{c}
4\\
-4\\
0
\end{array}\right)$$

is an eigenvector with eigenvalue $$3$$ and

$$(A-3I)e_1 = \left(\begin{array}{c}
-2\\
-4\\
0
\end{array}\right)$$

is an eigenvector with eigenvalue $$-3$$.