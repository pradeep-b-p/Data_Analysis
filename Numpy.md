# Numpy

NumPy (Numerical Python) is one of the core packages for numerical computing in Python. Pandas, Matplotlib, Statmodels and many other Scientific libraries rely on NumPy.
NumPy major contributions are:
•	Efficient numeric computation with C primitives
•	Efficient collections with vectorized operations
•	An integrated and natural Linear Algebra API
•	A C API for connecting NumPy with libraries written in C, C++, or FORTRAN.
Let's develop on efficiency. In Python, everything is an object, which means that even simple ints are also objects, with all the required machinery to make object work. We call them "Boxed Ints". In contrast, NumPy uses primitive numeric types (floats, ints) which makes storing and computation efficient.
 


import numpy as np
NewVar -> Variable created for copying the numpy array or due the functionality holds within np.

VIP
1.	Var = np.array_function.reshape(R,C)	-> This function can reshape the array into required shape. Using array creating function and specifying the Number of rows and columns
If we are not sure about anly one of parameter either row/column in such case we can mention “-1” it automatically adjusts the row/column.
Ex - Var = np.random.randint(3,10, 9).reshape(3,-1)


Methods of Creating Array
1.	Var = np.array(list)	-> Creates an array from the list
2.	Var = np.array(list, dtype=x)	-> Creates an array with the specified datatype for element X can be int/int32.., float/float64.., complex….
3.	Var = np.arange(Start, End, Step)	-> Creates an array from the range
4.	Var = np.array([list1, list2])	-> Creates an 2D array.
5.	Var = np.array([[list1, list2]])	-> Creates an 3D array.
6.	Var = np.array([list1, list2, listn], ndmin=x)	-> Creates an array with the specified dimension - x
7.	Var = np.zeros(R, dtype=x)	-> Creates a 1D array of zeros 
8.	Var = np.zeros([R, C])	-> Creates a 2D array of zeros
9.	Var = np.ones(R, dtype=x)	-> Creates a 1D array of zeros 
10.	Var = np.ones([R, C])	-> Creates a 2D array of zeros
11.	Var = np.eye(3)		-> Creates a 2D square array with 1 at diagonal position.
12.	Var= np.eye(R, C, dtype=x, k=y)		-> Creates a 2D square array with mentioned Row and column with 1 at diagonal position.
* Here k refers to the position of the diagonal.
* diagonal is 0 -> 1’s position is at Center, 
* diagonal is +ve -> 1’s position is at above center
* diagonal is -ve -> 1’s position is at below center
13.	Var = np.diag([val1,val2,val3….valn], k=y)	-> Places mentioned values as diagonal element
14.	Var = np.linspace(Start, End, Number_of_spacing)	-> Will split the range in given interval
* Note if Number_of_spacing is not given by default 50 is considered.
15.	Var = np.random.rand(R) 	-> Creates a 1D array of random values (>0 and <1)
16.	Var = np.random.rand(R,C) 	-> Creates a 2D array of random values (>0 and <1)
17.	Var = np.random.randn(R) 	-> Creates a 1D array of random values (+ve to -ve)
18.	Var = np.random.randn(R,C) 	-> Creates a 2D array of random values (+ve to -ve)
19.	Var = np.random.randint(lower, higher, number_of_values) 	-> Creates a 1D array of random values b/w the mentioned limit and gives specified number of values
20.	Var = np.random.randint(lower, higher, number_of_values, [R, C]) 	-> Creates a 2D array of random values b/w the mentioned limit and gives specified number of values, in Rows and Columns.


#
Other Functions
1.	Var.ndim	-> Gives the dimension of an array.
2.	np.arange(Start, End, Step)	-> Creates a range of values from the given range.
3.	Var.Shape	-> Gives the row and columns in the array/matrix
4.	NewVar = Var.reshape([number_of_sets], rows, columns)	-> reshapes the array
Note - For reshaping the matrix the number of values should distribute equally among the row and columns
•	number_of_sets is optional for creating multi dimension array
5.	NewVar = Var.reshape(-1)	-> Converts the multi dimension array into 1D array.
6.	np.nditer(var)	-> used for iterating the elements of an array, irrespective any number of dimension
for i in np.nditer(Var):
    print(i)
7.	np.ndenumerate(var)	-> Gives the index position along with the value
for i in np.ndenumerate(Var):
    print(i)
8.	np. concatenate ([var1, var2], axis=0/1)	-> Concatenate function combines the array, if its 1D it will concatenate horizontally.
Multi dimension array can be concatenated either in horizontally/vertically
9.	NewVar = np.where(var with condition)	-> Where function - performs search operation and gives the index value
Ex - op = np.where(var1 % 2==0)
10.	NewVar = var.searchsorted(number, side='right'/'left')	-> Search Sorted Array function - gives the index where the number/alphabet can be inserted
11.	NewVar = np.sort(var)	-> Sort - Sorts the elements of an array
12.	NewVar = Var[Var[condition]]	-> Filters the array and gives only those values.
13.	np.random.shuffle(a)	-> Shuffles the array
print(a)
14.	Var = np.resize(var, [R,C])	-> Changes the row and column order
•	The value keeps on repeating if extra row or column is mentioned
15.	NewVar = var.flatten(order = “x”)	-> Flatten - Converts the multi dimension array into 1D array
The order may be     
•	C -> Row Major (Vertical)
•	F -> Column Major (Horizontal)
•	K -> Order of element
•	C is default
16.	NewVar = np.ravel(var, order)	-> Ravel - Does the same as flatten but with different syntax
Swapping Rows and Column
1.	Swapping Rows (1st with 2nd)	-> var[[R2, R1],:] Ex - a[[1,0],:]
2.	Swapping Column (3rd with 1st)	-> var[:,[C3, C2, C1]] Ex - a[:,[-1,1,0]]

Reversing Columns and Rows
1.	Reverse Columns	-> var[:, ::-1]
2.	Reverse Rows		-> var[::-1,:]

Filtering/Extracting and conditional extraction
1.	Extracting Odd numbers form an array(Display the True False)	-> print(var%2!=0)
2.	Extracting Odd numbers form an array(Filter the values)	-> var[var%2!=0]
3.	Replacing values based on condition in source itself (Replacing Odd numbers form an array with 3) - var[var%2!=0]=3
4.	Replacing values based on condition without modifying source (Replacing Odd numbers form an array with 3) ->  NewVar = np.where(var%2!=0,'odd',var)

Unique Function
1.	NewVar = np.unique(var)	-> Gives unique value
2.	NewVar = np.unique(var, return_index=True, return_counts=True)	-> Returns index value and count of each unique item


Stack and Split function
Stack - Stack joins the array.
1.	NewVar = np.stack([var1], axis=1)	-> Transposes the array only for 1D array.
2.	NewVar = np.stack([var1, var2], axis=0/1)		-> Stack joins the array one below another/next to another based the axis value 0 or 1 for multi dimension array.
Note  - Stack transposes the array, by mentioning axis as 1 and joins the array.
3.	NewVar = np.hstack([var1, var2])	-> Stacks array one next to another
4.	NewVar = np.vstack([a1, a2])		-> Stacks array one below another
5.	NewVar = np.dstack([a1, a2])		-> Transposes array and stacks array one next to another (same as stack with axis as 1)

Split - splits into equal division.
1.	Var = np.split(vari,split_number)		-> Splits the array one next to another
2.	Var = np.hsplit(var, number_of_splits)	-> Splits array horizontally
3.	Var = np.vsplit(var, number_of_splits)	-> Splits array Vertically (Note here the number of splits should be within the number of rows in the array)
4.	Var = np.array_split(var,split_number,axis=0/1)	-> split into any number of splits.
•	Axis can be applied only to multi dimension array
•	by giving axis as 1 we can split horizontally
•	by default the splitting is done vertically
•	Uneven split will create empty array

Conversion of Data Type
1.	Mentioning dtype fullname at the creation of array -> Var = np.array(a, dtype="float32")
can be int/int32.., float/float54.., complex….
2.	Mentioning dtype shortform at the creation of array -> Var = np.array(a, dtype="f")
Can be i=integer, f=float, b=boolean, u=unsigned integer, c=complex, s=string, O=object, U=unicode String
3.	Using NewVar = np.datatype(var) 
Datatype can be int/int32.., float/float54.., complex
4.	Using Var.astype(datatype)

Broadcasting – Performs the arithmetic operation on the multi dimension array with the single value/single D array
    Note - For brodcasting any of the rule must satisfy
    1. Both array should be of equal shape
    2. One of them should be having dimension as 1 (Either Row or Column)

Indexing, Slicing and Extrzcting
Indexing
1D/2D Array
1.	Positive Indexing(3rd element of 1st row)	-> var[R, C] Ex - var[0,2])
2.	Negative Indexing(last but one element of 2nd row	-> var[R, C] Ex - var[1,-2]
Multi dimension Array – Her the array is 4D each dimension represent 0 one row only
1.	Second Row of 4 dimension array	-> var[Ra, Rb, Cc] Ex - var[0,0,1]
2.	2nd element of 1st Row of 4 dimension array:	-> var[Ra, Rb, Rc, Cd] Ex - var[0,0,0,1])

Slicing
1D/2D Array
1.	2nd Row last 3 elements (excluding 1st element):	-> var[R, Start:] Ex - a[1,1:] 
2.	Skip the elements:"	-> var[R, ::Step] Ex - a[1,::2]
Multi dimension Array – Her the array is 4D each dimension represents 0 one row only
1.	2 elements of Second Row of 4 dimension array:"	-> var[Ra, Rb, Rc, Start:End] Ex - b[0,0,1,2:4])
2.	3rd element and 4th element of 1st Row of 4 dimension array:"	-> var[Ra, Rb, Rc, Start:End] Ex - b[0,0,0,2:4])

Extracting
1.	Extracting Row (1st Row)	-> var[Rnumber] Ex - a[0]
2.	Extracting multiple Rows (1st and 3rd Row)	-> var[[R1, R3],:] Ex - a[[0,2],:]
3.	Extracting Column (2nd Column)	-> var[,:[C2]] Ex - a[:,2]
4.	Extracting Multiple Columns (2nd and 3rd Column)	-> var[,:[C2, C3]] Ex - a[:,[1,2]]
5.	Extracting Required column and row from array
a.	Accessing 1st and 3rd row of last two columns	-> var[[R1, R3],Col_Start:Col_End] or var[Row_Start:Row_End, Col_Start: Col_End] Ex - a[[0,2],3:5] or a[0:2,3:5]
b.	Accessing from 2nd and 3rd column	-> var[Row_Start:Row_End,[C2, C3]] Ex - a[0:2,[1,2]]


Arithmetic operation – Works both on 1D and multi Dimension array.
1.	a+b -> np.add(a,b)
2.	a-b -> np.subtract(a,b)
3.	a*b -> np.multiply(a,b)
4.	a/b -> np.divide(a,b)
5.	a%b -> np.mod(a,b)
6.	a**b -> np.power(a,b)
7.	1/a -> np.reciprocal(a)

Statistical Operation
1D Array functions
1.	NewVar = np.max(Var)         
2.	NewVar = np.min(Var)
3.	NewVar = np.argmax(Var)/np.argmin(Var) -> gives the position of the max/min value of an array.
4.	NewVar = np.sqrt(Var)
5.	NewVar = np.sin(Var)
6.	NewVar = np.cos(Var)
7.	NewVar = np.cumsum(Var) adds the previous value
8.	NewVar = np.cumprod(Var) multiplies the previous value

Multi D Array functions
same for multi dimension array wecan also add is axis=0/1 for column wise or rowwise calculation.  
works only on min, max, cumsum, cumprod, argmax, argmin functions
Ex - np.max(x, axis=0/1)

1.	NewVar = np.max(Var axis=0/1)         
2.	NewVar = np.min(Var axis=0/1)
3.	NewVar = np.argmax(Var axis=0/1)/np.argmin(Var axis=0/1) -> gives the position of the max/min value of an array.
4.	NewVar = np.sqrt(Var)
5.	NewVar = np.sin(Var)
6.	NewVar = np.cos(Var)
7.	NewVar = np.cumsum(Var axis=0/1) adds the previous value
8.	NewVar = np.cumprod(Var axis=0/1) multiplies the previous value

Insert, Append and Delete - Adds/inserts/deletes the value into array
	Insert – Adds at specified index position.
1.	NewVar = np.insert(var, index_position, new_value) 	-> 1D or Multi-D Array (to insert one next to another - horizontally)
2.	NewVar = np.insert(var, index_position, [new_value], axis=0) 	-> Multi-D Array (to insert below - vertically)

Append – Adds at the end of array.
1.	NewVar = np.append(var, new_value) 	-> 1D or Multi-D Array (to insert one next to another - horizontally)
2.	NewVar = np.append(var, [new_value], axis=0) -> Multi-D Array (to insert below - vertically)

Delete – Deletes the values from the mentioned index position.
1.	NewVar = np.delete(var, index_position) -> 1D or Multi-D Array (to delete one next to another - horizontally amd flaten array)
2.	NewVar = np.delete(var, index, axis=0/1) -> Deletes the row or column accordingly based on axis value 0 or 1
Note – If axis is not mentioned for multi dimension array it deletes value and converts the multi dimension array to 1D array

Difference b/w Array and Matrix
•	Array does the multiplication with respect to position, where has matrix has its rule (m X n) (n X z) 
•	the column from one matrix should be the same size of row of another matrix

1.	Creating the matrix
Var = np.matrix([[5,7],[2,8],[1,9]])
2.	Transpose - Transposes the matrix.
There are 3 syntax which any one of them can be used.
    NewVar = var.transpose()
    or
    NewVar = np.transpose(var)
    or
    NewVar = var.T
3.	Swapaxes - Swaps the axis of the matrix Row to collum(0,1) or column to row(1,0)
There are two syntax where any one of them can be used.
    NewVar = var.swapaxes(Current_Axis, Required_Axis)
    or
    NewVar = np.swapaxes(var, Current_Axis, Required_Axis)  
4.	Inverse - Inverses the matrix.
NewVar = np.linalg.inv(var))
Note - only works on square matrix i.e. (R X C), R==C
5.	Power - multiplies the matrix the number of times mentioned with itself.
NewVar = np.linalg.matrix_power(var,n)
Note - only works on square matrix i.e. (R X C), R==C
    Different operation will happen based on the value passed to n
        n = 0 -> Identity Matrix
        n > 0 -> Multiplies itself with that many times
        n < 0 -> Inverses and Multiplies itself
6.	Determinant - performs determinant function on matrix
NewVar = np.linalg.det(var)
Note - only works on square matrix i.e. (R X C), R==C