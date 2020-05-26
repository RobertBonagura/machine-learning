# Linear Algebra Review

## Addition and Scalar Multiplication
### Matrix Addition
* Add each element one at a time
* Has to be matrices of the same dimension
### Scalar Multiplication
Multiplying or Dividing each element by a number
### Combination of Operands
You can use the in combination, such as if *A, B*, and *C* are all vectors of the same size:
* 3 * A + B - C / 3 is valid

## Matrix Vector Multilication
i.e. a 3x2 * 2x1
* Vector will always have to have size of Matrix's column dimension.

Result in this case will be a 3 x 1, a 3 dimensional vector.

### Details
To get *y<sub>i</sub>*, multiply *A*'s *i<sup>th</sup>* row with elements of vector *x*, and add them up.

## Matrix Matrix Multiplication
Very similar to Matric Vector

For *A* x *B* = *C* :
* The *i<sup>th</sup>* column of the matrix *C* is obtained by multiplying the *i<sup>th</sup>* row of *A* with the *i<sup>th</sup>* column of *B*

## Matrix Multiplication Properties
1. Matrix Multiplication is NOT Commutative
2. Matrix Multiplication IS Associative
3. For any matrix A, A * I = I * A = A
    * The Identity Matrix has 1's along the main diagonal and 0's everywhere else
    * Note that in general, AB != BA
    * However, AI = IA

## Inverse and Transpose
### Matrix Inverse:
If *A* is an m x m matrix, and if it has an inverse:
* *AA<sup>-1</sup>* = *A<sup>-1</sup>A* = *I*

Matrices that don't have an inverse are "singular" or "degenerate"

### Matrix Transpose:
Tranpose each row in a matrix as a column
* Let *A* be an m x n matrix, and let *B* = *A<sup>T</sup>*. Then *B* is an n x m matrix, and *B<sub>ij</sub>* = *A<sub>ji</sub>*