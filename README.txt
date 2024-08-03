342810835
316153386
*****
Comments:
Q1 - How does your agent fare?

scores: [1316, 6060, 2856, 1564, 2976, 3756, 1732, 5420, 5344, 3600]
highest tile: [128, 512, 256, 128, 256, 256, 128, 512, 512, 256]
game_durations: [0.12837004661560059, 0.32182955741882324, 0.17993617057800293, 0.17352557182312012,
0.24769186973571777, 0.25451183319091797, 0.14540362358093262, 0.3468759059906006, 0.325239896774292, 0.23276853561401367]
win rate: 0.0

Scores varying from 1316 to 6060 and highest tiles from 128 to 512.
Despite some high scores, the agent's consistency is lacking, as evidenced by the substantial variability in results.
The average game duration indicates quick decision-making, but the win rate of 0.0 suggests that the agent struggles
to reach the game's winning conditions.

Q7 - Description evaluation function
This evaluation function assesses the given game state using a linear
combination of various heuristic features to provide an overall score.
The features considered are as follows:
    1. Max Tile in Corners: Checks if the highest tile is in one of the
    four corners of the board. A high score is awarded if the condition is met.
     Positioning the highest tile in a corner is a common strategy in 2048, as it can help in organizing the board
     and making merges more predictable. A high weight is assigned to encourage this strategic positioning.

    2. Monotonicity: Evaluates how monotonic the rows and columns are,
    indicating that the tiles are either consistently non-increasing
    or non-decreasing.
    Monotonicity is important because it indicates organized tiles, which facilitates easier merges.
    By ensuring rows and columns follow a monotonic pattern, the agent can achieve higher tiles more systematically

    3. Smoothness: Measures the difference between adjacent tiles.
     A smaller difference indicates a smoother board,
     which is generally more desirable.
     A smoother board is easier to manage and merge tiles on. By penalizing high differences between adjacent tiles,
     the agent is encouraged to maintain a smooth board, which is beneficial for future merges.

    4. Empty Tiles: Counts the number of empty tiles on the board,
    as having more empty spaces often provides more opportunities
     for making moves.
     A moderate weight is assigned to prioritize the creation and maintenance of empty spaces.

    5. Legal Actions: Considers the number of possible moves the player can
     make, encouraging flexibility and the ability to continue gameplay.
     The ability to make more moves indicates greater flexibility and potential to continue gameplay.
     A high weight is given to this feature to emphasize the importance of keeping options open for the agent.

     6. Score : The current score of the game.
     It is included to ensure that the evaluation function aligns with the game's primary objective
      of maximizing the score.

     7. Max_tile : The highest tile currently on the board
     The highest tile reflects the agent's ability to achieve significant merges.
     It is included to directly reward the agent for reaching high tiles.

We used ChatGPT for helping us to formulate the understanding question.
We also used it in order to improve our algorithms structure, we saw an implementation of Minimax in Youtube and made
adjustements to our game.

