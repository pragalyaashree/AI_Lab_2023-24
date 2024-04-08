# Ex.No: 11  Planning –  Block World Problem 
### DATE: 01/04/2024                                                                        
### REGISTER NUMBER : 212221040125
### AIM: 
To find the sequence of plan for Block word problem using PDDL  
###  Algorithm:
Step 1 :  Start the program <br>
Step 2 : Create a domain for Block world Problem <br>
Step 3 :  Create a domain by specifying predicates clear, on table, on, arm-empty, holding. <br>
Step 4 : Specify the actions pickup, putdown, stack and un-stack in Block world problem <br>
Step 5 :  In pickup action, Robot arm pick the block on table. Precondition is Block is on table and no other block on specified block and arm-hand empty.<br>
Step 6:  In putdown action, Robot arm place the block on table. Precondition is robot-arm holding the block.<br>
Step 7 : In un-stack action, Robot arm pick the block on some block. Precondition is Block is on another block and no other block on specified block and arm-hand empty.<br>
Step 8 : In stack action, Robot arm place the block on under block. Precondition is Block holded by robot arm and no other block on under block.<br>
Step 9 : Define a problem for block world problem.<br> 
Step 10 : Obtain the plan for given problem.<br> 
     
### Program:
```
(define (domain blocksworld).
(:requirements :strips :equality)
(:predicates (clear ?x)
(on-table ?x)
(arm-empty)
(holding 7x)
(on ?x ?y))
(:action pickup
:parameters (?ob)
:precondition (and (clear Pob) (on-table ?ob) (arm-empty))
:effect (and (holding ?ob) (not (clear Pob)) (not (on-table ?ob))
(not (arm-empty))))
(:action putdown
:parameters (?ob)
:precondition (and (holding ?ob))
:effect (and (clear Pob) (arm-empty) (on-table ?ob)
(not (holding ?ob)) ))
(:action stack
:parameters (?ob ?underob)
:precondition (and (clear Punderob) (holding ?ob))
:effect (and (arm-empty) (clear Pob) (on Pob ?underob)
(not (clear Punderob)) (not (holding ? ob))))
(:action unstack
:parameters (?ob Punderob)
:precondition (and (on Pob Punderob) (clear Pob) (arm-empty))
:effect (and (holding Pob) (clear ?underob) (not (on ?ob Punderob)) (not (clear
(not (arm-empty)))))
```
### Input 
```
(define (problem pb1)
(:domain blocksworld)
(:objects a b)
(:init (on-table a) (on-table b) (clear a) (clear b) (arm-empty))
(:goal (and (on a b))))
```

### Output/Plan:
![Screenshot 2024-04-08 152338](https://github.com/pragalyaashree/AI_Lab_2023-24/assets/128135934/e6a3b47f-25c6-4994-b34d-abed55a68e67)

### Result:
Thus the plan was found for the initial and goal state of block world problem.
