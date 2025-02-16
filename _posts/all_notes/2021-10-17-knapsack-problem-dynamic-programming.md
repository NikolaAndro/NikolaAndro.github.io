---
layout: post
title:  "0/1 Knapsack Problem - Dynamic Programming"
date:   2021-10-17 09:29:20 +0700
categories: post
---

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
TO DO: explain filling the table and explain how code works

# Problem:

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Given weights and values of n items, put these items in a knapsack of capacity W to get the maximum total value in the knapsack. In other words, given two integer arrays val[0..n-1] and wt[0..n-1] which represent values and weights associated with n items respectively. Also given an integer W which represents knapsack capacity, find out the maximum value subset of val[] such that sum of the weights of this subset is smaller than or equal to W. You cannot break an item, either pick the complete item or don’t pick it (0-1 property).
 

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 This problem can be solved using bottom-up dynamic programming approach. The code for this approach looks as following:
 
{% highlight ruby %}

def knapSack(W, weight, val, n):
    # Making the final_row array to keep results as in table when doing by hand
    final_row = [0 for i in range(W+1)]  
 
    # for each row in the table, compute the calculations 
    # or --> for each element in that is being put in the bag
    for i in range(1, n+1): 
        print("\nLooking at the element", i, "with value of", val[i-1], 'and weight of', weight[i-1])
        
        # starting from back,so that we also have data of
        # previous computation when taking i-1 items
        for w in range(W, 0, -1):  
                                
            # Comparing until the index represented by row and column in the table.
            if weight[i-1] <= w:
                # finding the maximum value
                print("pick btw ",final_row[w], " and ",final_row[w-weight[i-1]]+val[i-1])
                final_row[w] = max(final_row[w], final_row[w-weight[i-1]]+val[i-1])
            else:
                break
            print(final_row)
    # returning the maximum value of knapsack
    return final_row[W]  
    
# Driver code
val = [4,13,10,5]
weight = [2,6,4,3]
W = 9
n = len(val)
# This code is contributed by Suyash Saxena
print('\n\nMaximum value this knapsack is ',knapSack(W, weight, val, n),'.')
  
{% endhighlight %}
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Instead of creating a 2d array for the table as if this problem was done by hand, we are creating final_row array that will be updated and at some point look exactly like each one of the rows when the table is constructed by hand. 
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 We approach this problem by first considering the first element and its weight. In the code above, the 1<sup>st</sup> element has the weight of 2. Hence, we will start filling the table from the back of the row/array until we meet the index 2. 
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 The way we fill this table is that we compare the `current value` in the row with `new possible value`, which is a combination of the element i that we are looking at + another element whose weight when added up to the weight of the element i, satisfies the capacity propery => weight of element i + weight of some other element <= W (capacity).
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 If we take a look at final first row of the table done by hand, we can see that the row looks like this:
 
 {% highlight ruby %}
 [0,0,4,4,4,4,4,4,4,4]
 {%endhighlight%}
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 We filled this row by comparing the current value in the row with new possible value until we hit index 2. They are all 4 because in the bag that has weight capacity *i* (which is 2 in this case), the best result for such capacity will be at index 2. Those are the optimal values for capacity i in that moment.
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Another example is the last row where we again start from the back and we have the following elements to compare:
 
 current value in this index/capacity: 17
 
 new possible value at this index/capacity => make a combination of the weight of the element we are looking at (in this case element value is 5 and weiht is 3) with another element (w - weight of this element (3) => 6). We have already computed the optimal vaue for the capacity 6 and saved it in our final array. Hence, we use it in this combination. 5 + 14 = 19
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 We save the greater value in the table and move on down the array until we meet the given weight index (in this case of the last row that index is 3).
 
 *Variation of this problem would be fractional knapsack prblem!*
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 The Squid

 
