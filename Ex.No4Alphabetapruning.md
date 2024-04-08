# Ex.No: 4   Implementation of Alpha Beta Pruning 
### DATE:23/03/24                                                                          
### REGISTER NUMBER : 212221040125
### AIM: 
Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.
### Steps:
1. Start the program
2. Initially  assign MAX and MIN value as 1000 and -1000.
3.  Define the minimax function  using alpha beta pruning
4.  If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
5.  In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
6.  In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
7.  Specify the score value of leaf nodes and Call the minimax function.
8.  Print the best value of Max player.
9.  Stop the program. 

### Program:
```
MAX, MIN 
= 
1000, -1000 
def minimax(depth, nodeIndex, maximizingPlayer, 
values, alpha, beta): 
if depth 
== 3: 
return values [nodeIndex] 
if maximizingPlayer: 
best = MIN 
for i in range(0, 2): 
val = minimax(depth + 1, nodeIndex * 2 + i, 
False, values, alpha, beta) 
best = max(best, val) 
alpha = max(alpha, best) 
if beta <= alpha: 
break 
return best 
else: 
best = MAX 
for i in range(0, 2): 
val = minimax (depth + 1, nodeIndex * 2 + i, 
True, values, alpha, beta) 
best = min(best, val) 
beta 
= 
min(beta, best) 
if beta <= alpha: 
break 
return best 
values = [3, 5, 6, 9, 1, 2, 0, -1] 
print("The optimal value is :", minimax(0, 0, True, values, MIN, MAX)) 
```
### Output:
![Screenshot 2024-04-08 100829](https://github.com/pragalyaashree/AI_Lab_2023-24/assets/128135934/1cca02fe-7e89-474b-88b1-e73c0d215d01)

### Result:
Thus the best score of max player was found using Alpha Beta Pruning.
