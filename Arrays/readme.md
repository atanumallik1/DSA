<!-- vscode-markdown-toc -->
* 1. [Check Duplicates](#CheckDuplicates)
	* 1.1. [Problem](#Problem)
	* 1.2. [Solusion](#Solusion)
* 2. [Find Minimum and Maximum of an Array](#FindMinimumandMaximumofanArray)
	* 2.1. [Solusion](#Solusion-1)
* 3. [Minimum number of deletion to Remove the Max and Min element](#MinimumnumberofdeletiontoRemovetheMaxandMinelement)
	* 3.1. [Problem](#Problem-1)
	* 3.2. [Solusion](#Solusion-1)
* 4. [Cyclically rotate an array by K positions](#CyclicallyrotateanarraybyKpositions)
	* 4.1. [Solusion](#Solusion-1)
* 5. [Find Missing Number in an Unsorted Integer Array](#FindMissingNumberinanUnsortedIntegerArray)
	* 5.1. [Problem](#Problem-1)
	* 5.2. [Solusion](#Solusion-1)
* 6. [Find Intersection of 2 Arrays](#FindIntersectionof2Arrays)
	* 6.1. [Problem](#Problem-1)
	* 6.2. [Solusion](#Solusion-1)
* 7. [Find Peak](#FindPeak)
* 8. [Max Sum Subarray (Kadane)](#MaxSumSubarrayKadane)
* 9. [Subarray Sum Equals K](#SubarraySumEqualsK)
	* 9.1. [Problem](#Problem-1)
	* 9.2. [Solusion](#Solusion-1)
* 10. [Continuous Sum Subarray](#ContinuousSumSubarray)
* 11. [K subarrays of Equal Sums](#KsubarraysofEqualSums)
* 12. [Is array divisible in 2 euqal sum subarrays / Partition Equal Subset Sum](#Isarraydivisiblein2euqalsumsubarraysPartitionEqualSubsetSum)
	* 12.1. [Problem](#Problem-1)
	* 12.2. [Solusion](#Solusion-1)
* 13. [Best Time to Buy and Sell Stock](#BestTimetoBuyandSellStock)
	* 13.1. [Problem](#Problem-1)
	* 13.2. [Solusion](#Solusion-1)
* 14. [Best Time to Buy and Sell Stock 2](#BestTimetoBuyandSellStock2)
	* 14.1. [Solusion](#Solusion-1)
* 15. [Find Kth Largest Element](#FindKthLargestElement)
* 16. [Merge 3 sorted Arrays](#Merge3sortedArrays)
* 17. [2 Sum : Sorted Array](#Sum:SortedArray)
* 18. [3 Sum : Unsorted Array with Duplicates](#Sum:UnsortedArraywithDuplicates)
* 19. [Grouping / Dutch National Flag Problem](#GroupingDutchNationalFlagProblem)
* 20. [Rotate an Image](#RotateanImage)
* 21. [Sort Characters By Frequency](#SortCharactersByFrequency)
	* 21.1. [Problem](#Problem-1)
	* 21.2. [Solusion](#Solusion-1)
* 22. [Top K Frequent Elements](#TopKFrequentElements)

<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->
# Summary of Array Problems 



##  1. <a name='CheckDuplicates'></a>Check Duplicates
###  1.1. <a name='Problem'></a>Problem
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

###  1.2. <a name='Solusion'></a>Solusion 
1. Use a `Map`
2. Put all the elements of the Array into the `Map`
3. We can detect if there is already a duplicate

##  2. <a name='FindMinimumandMaximumofanArray'></a>Find Minimum and Maximum of an Array
###  2.1. <a name='Solusion-1'></a>Solusion 
1. Loop through all the elements in the array
2. Find `Min` and `Max`

##  3. <a name='MinimumnumberofdeletiontoRemovetheMaxandMinelement'></a>Minimum number of deletion to Remove the Max and Min element
###  3.1. <a name='Problem-1'></a>Problem 
You are given a `0`-indexed array of distinct integers `nums`.

There is an element in `nums` that has the `lowest` value and an element that has the `highest` value. We call them the minimum and maximum respectively. Your goal is to remove both these elements from the array.

A `deletion` is defined as either removing an element from the front of the array or removing an element from the back of the array.

Return the `minimum` number of deletions it would take to remove both the minimum and maximum element from the array.


###  3.2. <a name='Solusion-1'></a>Solusion 
1. First find teh index of `Max` and `Min` element in the array 
2. In the example below : `Max = 6 , MaxIndex=3 ` `Min = 0, MinIndex=4`

````
Index  0 1 2 3 4
Value  2 3 5 6 0 

````

3. We can delete in 3 possible ways 
    1.  Delete both from Left ; Total number of Deletion needed = `Max(MaxIndex,MinIndex)+1` = `5 `
    2.  Delete both from Right ; Total number of Deletion needed = `Length of Array  - Min(MaxIndex,MinIndex` = `5 - 3 ` = `2`
    3.  Delete one `closer to start` from `Left` and `One Closer` to `end` from `right` =  3 + 2 = 5
    4. Answer is Minimum of the above 3 options


##  4. <a name='CyclicallyrotateanarraybyKpositions'></a>Cyclically rotate an array by K positions
###  4.1. <a name='Solusion-1'></a>Solusion 
1. Reverse whole array
2. Reverse the First K elements 
3. Reverse the remaining elements in the array   


##  5. <a name='FindMissingNumberinanUnsortedIntegerArray'></a>Find Missing Number in an Unsorted Integer Array
###  5.1. <a name='Problem-1'></a>Problem 
Given an unsorted `integer` array nums, return the smallest missing positive integer.
You must implement an algorithm that runs in O(n) time and uses constant extra space.
The array may contain `-VE` values as well 

###  5.2. <a name='Solusion-1'></a>Solusion
1. The array might contain `-VE` , `+VE` and `0`
2. However we are interested in indentifying the missing `+VE` number 
3. We want to utilize array's Index property to acrieve this . 

````
Index      0 1 2 
Array      2 3 4

````
after Processing the array it woud look like 

````
Index      0  1   2 
Array      2 -3  -4
````

The presence of a `-VE` value at an index signifies the presence of `index+1` value 
If we consider the value at index `0` which is positive ; it means element `index+1` = `0+1` = `1` is missing element

4. Preprocessing 
    -  Loop through the array and replace all `-VE` elements with 0
    -  We choose value 0, since teh original `-VE` element is out of our solusion scope since we want only `+VE` elements 
5. Processing 
    - For a value = `X` in array ; the `index` = `X-1`; in case teh value `X` is `-VE`; we do `Math.abs(X)`; 
    - if the `Index` is within valid array index range i.e. `0 .... n-1`; 
        -  then mark the value at `arr[Index] = -1 *  arr[Index] `
        - if teh value at acell is `0`; then change it to `-INFINITY` ; since it tells teh original value at cell was `-VE` and this has no significance on teh finding logic 

6. Finding      
    - The presence of a `-VE` value at an index signifies the presence of `index+1` value 


##  6. <a name='FindIntersectionof2Arrays'></a>Find Intersection of 2 Arrays
###  6.1. <a name='Problem-1'></a>Problem 
Given two integer arrays nums1 and nums2, return an array of their intersection. Each element in the result must be `unique` and you may return the result in any order.

###  6.2. <a name='Solusion-1'></a>Solusion
- We can create 2 sets  out of 2 arrays ; the set removes the duplicates  ; since teh solusion seeks for unique elements 
- we can perform `retainAll`   to find the intersection `set1.retainAll(set2)`




##  7. <a name='FindPeak'></a>Find Peak 

1. We want to do a binary search like logic ; we evaluate if the `middle` element is a Peak using the peak condition below. If the middle elemnt is not   the peak we shift the search area toward teh side which has the larger element

2. Condition for Peak 
  - Left Condition  : ` index = 0 || a[mid] >= a[mid-1]`
  - Right Condition : `index = n-1 || a[mid] >= a[mid+1]`
  - if both conditions are met then we foudn a Peak 

3. If the element is not the Peak : move towards teh side which has big element
   ````java
             // if mid is not a peak
              // move to the side which has bigger element than mid; this is because at some point the bigger element might become the peak 
               if(a[mid + 1] > a[mid ])
                   low = mid + 1;
               else 
                   high = mid -1 ;
   ````  

##  8. <a name='MaxSumSubarrayKadane'></a>Max Sum Subarray (Kadane)  
- works on Array with `-VE`
- It says: do not carry the `currentSum` if it is `-VE`
````java
    public int maxSubArray(int[] nums) {
        
        // Accumulator variable 
        int maxSum = Integer.MIN_VALUE;
        int currntSum = 0 ; 
    
        
        for( int i = 0 ;i < nums.length ; i++){
            // No need to carry forward if the current sum is negative
            if(currntSum < 0)
               currntSum = 0;
            
            currntSum = currntSum + nums[i];
            maxSum = Math.max(maxSum ,currntSum );
        }
        
        
        return maxSum;
        
    }
````

##  9. <a name='SubarraySumEqualsK'></a>Subarray Sum Equals K
###  9.1. <a name='Problem-1'></a>Problem
Given an array of integers nums and an integer k, return the total number of subarrays whose sum equals to k. A subarray is a contiguous non-empty sequence of elements within an array.

###  9.2. <a name='Solusion-1'></a>Solusion
- This needs to be soleved using `PrefixSum`
- We need to count the occurrence of `Prefix Sum`
- We need a `Map` to tell us the cout of coourrence so far
- Refer to [Subarray Sum Equals K
](https://github.com/atanumallik1/Project/blob/main/DSA/Dynamic%20Programming/14.Subarray%20Sum%20Equals%20K.md)


##  10. <a name='ContinuousSumSubarray'></a>Continuous Sum Subarray 

INCOMPLETE

##  11. <a name='KsubarraysofEqualSums'></a>K subarrays of Equal Sums 
- Back tracking Problem

##  12. <a name='Isarraydivisiblein2euqalsumsubarraysPartitionEqualSubsetSum'></a>Is array divisible in 2 euqal sum subarrays / Partition Equal Subset Sum
###  12.1. <a name='Problem-1'></a>Problem 
Given a non-empty array nums containing only positive integers, find if the array can be partitioned into two subsets such that the sum of elements in both subsets is equal.

###  12.2. <a name='Solusion-1'></a>Solusion
- We use a `Set` to store all possible sums 
- the approach to find teh set is a bit complicated     ; Refer to https://github.com/atanumallik1/Project/blob/main/DSA/Arrays/7.2.DivideIn2PartsOfEqualSum.md 
- If teh Set contains the expected sum whihc is `total of elements/ 2` then we are good


##  13. <a name='BestTimetoBuyandSellStock'></a>Best Time to Buy and Sell Stock
###  13.1. <a name='Problem-1'></a>Problem 
You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

###  13.2. <a name='Solusion-1'></a>Solusion
- We start from the end of teh array 
- We track teh max selling price possible 
- then we calculate the profit per day


##  14. <a name='BestTimetoBuyandSellStock2'></a>Best Time to Buy and Sell Stock 2
###  14.1. <a name='Solusion-1'></a>Solusion
- loop from 1st element in array 
- if there is a price increase from `i-1` index then consider and add it in profit 


##  15. <a name='FindKthLargestElement'></a>Find Kth Largest Element 
- Need a `min` heap of size `K`
- Add all elements one by 1
- if the size is `K` then delete an element and add an element 
- after all elements are added ; top element in the heap is kth Largest


##  16. <a name='Merge3sortedArrays'></a>Merge 3 sorted Arrays

- We put a pointer at the beginning of eeach arrays
- We add the smallest in the final list and add its pointer 

##  17. <a name='Sum:SortedArray'></a>2 Sum : Sorted Array 

- We take 2 Pointer Approach ; note that the array is already **sorted** 
- at the beginning : `P1` points to `index 0` and `P2` points to `Index 1`
- Calculate Sum = `arr[P1] + arr[p2]`
- If the Sum exceeds expectation , we forward the `Right pointer`
- If the Sum is lesser than expectation , we forward the `Left pointer`


##  18. <a name='Sum:UnsortedArraywithDuplicates'></a>3 Sum : Unsorted Array with Duplicates
- https://github.com/atanumallik1/Project/blob/main/DSA/Arrays/12.1.3Sum.md 
- We sort the array 
- the main loop rund from `i =0` to `i= n-3` ; since we need at 3 elements
- we use 2 sum approach
- for duplicate values for `a` : we ignore the value in parent loop
- for duplicate values for `b` and `c` : we fast forward

##  19. <a name='GroupingDutchNationalFlagProblem'></a>Grouping / Dutch National Flag Problem 
- We need 3 pointers ; `Left,Right,Current`
- loop `Current < Right`
  - if (arr[current] == 0)
     - swap(current,low)
     - low++
     - current++
  - if (arr[current] == 1)
     - current++

  - if (arr[current] == 2)
    - Swap (current, Right)
    - Right ++ 
    - in this cas we do not increment current; since current gets a new element which will beprocessed in next iteration

##  20. <a name='RotateanImage'></a>Rotate an Image
 - Create Transpose 
 - Reverse each row     

##  21. <a name='SortCharactersByFrequency'></a>Sort Characters By Frequency
###  21.1. <a name='Problem-1'></a>Problem 
Given a string s, sort it in decreasing order based on the frequency of the characters. The frequency of a character is the number of times it appears in the string.

Return the sorted string. If there are multiple answers, return any of them.

Example 1:
````
Input: s = "tree"
Output: "eert"
Explanation: 'e' appears twice while 'r' and 't' both appear once.
So 'e' must appear before both 'r' and 't'. Therefore "eetr" is also a valid answer.
````

###  21.2. <a name='Solusion-1'></a>Solusion
- We create a Map where we capture the frequency of each characters 
  - For `tree` the map will be like 
    ````
     e 2
     t 1
     r 1
    ````
- We create an  array of `Set<Character>` of size `length of String +1 `
    - the length has one extra character, since we want to operate from index 1 to get benefit 
- Map the frequencies to index     
      ````
      0     1     2    3   4   5
     ---------------------------
     |   | t,r | e |    |    |   |
     ---------------------------
      ````
- now we iterate from last and build the string       


##  22. <a name='TopKFrequentElements'></a>Top K Frequent Elements
- We can use the approach of teh preious section which will be simple since it does not require any sorting
- we can alternatively use aPriorityQueue /HEap ; but seletion from HEap is O(logn)
- details [here](https://github.com/atanumallik1/Project/blob/main/DSA/Arrays/18.TopKFreqElement.md)