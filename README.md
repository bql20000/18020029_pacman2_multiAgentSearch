# Pacman Project 2: Multi-agent search

Source project link: http://ai.berkeley.edu/multiagent.html <br />
Name: Bui Quang Long <br />
MSSV: 18020029 <br />

## Overall results: 25/25

### Question 1 (4/4): Reflex Agent
First, I make sure the distance between Pacman and the closest ghost always < 2, by returning a -INF value when the condition is not satisfied. <br />
Second, I add to the score the inverted of the distance to the closest food, which means the action getting closer to the closest food is encourged. <br />
Third, I add a small random number to prevent Pacman from being into unwanted long loop. <br />
Overall, my evaluation function is <br />
successorGameState.getScore() + 10 / closest_food_distance + random.random()

### Question 2 (5/5): Minimax Search
First I get all legalActions from the current game state, then try to apply minimax search for each actions. The chosen action will have the highest score.

### Question 3 (5/5): Alpha Beta Search
Similar to minimax search

### Question 4 (5/5): Expectimax Search
Similar to minimax search, but the minimax search function return the average score instead of min score if the current agent is not Pacman. Thus the ghosts in this section play less optimized and more randomly.

### Question 5 (6/6): Evaluation function
I try I apply the similiar function from question 1, but it seems to be insufficient. (only 5/6 points, with around 950 score in average)
Then I add to the function sum of the scared time of ghosts, which means now Pacman is encouraged to eat the big food and eat the ghost is possible. This improvement significantly increase the score. (6/6 points, 1200 score in average)

