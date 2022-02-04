# Solving Linear Equations  

## 2.1 Vectors and Linear Equations  

![image-20220204154108499](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220204154108499.png)

The central problem of linear algebra is to solve a system of equations. Those equations are linear, which means that the unknown are only multiplied by numbers--wenever see x times y.  

![image-20220204154515925](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220204154515925.png)

The first equation $x-2y=1$ produces a straight line in the xy plane. The point x=1,y=0 is on the line because it solves that equation.  
The slope of this particular line is $\frac{1}{2}$,because y increases by 1 when x changes by 2. But slopes are important in calculus and this is linear algebra!  

![image-20220204160145351](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220204160145351.png)

**ROWS  The row picture shows two lines meeting at a single point (the solution).**  

![image-20220204160821281](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220204160821281.png)

Turn now to column picture.  
If you separate the original system into its columns instead of its rows, you get a vector equations:  
$$
\mathbf{Combination\ equals\ b}\ \ \ x
\left[
\begin{matrix}
1\\
3
\end{matrix}
\right]
+y
\left[
\begin{matrix}
-2\\
2
\end{matrix}
\right]=
\left[
\begin{matrix}
1\\
11
\end{matrix}
\right]
=b.
$$

This has two column vectors on the left side. The problem is to find the combination of those vectors that equals the vector on the right. 

**COLUMNS The column picture combines the column vectors on the left side to produce the vector b on the right side.**

![image-20220204161044067](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220204161044067.png)

到32页中间
