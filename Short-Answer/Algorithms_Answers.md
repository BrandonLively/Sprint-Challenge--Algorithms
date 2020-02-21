#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a)
O(N^2) because the loop is going over n^3 while the operation inside the loop is squaring n, which means it'll only loop n^2 times. 

b)
O(N) - the second for loop is exponential growth, which as the program scales it'll have an ever increasing diminishing effect which makes it moot compared to the linear growth of the first for loop.

c)
O(N) - Since the recursion will pop only after it's completed, the 2 part doesn't matter, the recursion will still only run one time per bunnyEars passed in. which is O(N)
## Exercise II


Sounds like we just need to figure out the value of F, and eggs are our indicator, so a binary search would be best suited here, start at floor 0 and increase if egg doesn't break then set that is the minLimit, increase the floor exponentially until it breaks, then perform binary search between the two floors until a result is reached.

def findTheFloor():
    minLimit = 0
    maxLimit = float('inf') 
    currentFloor = 2
    result = 0
    
    if dropEggBreaks(0):
        return 0
    if dropEggBreaks(1):
        return 1
    
    while(maxLimit == float('inf')):
        if dropEggBreaks(currentFloor) == False:
                minLimit = currentFloor
                currentFloor *= currentFloor
        else
            maxLimit = currentFloor
     
    while result == 0:
        if(maxLimit - minLimit == 1):
            result = maxLimit
        currentFloor = maxLimit - minLimit //2
        if dropEggBreaks(currentFloor) == false:
            minLimit = currentFloor
        else:
            maxLimit = currentFloor
            
    return result
    
    
    The Time complexity is O(1) since we're doing binary search the size of n doesn't significantly effect the number of operations as n scales.