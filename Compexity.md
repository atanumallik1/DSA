# Complexity

Complexity analysis is teh mechanism to analyze the behaviour in Runtime of an application based on input size `n`

We discuss about worst case scenario

- in big `o` notation we consider only the larget term. If something takes `n + nlog n`, then we call it `O(nlogn)` ( we discard the n ) 

- O(1)
- O(log(n))
- O(sqrt(n))
- O(n)


- O(nlog(n))
- O(n^2)
- O(n^3)
- O(n!)

<img width="723" alt="image" src="https://user-images.githubusercontent.com/8110582/194998658-911b2df1-f67d-443b-9319-001b83a32c6b.png">


###  O(1)
  - runtime is constant irrespective of input size 
  - best algotithms 
  - Examples:
    - accessing array elements by index 
    - accessing an element from hahs map

### O(n)
   - linear time algo 
   - time grows linearly with input size 
   - example :
     - calculate sum of ala elements in a an array 
     - insert / remove at the middle of an array 
     - search in an array
     - __heapify__ algotithm
       - if we build a heap from scratch it is of `o(n)`; but if you insert an element in an heap it is `o(log (n))`
     - monotonic stack is of `o(n)`
       - example:   water logging ; maximum tempareture 

### O(n ^2)
   - example
     - matrix addition ( `O(n*m)`)
     - bubble sort  
     - insertion sort

### O(n ^3)    
    - examples
      - 3 nested loops 
        - you have an array , find every triplet  


###  O(log(n))     
    - in every iteration we reduce the data size by half
      - we can ask , given an array of size `n` ; how many times can we divide it by half untill the result is 1
     - ````
        Howmany times can we divide teh array until we get the result 1
         n/2 --> 1
       ```` 
      - another way of asking : how mant time ne need to multiply 1 by 2 so that we get the value `n`
        -  ````
            1 * 2 --> n
           ```` 
      - in both cases the answer is `log(n)`    ( assuming the base is 2) 
    - for very big input size n (n is in billions) the value of `log(n) ~ 32` which is very small. It is more efficient than `o(n)`
    - examples
      - binary search in anarray 
      - binary search tree 
      - ann or remove an element in a heap    

### n log n

 - when we do work with complexity (log n), `n` times
 - examples
   - heap sort 

 - implecation of constants 
   - `n + n log n ` --> `O(logn)` , since  `nlogn > n`
   - `m + n log n ` --> `O(m + logn)` , since  we do not know how big or small `m` is; if `m` is very small then we can ignore `m` 


### O(2 ^n)
- example
   - 2 branch recursion  : in this case we shall have a recusrsion tree of height `n` but we shall have 2 branches always
   - find all combinations of n numbers

### O(C ^ n)
- example
   - `C` branch recursion  : in this case we shall have a recusrsion tree of height `n` but we shall have `C` branches always
   - recursion with arbitrary number of branches
   - find number of islands ( in graph algo)      
