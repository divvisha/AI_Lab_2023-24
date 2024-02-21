# Ex.No: 3  Implementation of Minimax Search
### DATE: 21/02/2024                                                                            
### REGISTER NUMBER : 212221040044

### AIM: 
Write a mini-max search algorithm to find the optimal value of MAX Player from the given graph.

### Algorithm:
1. Start the program
2. import the math package
3. Specify the score value of leaf nodes and find the depth of binary tree from leaf nodes.
4. Define the minimax function
5. If maximum depth is reached then get the score value of leaf node.
6. Max player find the maximum value by calling the minmax function recursively.
7. Min player find the minimum value by calling the minmax function recursively.
8. Call the minimax function  and print the optimum value of Max player.
9. Stop the program. 

### Program:

~~~
MAX, MIN = 1000, -1000
def minimax(depth, nodeIndex, maximizingPlayer,
            values, alpha, beta):
    if depth == 3:
        return values[nodeIndex]
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
          
            val = minimax(depth + 1, nodeIndex * 2 + i,
                            True, values, alpha, beta)
            best = min(best, val)
            beta = min(beta, best)
            if beta <= alpha:
                break
        return best
values = [3, 5, 6, 9, 1, 2, 0, -1] 
print("The optimal value is :", minimax(0, 0, True, values, MIN, MAX))

~~~

### Output:

<img width="741" alt="Screenshot 2024-02-21 142507" src="https://github.com/DrUmaRaniV/AI_Lab_2023-24/assets/127508123/2068e1b1-7f1a-467d-904b-7150f865c14b">



### Result:
Thus the optimum value of max player was found using minimax search.
