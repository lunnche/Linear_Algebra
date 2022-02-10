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

光看上面两个图，可能无法触发恍然大明白，来看一个栗子🌰  
$$
\left[
\begin{matrix}
1&& 2&&3\\
2&&5&&2\\
6&&-3&&1
\end{matrix}
\right]
\left[
\begin{matrix}
0\\
0\\
2
\end{matrix}
\right]=2\ times\ column\ 3=
\left[
\begin{matrix}
6\\
4\\
2
\end{matrix}
\right].
$$
看到没，最后结果直接理解成2乘以第三列

再来各栗子🌰
$$
Ax=
\left[
\begin{matrix}
1&&0&&0\\
1&&0&&0\\
1&&0&&0
\end{matrix}
\right]
\left[
\begin{matrix}
4\\
5\\
6
\end{matrix}
\right]
=
\left[
\begin{matrix}
4\\
4\\
4
\end{matrix}
\right]
$$

如果你是“行”人，你看到的就是点乘（1，0，0）和（4，5，6）得到4.如果你是个“列”人，Ax的线性组合就是4乘以第一列（1，1，1），因为第二列，第三类都是0.  

***
**identity matrix**
$$
I=
\left[
\begin{matrix}
1&&0&&0\\
0&&1&&0\\
0&&0&&1
\end{matrix}
\right]
$$
![image-20220209143253305](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220209143253305.png)



I is special.It has ones on the "main diagonal".Whatever vector this matrix multiplies,that vector is not changed.This is like multiplication by 1,but for matrices and vectors.The exceptional matrix in this example is the 3 by 3 **identity matrix**


***

## Matrix Notation

矩阵元素的记法：

​    ![image-20220209143459125](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220209143459125.png)

## Multiplication in MATLAB
咋输入呢？
Enter matrices a row at a time, and use a semicolon to signal the end of a row.Or enter by columns and transpose by `'`:
$$
A=[1\ 2\ 3;\ 2\ 5\ 2;\ 6\ -3\ 1]\\
x=[0\ 0\ 2]'\ \ or\ \ x=[0;0;2]
$$

在matlab里，矩阵乘法有三种表示方法：  
第一种：
$$
Matrix\ multiplication\ \ b=A*x
$$
第二种：
We can also pick out the first row of A (as a smaller matrix).The notation for that 3 by 3 submatrix is A(1,:).**Here the colon symbol:keeps all columns of row 1.**  
$$
Row\ at\ a\ time\ \ b=[A(1,:)*x;A(2,:)*x;A(3,:)*x]
$$

第三种：
$$
Column\ at\ a\ time\ \ b=A(:,1)*x(1)+A(:,2)*x(2)+A(:,3)*x(3)
$$

注意：matrices are stored by columns.Then multiplying a column at a time will be a little faster.So A*x is actually executed by columns.  

## Programming Languages for Mathematics and Statistics  
Julia,Python,R,Mathematica,Maple  

## review of the key ideas  
1. The basic operations on vectors are multiplication cv and vector additon v+w.
2. Together those operations give linear combinations cv+dw.
3. Matrix-vector multiplication Ax can be computed by dot products, a row at a time. But Ax must be understood as a combination of the columns of A.
4. Column picture: Ax=b asks for a combination of columns to produce b.  
5. Row picture: Each equation in Ax=b gives a line(n=2) or a plane (n=3) or a "hyperplane"(n>3).They intersect at the solution or solutions,if any.  

来个栗子🌰

![image-20220209152403217](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220209152403217.png)

![image-20220209152823146](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220209152823146.png)

## 2.2 The Idea of Elimination  

![image-20220209152918687](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220209152918687.png)

![image-20220209153704536](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220209153704536.png)

**Elimination produce an upper triangular system**  
The nonzero coefficients 1,-2,8 form a triangle.That system is solved from the bottom upwards- first y=1 and then x=3.This quick process is called **back substitution** It is used for upper triangular systems of any size, after elimination gives a triangle.  

重要的一点：The original equations have the same solution x=3 and y=1.下图shows each system as a pair of lines,intersecting at the solution point(3,1).After elimination,the lines still meet at the same point.

![image-20220209162453980](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220209162453980.png)

How did we get from the first pair of lines to the second pair?  
**To eliminate x: Subtract a multiple of equation 1 from equation 2.**  

啥玩意叫pivot？主元  
就是第一行方程中x的系数(the coefficient of x).

![image-20220209163555096](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220209163555096.png)

到47页了

**The pivots are on the diagonal of the triangle after elimination**  

## Breakdown of Elimination  
elimination produces the pivots that take us to the solution. But failure is possible.At some point,the method might ask us to divide by zero.The process has to stop.There might be a way to adjust and continue-or failure may be unavoidable.  

三个栗子🌰
第一个栗子
$$
\begin{aligned}
x-2y&=1\\
3x-6y&=11
\end{aligned}
$$
Subtract 3 times eqn.1 from eqn.2 $\downarrow$
$$
\begin{aligned}
x-2y &= 1\\
0y &=8.
\end{aligned}
$$

There is no solution to $0y=8$.Normally we divide the right side 8 by the second pivot,but this system has no second pivot.  
**Zero is never allowed as a pivot!**  
the row and column pictures show why failure was unavoidable.  

![image-20220210085217622](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220210085217622.png)
if there is no solution,elimination will discover that fact by reaching an equation like $0y=8$  

从行来看，两条平行线没有交点
从列来看，two columns in the same direction.All combinations of the columns lie along a line.But the column from the right side is in a different direction(1,11).No combination of the columns can produce this right side-therefore no solution.

第二个栗子 failure with infinitely many solutions.Change b=(1,11) to (1,3).
$$
\begin{aligned}
x-2y &= 1\\
3x-6y &=3
\end{aligned}
$$
Subtract 3 times eqn.1 from eqn.2 $\downarrow$
$$
\begin{aligned}
x-2y &= 1\\
0y &= 0
\end{aligned}
$$
$\uparrow$ still only **one pivot**

Every y satisfies $0y=0$.There is really only one equation $x-2y=1$.The unknown y is "free".  
In the row picture,the parallel lines have become the same line.Every point on that line satisfies both equations.We have a whole line of solutions.  
In the column picture.b=(1,3) is now the same as column1.

![image-20220210091438109](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220210091438109.png)

***
**Failure** For n equations we do not get n pivots
**Elimination leads to an equation** $0\neq0$ (no solution) or 0=0 (many solutions)  

**Success comes with n pivots. But we may have to exchange the n equations.**
***

Elimination can go wrong in a third way- but this time it can be fixed.  
来看个栗子🌰  
第三个栗子  
Temporary failure(zero in pivot).A row exchange produces two pivots:  
permutation:  
$$
\begin{aligned}
0x+2y &=4\\
3x-2y &=5
\end{aligned}
$$
exchange the two equations $\downarrow$
$$
\begin{aligned}
3x-2y &=5\\
2y &=4
\end{aligned}
$$

The new system is already triangular.This small example is ready for backsubstitution.  

okkkk，到这三个栗子完了，总结下：
前连个栗子 are **singular**-there is no second pivot
第三个栗子 is **nonsingular**-there is a full set of pivots and exactly one solution.  
**Singular equations have no solution or infinitely many solutions.**  
**Pivots must be nonzero because we have to divide by them.**  

## Three Equations in Three Unknowns  

消元法是谁发明的？高斯！
Gaussian elimination  

到50页了
