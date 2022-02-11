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

To understand Gaussian elimination,you have to go beyond 2 by 2 systems.Three by Three is enough to see the patten.For now th ematrices are square - an equal number of rows and columns.Here is 3 by 3 system,specially constructed so that all elimination steps lead to whole numbers and not fractions:  
$$
\begin{aligned}
2x+4y-2z&=2\\
4x+9y-3z&=8\\
-2x-3y+7z&=10
\end{aligned}
$$

What are the steps?the first pivot is the 2(upper left).Below that pivot we want to eliminate the 4.The first multiplier is the ratio 4/2 =2. Multiply the pivot equation by $l_{21}$ and subtract.Subtraction removes the 4x from the second equation:

**Step1** Subtract 2 times equation 1 from equation 2.This leaves $y+x=4$.
We also eliminate -2x from equation 3-still using the first pivot.The quick way is to add equation 1 to equation 3.Then 2x cancles -2x.We do exactly that,but the rule in this book is to **subtract rather than add**.The systematic pattern has multiplier $l_{31}=-2/2=-2$. Subtracting -1 times an equation is the same as adding.  

**Step2** Subtract -1 times equation 1 from equation 3.This leaves y+5z=12.The two new equations involve only y and z. The second pivot is 1:  
**x is eliminated**
$$
\begin{aligned}
1y+1z&=4\\
1y+5z&=12
\end{aligned}
$$
We have reached a 2 by 2 system.The final step eliminates y to make it 1 by 1:  

**Step3**  Subtract equation $2_{new}$ from $3_{new}$.The multiplier is 1/1=1.Then 4z=8.The original Ax=b has been converted into an upper triangular $Ux=c$:  

![image-20220210144959946](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220210144959946.png)

The goal is achieved -forward elimination is complete from A to U.  
**Notice the pivots 2,1,4 along the diagonal of U.**
**The pivots 1 and 4 were hidden in the original system.Elimination brought them out.**  
Ux=c is ready for **back substitution**,which is quick:  
$$
(4z=8\ gives\ z=2)\ (y+z=4\ gives\ y=2)\ (equation\ 1\ gives\ x=-1)
$$
The solution is (x,y,z)=(-1,2,2).The row picture has three planes from three equations.All the planes go through this solution.The original planes are sloping,but the last plane 4z=8 after elimination is horizontal.  
The column picture show a combination Ax of column vectors producing the right side b.The coefficients in that combination are -1,2,2(the solution):
$$
Ax=(-1)
\left[
\begin{matrix}
2\\
4\\
-2
\end{matrix}
\right]
+2
\left[
\begin{matrix}
4\\
9\\
-3
\end{matrix}
\right]
+2
\left[
\begin{matrix}
-2\\
-3\\
7
\end{matrix}
\right]
\ equals\ 
\left[
\begin{matrix}
2\\
8\\
10
\end{matrix}
\right]=b.
$$

The numbers x,y,z multiply columns 1,2,3 in Ax=b also in the triangular Ux=c.  


For an n by n problem,elimination proceeds in the same way.Here is the whole idea, column by column from A to U,when Gaussian elimination succeeds.  

所以呢总结下n×n矩阵，用消元法的步骤：
**Column 1. Use the first equation to create zeros below the first pivot.**
**Column 2.Use the new equation 2 to create zeros below the second pivot.
**Column 3 to n. Keep going to find all n pivots and the upper triangular U.**  

![image-20220210150811152](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220210150811152.png)

The result of forward elimination is an upper triangular system. It is nonsingular if there is a full set of n pivots (never zero!).

## review of the key ideas  
1. A linear system (Ax=b) becomes **upper triangular**(Ux=c) after elimination.  
2. We **subtract** $l_{ij}$ times equation j from equation i, to make the (i,j) entry zero.  
3. The **multiplier** is $l_{ij}=\frac{entry\ to\ eliminate\ in\ row\ i}{pivot\ in\ row\ j}$.**Pivots** can not be zero!  
4. When zero is in the pivot position,**exchange rows** if there is a nonzero below it.  
5. The upper triangular Ux=c is solved by **back substitution**(starting at the bottom).  
6. When **breakdown** is permanent,Ax=b has no solution or infinitely many.  

$$
A=
\left[
\begin{matrix}
1&&1&&0\\
1&&2&&1\\
0&&1&&2
\end{matrix}
\right]
$$

This A is a "band matrix".Everything stays zero outside the band.  

问题？
Suppose A is already a **triangular matrix**(upper triangular or lower triangular).Where do you see its pivots?When does Ax=b have exactly one solution for every b?  

**Solution** The pivots of a triangular  matrix are already set along the main diagonal.Elimination succedds when all those numbers are nonzero.Use **back** substitution when A is upper triangular,go **forward** when A is lower triangular.  

来看一个具体实栗：  
用消元法解方程：  
$$
\begin{aligned}
x+y+z&=7\\
x+y-z&=5\\
x-y+z&=3
\end{aligned}
$$

![image-20220210155220557](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220210155220557.png)

## 2.3 Elimination Using Matrices  

![image-20220210155709714](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220210155709714.png)

到58页

This section gives our first example of **matrix multiplication**  

we start with matrices that contain many zeros.  

E acts on a vector b or a matrix A to produce a new vector Eb or a new matrix EA.  

Our first example will be **"elimination matrices."** They execute the elimination steps:   
Multiply the $j^{th}$ equation by $l_{ij}$ and subtract from $i^{th}$ equation.(This eliminates $x_j$ from equation i)注意这里，  
We need a lot of these simple matrices $E_{ij}$,one for cvery nonzero to be eliminated below the main diagonal.  

Fortunately we won't see all these matrices $E_{ij}$ in later chapters. They are good examples to start with, but there are too many.They can combine into one overall matrix $E$ that takes all steps at once.The neatest way is to combine all their inverses $(E_{ij})^{-1}$ into one overall matrix $L=E^{-1}$  

接下来看看：
1. 矩阵乘法的每一步是怎样的
2. 怎样把那些$E_{ij}$组合成E
3. 看看每个$E_{ij}$是如何求逆的
4. 把所有的$E_{ij}^{-1}$组成L  


L的特性是所有的乘数$l_{ij}$都"在适当的位置？" (fall into place). Those numbers are mixed up in E(forward elimination from A to U). They are perfect in L(unding elimination,returning from U to A).Inverting puts the steps and their matrices $E_{ij}^{-1}$ in the opposite order and that prevents the mixup.  

## Matrices times Vectors and Ax=b

![image-20220211091108621](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211091108621.png)

**A times x** is exactly chosen to yield the three equations.
矩阵乘以向量，怎么定义它呢，怎样定义能生成三个方程就怎样定义。  

Review of A times x:  
A matrix times a vector gives a vector.

![image-20220211093211989](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211093211989.png)

key point:Ax=b represents the row form and also the column form of the equations.  

![image-20220211093349990](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211093349990.png)

Ax is a combination of the columns of A.To compute each component of Ax, we use the row form of matrix multiplication.  
Components of Ax are dot products with rows of A.The short formula for that dot product with x uses "sigma notation"
The first component of Ax above is $(-1)(2)+(2)(4)+(2)(-2)$
The ith component of Ax is 
$$
(row\ i) \cdot x=a_{i1}x_1 +a_{i2}x_2+\cdots+a_{in}x_n.
$$

This is sometimes written with the sigma symbol as:  
$$
\sum_{j=1}^n a_{ij} x_j .
$$
$\sum$ is an instruction to add. Start with j=1 and stop with j=n. The sum begins with $a_{i1}x_1$ and ends with $a_{in}x_n$. That produces the dot product (row i)$\cdot$x.  

The word "entry" for a matrix corresponds to "component" for a vector.General rule:  
$$
a_{ij}=A(i,j)\ is\ in\ row\ i,column\ j.
$$

爱因斯坦记法：
Einstein shortened this even more by omitting the $\sum$. The repeated j in $a_{ij}x_j$ automatically meant addition. He also wrote the sum as $a_i^j x_j$  

## The Matrix Form of One Elimination Step  

怎么把某一步消元的步骤，用一个矩阵来表示？  
We want to do that subtracton with a matrix!The same result $b_{new}=Eb$ is achieved when we multiply an "elimination marix" E times b.It subtracts $2b_1$ from $b_2$ 

![image-20220211101750547](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211101750547.png)

***
The **identity matrix** has 1's on the diagonal and otherwise 0's.Then $Ib=b$ for all b.The **elementary matrix or elimination matrix** $E_{ij}$ has the extra nonzero entry $-l$ in the i,j position.Then $E_{ij}$ subtracts a multiple l of row j from row i.  
***

好了上面说的是E乘以向量（Ax=b右边的b）的情况，What about the left side?  
**The purpose of** $\mathbf{E_{31}}$ **is to produce a zero in the (3,1) position of the matrix.**  

The notation fits this purpose .Start with A. Apply E's to produce zeros below the pivots(the first E is $E_{21}$.End with a triangular U.  
看看这些步骤的细节：  
首先，The solution x is not changed by elimination.只是coefficient matrix变了而已。
When we start with Ax=b and multiply by E,the result is $EAx=Eb$.

## Matrix Multiplication  
一个大问题：
**How do we multiply two matrices?**

$$
E(Ax)=Eb\ \ \ is\ also\ (EA)x=Eb
$$

parentheses are not needed.We just write $EAx$  

associative law:
$$
3 \times (4 \times 5)=(3\times 4)\times 5
$$
commutative law:
$$
3 \times 4 = 4\times 3
$$

在矩阵乘法中，associative law is true,commutative law is false: 

![image-20220211110126120](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211110126120.png)

we also should be able to multiply matrices EB a column a t a time:

![image-20220211110323592](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211110323592.png)

**The beauty of matrix multiplication is that all three approaches(rows,columns,whole matrices) come out right."**

## The Matrix Pij for a Row Exchange  
To subtract row j from row i we use $E_{ij}$.  
To exchange or "permute" those rows we use another matrix $P_ij$(a **permutation matrix**).A row exchange is needed when zero is in the pivot position.Lower down,that pivot column may contain a nonzero.By exchanging the two rows, we have a pivot and elimination goes forward.  

![image-20220211143517170](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211143517170.png)

![image-20220211143603530](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211143603530.png)

![image-20220211143648525](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211143648525.png)

## The Augmented Matrix  

Key idea: Elimination does the same row operations to A and to b. **We can include b as extra column and follow it through elimination.**.The matrix A is enlarged or "augmented" by the extra column b:

![image-20220211144121619](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211144121619.png)

Elimination acts on whole rows of this matrix. The left side and right side are both multiplied by E, to subtract 2 times equation 1 from equation 2. With [A b] those steps happen together.  

Notice again the word "acts".This is essential.Matrices do something!The matrix A acts on x to produce b.The matrix E operates on A to give EA.  
The whole process of elimination is a sequence of row operations.  

## review of the key ideas  
1. $Ax=x_1$ times column $1+\cdots+x_n$ times column n.And  
$$
(Ax)_i=\sum_{j=1}^n a_{ij} x_j.
$$
2. Identity matrix=I,elimination matrix=$E_{ij}$ using $l_{ij}$,exchange matrix=$P_{ij}$.
3. Multiplying Ax=b by $E_{21}$ subtracts a multiple $l_{21}$ of equation 1 from equation 2.The number $-l_{21}$ is the (2,1) entry of the elimination matrix $E_21$
4. For the augmented matrix [A b],that elimination step gives 
$$
\left[
\begin{matrix}
E_{21}A && E_{21}b
\end{matrix}
\right].
$$
5. When A multiplies any matrix B, it multiplies each column of B separately.  

来来来一个栗子🌰
matrix $E_{21}$ subtracts 4 times row 1 from row 2:
$$
E_21=
\left[
\begin{matrix}
1&&0&&0\\
-4&&1&&0\\
0&&0&&1
\end{matrix}
\right]
$$
注意：这个矩阵$E_{21}$乘在向量左边，表示啥，表示第二行减去（第一行乘以4），如果是乘在向量右边呢？是从第一列里减去4倍的第二列。  
类似的，对于permutation matrix,乘在左边是二三行互换，乘在右边是2、3列互换。  

## Rules for Matrix Operations  

![image-20220211152552015](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211152552015.png)

A matrix is a rectangular array of numbers or "entries".  
When A has m rows and n columns, it is an "m by n" matrix.  
Matrices can be added if their shapes are the same.
Theycan be multiplied by any constant c.  

Matrices are added exactly as vectors are- one entry at a time.   

The entry in row i and column j is called $a_{ij}$ or A(i,j). 

**To multiply AB: If A has n columns, B must have n rows.**

![image-20220211160750658](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211160750658.png)

![image-20220211161018949](https://raw.githubusercontent.com/lunnche/picgo-image/main/image-20220211161018949.png)

矩阵乘法的第一种方法就是take the dot product of each row of A with each column of B. 
$$
The\ entry\ in\ row\ i\ and\ column\ j\ of\ AB\ is\ (row\ i\ of\ A)\cdot(column\ j\ of\ B).
$$

到71页了
