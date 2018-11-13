# hill-climbing-algorithm

Description of N-Queens Formulation: 
The n – queens problem involves placing n queens on a n * n chessboard, such that no two queens would threaten each other. Thereby, no two queens should share the same column, row or diagonal. 

Hill-Climbing Searching Technique: 
Hill-Climbing search involves looking for the goal state locally without keeping track of states except for the immediate neighbouring ones. Its an iterative algorithm that starts with a random state and attempts to reach the goal state by incrementing its situation one at a time. Neighbouring state’s heuristic is formed based on evaluation function, and decision to traverse to that neighbour is made based on which hill-climbing variant is being implemented. 

Program Structure: 
Language Used: Java 8.0 
1. Run the NQueensProblem java class file which contains starting point of execution for the program. 
2. User will be prompted to enter the size of chess board, upon which all three variants of hill climbing will be triggered one by one 3. Steepest ascent hill climbing: 
  a. Chess board with random queen positions is generated. Upon calculating its threat level, a heuristic board is generated for the
  entire board.  
  b. A new queen position is randomly selected from list of minimum threat levels in heuristic board 
  c. These steps are repeated until the chess board has reached zero threat count or if all the threat counts in heuristic board are
  more than or equal to current threat count d. For the sake of generating average performance, this entire process is repeated 500
  times and we obtain success and failure rates along with average steps required to reach goal state as well as fail state.
  
4. Hill Climbing With Sideways Moves: 
  a. Chess board with random queen positions is generated. Upon calculating its threat level, a heuristic board is generated for the
  entire board.  
  b. A new queen position is randomly selected from list of minimum threat levels in heuristic board 
  c. These steps are repeated until the chess board has reached zero threat count or if all the threat counts in heuristic board are
  more than current threat count 
  d. The algorithm continues for same level of heuristic up to an arbitrary limit(say 100) with the hope of getting better heuristic
  values eventually. Hence this algorithm deals with plateau terrain in search terminologies.  
  e. For the sake of generating average performance, this entire process is repeated 500 times and we obtain success and failure rates
  along with average steps required to reach goal state as well as fail state. 
  
5. Random Restart Hill Climbing With and Without Sideways moves: 
  a. For Random Restart Without Sideways moves, the steepest ascent variant is called on a loop until a goal state has been found. 
  b. For Random Restart With Sideways moves, the Hill Climbing with sideways moves variant is called on a loop until a goal state has
  been found. 
  c.  Here we repeatedly restart the algorithm by generating new chess board states on failure.  
  d. Performance is measured by listing out average number of restarts required along with average number of states per round
  
NQueensProblem.java (main class) 
Methods: 
  1. main(): Th starting point of program which accepts input of ‘n’ from user and in turn calls all the three hill-climbing search
  variants. 
  2. steepestAscentHillClimbingMain(): Private method to initiate steepest ascent hill climbing and repeat iterations 500 times to show
  average success, failure rate along with step count and few sequence paths 
  3.  hillClimbingWithSidewaysMoveMain(): Private method to initiate hill climbing with sideways moves and repeat iterations 500 times
  to show average success, failure rate along with step count and few sequence paths 
  4. randomRestartHillClimbing(): Private method to to initiate random restart hill climbing with both the variations of with and
  without sideways moves (based on boolean parameter's value). It will run until a goal state is found. 
  5. steepestAscentHillClimbing(): Private Method for Steepest Ascent Hill Climbing, in which neighbouring states with better heuristic
  are only traversed 
  6. hillClimbingWithSidewaysMove(): Private method for Hill Climbing with sideways move, in which neighbouring states with similar
  heuristic (plateau) are also traversed upto a limit 
  7. calculatePotentialMoves(): Generic method for calculating heuristic board with respect to current chess board state 
  8. traverseToNeighbor(): Private method for moving queen's position to one of the chosen heuristic states 
  9. calculateHeuristic(): Generic method to calculate threat count based on positions of other queens in same diagonal, row or column
  10. printChessboard(): Utility method for printing chess board state with queen positions as array as well as matrix 
  11. isArrayEqual(): Utility method for checking duplicate chessboard states 
  12. generateChessBoard(): Utility method for generating randomized chess board state of n*n board size 
 
ChessboardState.java (POJO class) 
Variables:  
  1. goalReached : A Boolean variable to keep track of goal state 
  2. noOfTries: A counter variable for recording number of increments performed from initial to goal or fail state 
  3. successSteps: A list of integers for recording steps leading to goal state in each iteration, for calculating the average of
  success steps 
  4. failureSteps: A list of integers for recording steps not leading to goal state in each iteration, for calculating the average of
  fail steps 
  
  Methods: 
  Usual getter and setter methods for all the variables listed above such as isGoalReached(), setGoalReached (), getNoOfTries(),
  setNoOfTries(), getSuccessSteps(), setSuccessSteps(), getFailureSteps(), setFailureSteps()  
