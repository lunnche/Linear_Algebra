# Linear Algebra

W.Gilbert Strang  

course web page:  

https://mitmath.github.io/1806/  

## solve a system of linear equations  
求解线性方程组  

n linear equations, n unkowns  
an equal number of equations and unknowns  

方成数和未知数个数相等，这种情况最让人舒服  

行图像 Row picture  

一个行图像显示一个方程  

\*Column picture  

Matrix form  

例子： 

$$
2x-y=0\\
-x+2y=3
$$
what is the coefficient matrix（系数矩阵）  

a matrix is just a rectangular array of numbers  

$$
\left[
\begin{matrix}
2 & -1 \\
-1 & 2
\end{matrix}
\right]
\left[
\begin{matrix}
x \\
y
\end{matrix}
\right]
=
\left[
\begin{matrix}
0 \\
3
\end{matrix}
\right]
$$

matrix A: matrix of coefficients  
vector of unknowns 通常用加粗的X表示（extra bold）  
右侧也是一个向量，记作b  

$$
A X = b
$$

![Screen Shot 2021-12-27 at 2.35.38 PM](https://raw.githubusercontent.com/lunnche/picgo-image/main/Screen%20Shot%202021-12-27%20at%202.35.38%20PM.png)

上图即为Row picture，而列图像column picture才是关键

$$
x
\left[
\begin{matrix}
2 \\
-1
\end{matrix}
\right]
+
y
\left[
\begin{matrix}
-1 \\
2
\end{matrix}
\right]
=
\left[
\begin{matrix}
0 \\
3
\end{matrix}
\right]
$$

该方程的目的是什么？  
目的是寻找如何将左边两个向量正确组合，从而构成右边的向量。即寻求找到正确的线性组合。  

线性组合（linear combination）是贯穿课程始终的基本方法。  

这里是列向量的线性组合  linear combination of columns  

按照之前计算过的  x=1,y=2 的线性组合可以求出b，而所有的线性组合可以求出所有可能的右侧向量，它们将填满整个平面  

![Screen Shot 2021-12-27 at 3.11.28 PM](https://raw.githubusercontent.com/lunnche/picgo-image/main/Screen%20Shot%202021-12-27%20at%203.11.28%20PM.png)

两方程两未知（2×2）情况很容易作图，现尝试推广到3×3的情况:  

$$
\begin{aligned}
2x -  y   & =  0 \\
-x + 2y-  z &= -1 \\
   - 3y+ 4z &=  4
\end{aligned}
$$

上式的矩阵形式：  

$$
A = 
\left[
\begin{matrix}
2 & -1 & 0 \\
-1 & 2 & -1 \\
0 & -3 & 4
\end{matrix}
\right]
$$

$$
b = 
\left[
\begin{matrix}
0 \\
-1 \\
4
\end{matrix}
\right]
$$

3元方程的解是一个平面
3×3问题的每一行都是三维空间的一个平面  



![Screen Shot 2021-12-27 at 4.03.58 PM](https://raw.githubusercontent.com/lunnche/picgo-image/main/Screen%20Shot%202021-12-27%20at%204.03.58%20PM.png)

然后来看column picture  

$$
x
\left[
\begin{matrix}
2\\
-1\\
0
\end{matrix}
\right]
+y
\left[
\begin{matrix}
-1\\
2\\
-3
\end{matrix}
\right]
+z
\left[
\begin{matrix}
0\\
-1\\
4
\end{matrix}
\right]
=
\left[
\begin{matrix}
0\\
-1\\
4
\end{matrix}
\right]
$$
左侧是三个向量的线性组合，每个向量均为三维向量，我们想知道，通过怎样的组合才能得到右侧向量

![Screen Shot 2021-12-27 at 4.18.51 PM](https://raw.githubusercontent.com/lunnche/picgo-image/main/Screen%20Shot%202021-12-27%20at%204.18.51%20PM.png)

问题：对于任意b，是否都能求解$Ax=b$?  
这个问题换个说法：列的线性组合是否能覆盖整个三维空间？  
对于上述3×3矩阵，答案是yes，因为它是非奇异矩阵(non-singular matrix),是可逆矩阵（invertible matrix），而对于其他一些矩阵，答案可能是no  

举例来说，什么情况下答案是no？如果三个列向量同处一个平面，那么其组合肯定也在该平面上，问题就出现了，比如列3正好等于列1加上列2，答案就是no，因为不管怎么组合，都得不出它们平面以外的向量。因此当b处在平面以内，方程组有解。但大部分不在平面内的b，均是无法构造的。这种情形称作奇异，矩阵并非可逆。不是任何b都有解。

想象下把此问题推广到9维的情况，这样就有9列，每一列都是9维空间的向量，我们来考虑其线性组合，是否对任意b都有解，还是取决于这9个列向量，比如取随机矩阵，答案很可能是yes，在matlab中使用随机命令，任意取一个9×9矩阵，保证好使，保证非奇异、可逆。但如果选择一些相互不独立的列向量，比如假设一种情况9列只相当于8列，其中一列毫无贡献，这样就会有一些b无法求得，

想象9维空间中的中的9个向量的组合，这是线性代数中必须掌握的中心内容,虽然你无法将将其具象化,但不久后你将能够做到。  

九个列向量及其线性组合将能够覆盖整个九维空间，但如果第九列碰巧等于第八列（它毫无贡献），这时线性组合就只能覆盖9维空间中的某8维平面。最后的求解也只能在这个8维平面上展开  

方程的矩阵形式 matrix form of the equation  

矩阵A乘以某向量x等于右侧向量b  
$$
Ax=b
$$

矩阵乘以向量，如何做，例如：  
第一种方法，一次取一列：
$$
\left[
\begin{matrix}
2&5 \\
1&3 
\end{matrix}
\right]
\left[
\begin{matrix}
1 \\
2
\end{matrix}
\right]
$$
取1个第1列和2个第二列之和
$$
\left[
\begin{matrix}
2&5 \\
1&3 
\end{matrix}
\right]
\left[
\begin{matrix}
1 \\
2
\end{matrix}
\right]
=1
\left[
\begin{matrix}
2 \\
1
\end{matrix}
\right]
+2
\left[
\begin{matrix}
5 \\
3
\end{matrix}
\right]
=
\left[
\begin{matrix}
12 \\
7
\end{matrix}
\right]
$$

第二种方法，一次取一行：  

用一行乘以向量，这也是点乘（dot product)的概念  
2×1+5×2=12  

Gilbert Strang 更倾向于第一种方法，see that as a linear combination of a column.

A 乘以x，可以看作A各列的线性组合  
Ax is a combination of columns of A  

以上两种方法都可以，但在以后处理数据量较大的问题时，推荐看作列的线性组合来解决问题  

p1 结束  

jsljflks
