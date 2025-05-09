Problem Question:
Given an array of both positive and negative integers, the task is to compute sum of minimum and maximum elements of all sub-array of size k.

Examples: 

Input : arr[] = {2, 5, -1, 7, -3, -1, -2}  
        K = 4
Output : 18
Explanation : Subarrays of size 4 are : 
     {2, 5, -1, 7},   min + max = -1 + 7 = 6
     {5, -1, 7, -3},  min + max = -3 + 7 = 4      
     {-1, 7, -3, -1}, min + max = -3 + 7 = 4
     {7, -3, -1, -2}, min + max = -3 + 7 = 4   
     
     Missing sub arrays - 
     
     {2, -1, 7, -3}
     {2, 7, -3, -1}
     {2, -3, -1, -2}
     {5, 7, -3, -1}
     {5, -3, -1, -2}
     and few more -- why these were not considered??
     Considering missing arrays result coming as 27
     
     Sum of all min & max = 6 + 4 + 4 + 4 = 18

 Naive Approach:
Run two loops to generate all subarrays and then choose all subarrays of size k and find maximum and minimum values.
Finally, return the sum of all maximum and minimum elements.

Our Approach:
The idea is to use Dequeue data structure and sliding window concept. We create two empty double-ended queues of size k (‘S’ , ‘G’) 
that only store indices of elements of current window that are not useless. An element is useless if it can not be maximum or minimum of next subarrays. 
