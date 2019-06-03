# Worked Examples: Complex Eigenvalues

<script type="text/javascript" src="{{ base.url | prepend: site.url }}/assets/miniMathJax/MathJax.js?config=TeX-AMS_SVG"></script>

## A Two Dimensional Rotation

The matrix that represents an anticlockwise rotation by $$45$$ degrees is

$$\frac{\sqrt{2}}{2}\left(
\begin{array}{cc}
1 & -1\\
1 & 1
\end{array}\right)$$

with respect to the standard basis.
If

$$v=\left(\begin{array}{cc}
1\\
0
\end{array}\right)$$

then

$$\alpha(v)=\frac{\sqrt{2}}{2}\left(\begin{array}{cc}
1\\
1
\end{array}\right)$$

and 

$$\alpha^2(v) = \frac{\sqrt{2}}{2}\left(\begin{array}{cc}
\frac{\sqrt{2}}{2}\\
\frac{\sqrt{2}}{2}
\end{array}\right)+
\frac{\sqrt{2}}{2}\left(\begin{array}{cc}
-\frac{\sqrt{2}}{2}\\
\frac{\sqrt{2}}{2}
\end{array}\right)=
\left(\begin{array}{cc}
\frac{1}{2}\\
\frac{1}{2}
\end{array}\right)+
\left(\begin{array}{cc}
-\frac{1}{2}\\
\frac{1}{2}
\end{array}\right)
=
\left(\begin{array}{cc}
0\\
1
\end{array}\right)$$

Therefore 

$$0 = \alpha^2(v)-\sqrt{2}\alpha(v)+v = (\alpha^2 -\sqrt{2}\alpha + I)v$$

which we can factorise as

$$\left(\alpha -\frac{\sqrt{2}}{2}(1+i)I\right)\left(\alpha -\frac{\sqrt{2}}{2}(1-i)I\right)=0$$

and hence

$$\left(\alpha - \frac{\sqrt{2}}{2}(1+i)I\right)v=\alpha(v)-\frac{\sqrt{2}}{2}(1+i)v$$

$$ = \frac{\sqrt{2}}{2}
\left(\begin{array}{cc}
1\\
1
\end{array}\right)
-
\frac{\sqrt{2}}{2}(1+i)
\left(\begin{array}{cc}
1\\
0
\end{array}\right)$$

$$=\frac{\sqrt{2}}{2}
\left(\begin{array}{cc}
-i\\
1
\end{array}\right)$$

is an eigenvector with eigenvalue $$\frac{\sqrt{2}}{2}(1-i)$$ and

$$\left(\alpha - \frac{\sqrt{2}}{2}(1-i)I\right)v=\alpha(v)-\frac{\sqrt{2}}{2}(1-i)v$$

$$ = \frac{\sqrt{2}}{2}
\left(\begin{array}{cc}
1\\
1
\end{array}\right)
-
\frac{\sqrt{2}}{2}(1-i)
\left(\begin{array}{cc}
1\\
0
\end{array}\right)$$

$$=\frac{\sqrt{2}}{2}
\left(\begin{array}{cc}
i\\
1
\end{array}\right)$$

is an eigenvector with eigenvalue $$\frac{\sqrt{2}}{2}(1+i)$$.

## A Two Dimensional Rotation then Magnification

The matrix that represents an anticlockwise rotation by $$90$$ degrees followed by a magnification of $$2$$ is

$$\left(
\begin{array}{cc}
0 & -2\\
2 & 0
\end{array}\right)$$

with respect to the standard basis.
If

$$v=\left(\begin{array}{cc}
1\\
0
\end{array}\right)$$

then

$$\alpha(v)=\left(\begin{array}{cc}
0\\
2
\end{array}\right)$$

and

$$\alpha^2(v)=\left(\begin{array}{cc}
-4\\
0
\end{array}\right)$$

so 

$$\alpha^2(v)+4v = 0$$

$$(\alpha^2+4)v=0$$

which factorises as

$$(\alpha -2i)(\alpha +2i)v=0$$

Hence

$$(\alpha-2i)v=\alpha(v)-2iv=\left(\begin{array}{cc}
0\\
2
\end{array}\right)-2i
\left(\begin{array}{cc}
1\\
0
\end{array}\right)=
\left(\begin{array}{cc}
-2i\\
2
\end{array}\right)
$$

is an eigenvector with eigenvalue $$-2i$$ and 

$$(\alpha+2i)v=\alpha(v)+2iv=\left(\begin{array}{cc}
0\\
2
\end{array}\right)+2i
\left(\begin{array}{cc}
1\\
0
\end{array}\right)=
\left(\begin{array}{cc}
2i\\
2
\end{array}\right)
$$

is an eigenvector with eigenvalue $$2i$$.

## A Three Dimensional Rotation

The matrix that represents an anticlockwise rotation by $$90$$ degrees around the vector 

$$v=\left(\begin{array}{cc}
0\\
\frac{\sqrt{2}}{2}\\
\frac{\sqrt{2}}{2}
\end{array}\right)$$

is

$$\left(
\begin{array}{cc}
0 & -\frac{\sqrt{2}}{2} & \frac{\sqrt{2}}{2}\\
\frac{\sqrt{2}}{2} &\frac{1}{2} & \frac{1}{2}\\
-\frac{\sqrt{2}}{2} & \frac{1}{2} & \frac{1}{2}
\end{array}\right)$$

with respect to the standard basis.
Since we spot that the sum of the second and third columns has a particularly nice form we try the initial vector

$$v=\left(\begin{array}{cc}
0\\
1\\
1
\end{array}\right)$$

and see that

$$\alpha(v)=\left(\begin{array}{cc}
0\\
1\\
1
\end{array}\right)$$

and so

$$\alpha(v)=\left(\begin{array}{cc}
0\\
1\\
1
\end{array}\right)$$

is an eigenvector with eigenvalue $$1$$.
(This shows us the axis of rotation.)
If

$$v=\left(\begin{array}{cc}
1\\
0\\
0
\end{array}\right)$$

then

$$\alpha(v)=\left(\begin{array}{cc}
0\\
\frac{\sqrt{2}}{2}\\
-\frac{\sqrt{2}}{2}
\end{array}\right)$$

and

$$\alpha^2(v)=\frac{\sqrt{2}}{2}
\left(\begin{array}{cc}
-\frac{\sqrt{2}}{2}\\
\frac{1}{2}\\
\frac{1}{2}
\end{array}\right)
-\frac{\sqrt{2}}{2}\left(\begin{array}{cc}
\frac{\sqrt{2}}{2}\\
\frac{1}{2}\\
\frac{1}{2}
\end{array}\right)=\left(\begin{array}{cc}
-1\\
0\\
0
\end{array}\right)
$$

hence

$$\alpha^2(v)+v = 0$$

$$(\alpha^2+I)v=0$$

factorising gives

$$(\alpha+iI)(\alpha-iI)v=0$$

so

$$(\alpha-iI)v=\alpha(v)-iv=\left(\begin{array}{cc}
0\\
\frac{\sqrt{2}}{2}\\
-\frac{\sqrt{2}}{2}
\end{array}\right)-i\left(\begin{array}{cc}
1\\
0\\
0
\end{array}\right)=
\left(\begin{array}{cc}
-i\\
\frac{\sqrt{2}}{2}\\
-\frac{\sqrt{2}}{2}
\end{array}\right)
$$

is an eigenvector with eigenvalue $$-i$$.
Also

$$(\alpha+iI)v=\alpha(v)+iv=\left(\begin{array}{cc}
0\\
\frac{\sqrt{2}}{2}\\
-\frac{\sqrt{2}}{2}
\end{array}\right)+i\left(\begin{array}{cc}
1\\
0\\
0
\end{array}\right)=
\left(\begin{array}{cc}
i\\
\frac{\sqrt{2}}{2}\\
-\frac{\sqrt{2}}{2}
\end{array}\right)
$$

is an eigenvector with eigenvalue $$i$$.