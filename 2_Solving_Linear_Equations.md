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

two basic operations in linear algebra:  
$$
\mathbf{Scalar\ multiplication}\ \ 3
\left[
\begin{matrix}
1\\
3
\end{matrix}
\right]=
\left[
\begin{matrix}
3\\
9
\end{matrix}
\right]
$$


$$
\mathbf{Vector\ addition}\ \ 
\left[
\begin{matrix}
3\\
9
\end{matrix}
\right]+
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
$$

![image-20220206151809872](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220206151809872.png)

four steps to understanding elimination using matrices.  
1. Elimination goes from A to a triangular * by a sequence of matrix steps $E_{ij}$.
2. The triangular system is solved by $\mathbf{back substitution}$: working bottom to top.  
3. In matrix language A is factored into LU=(lower triangular)(upper triangular).  
4. Elimination succeeds if A is invertible.(But it may need row exchanges.)

The most-used algorithm in computational science takes those steps (MATLAB calls it **lu**).Its quickest form is backslash:$x=A \backslash b$.
But linear algebra goes beyond square invertible matrices.可逆方阵?

For m by n matrices, $Ax=0$ may have many solutions. Those solutions will go into a $\mathbf{vector space}$.The $\mathbf{rank}$ of A leads to the $\mathbf{dimension}$ of that vector space.
这话得翻译下：m×n矩阵Ax=0 可能有很多解。这些解构成向量空间。系数矩阵A的秩就是该向量空间的维数。  

## Three Equations in Three Unknowns  
三个未知数x,y,z,三个方程
$$
Ax=b\ \ \ \ \ 
\left[
\begin{matrix}
x+2y+3z=6\\
2x+5y+2z=4\\
6x-3y+z=2
\end{matrix}
\right]
$$
我们想找出同时满足三个方程的x,y,z值，可能找到，也可能粗存在。一般情况下，如果未知数个数等于方程数，一般都有解。
这个方程组的不同视点：
**ROW** The row picture shows three planes meeting at a single point.
**COLUMN** The column picture combines three columns to produce $b=(6,4,2)$.

**The column form will now show immediately why z=2**

$$
The\ column\ pictures\ starts\ with\ the\ vector\ form\ of\ the\ equations\ Ax=b:
$$

$$
\mathbf{Combine\ columns}\ \ \ \ \ 
x
\left[
\begin{matrix}
1\\
2\\
6
\end{matrix}
\right]+y
\left[
\begin{matrix}
2\\
5\\
-3
\end{matrix}
\right]+z
\left[
\begin{matrix}
3\\
2\\
1
\end{matrix}
\right]=
\left[
\begin{matrix}
6\\
4\\
2
\end{matrix}
\right]
=b.
$$

一看就知道：
$$
\mathbf{Correct\ combination}\ \ (x,y,z)=(0,0,2) \ \ \ \ \  0
\left[
\begin{matrix}
1\\
2\\
6
\end{matrix}
\right]
+0
\left[
\begin{matrix}
2\\
5\\
-3
\end{matrix}
\right]
+2
\left[
\begin{matrix}
3\\
2\\
1
\end{matrix}
\right]
=
\left[
\begin{matrix}
6\\
4\\
2
\end{matrix}
\right]\ .
$$

很自然，看出来，取z=2 ，前边都是0，可解  

## The Matrix Form of the Equations  

**The "coefficient matrix" in** $Ax=b\ \ $ is
$$
A=
\left[
\begin{matrix}
1&&2&&3\\
2&&5&&2\\
6&&-3&&1
\end{matrix}
\right]\ .
$$

$$
\mathbf{Matrix\ equation}\ \ Ax=b\ \ 
\left[
\begin{matrix}
1&&2&&3\\
2&&5&&2\\
6&&-3&&1
\end{matrix}
\right]
\left[
\begin{matrix}
x\\
y\\
z
\end{matrix}
\right]
=
\left[
\begin{matrix}
6\\
4\\
2
\end{matrix}
\right]\ .
$$

Basic question:**What does it mean to "multiply A times x"?** 可以用行来乘，可以用列来乘，不管怎么乘，结果应该一样，以此为基准、诉求来定义什么是矩阵和向量相乘。  

![image-20220206161405936](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220206161405936.png)



![image-20220206161441333](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220206161441333.png)


