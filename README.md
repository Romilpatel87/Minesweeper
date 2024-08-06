# Minesweeper Neural Network Bot
This project involves developing and evaluating different agents for playing Minesweeper using a neural network approach. The project is divided into three main tasks, each focusing on different aspects of the game: traditional Minesweeper boards, variable numbers of mines, and variable size boards. Additionally, a bonus task involves generating Minesweeper boards using a Generative Adversarial Network (GAN).
## Logic Bot

### Description
The Logic Bot is designed to solve Minesweeper using deterministic rules. It:

- **Initialization**: Starts by initializing the game environment and sets up three key sets:
  - **Cells Remaining**: Initially contains all cells.
  - **Inferred Safe**: Initially empty.
  - **Inferred Mine**: Initially empty.

- **Cell Handling**: Queries the environment for cell information and updates accordingly.
  - **Revealed Clues**: Uses clues to infer the location of mines and safe cells.
  - **Inferences**:
    - **Mines Detection**: Marks cells as mines if the number of adjacent flagged cells matches the clue number.
    - **Safe Cells Inference**: Marks cells as safe if the number of adjacent safe cells plus flagged mines matches the clue number.

- **Loop**: Repeats the process until no new inferences can be made.

- **Outcome**: Returns the number of successfully revealed cells and the number of mines triggered.

## Task 1: Traditional Minesweeper Boards

### Description
The objective is to design a neural network agent for playing Minesweeper with three difficulty levels:

- **Easy**: 9x9 board with 10 mines.
- **Intermediate**: 16x16 board with 40 mines.
- **Expert**: 30x16 board with 99 mines.

The neural network should:
- **Input Representation**: Take a representation of the game state as input.
- **Output**: Predict which cell to open next based on the network’s output.
- **Iteration**: Continuously update the game state and compute the next cell to open until the game ends.

### Model Structure
- **Input Data**: Must represent available information, excluding hidden mines.
- **Model Design**: Use neural network layers suited for pattern recognition in grid-based data.
- **Training**: Address overfitting and make training efficient through techniques such as regularization.

### Evaluation
- **Comparison**: Compare the neural network bot to the Logic Bot in terms of:
  - **Board Clearance Rate**.
  - **Average Steps Before Hitting a Mine**.
  - **Mines Triggered by the End of the Game**.
- **Different Decisions**: Analyze scenarios where the neural network bot and the Logic Bot make different choices.

## Task 2: Variable Numbers of Mines

### Description
The goal is to build and train a network to handle varying numbers of mines on a 30x30 board, where mines can cover 0% to 30% of the board.

### Changes Required
- **Data Generation**: Include variable numbers of mines and generate corresponding data.
- **Model Adjustment**: Ensure the model can adapt to different mine densities.
- **Training**: Modify the training process to accommodate varying mine counts.

### Comparison Metrics
- **Board Clearance Probability**.
- **Average Steps Before the First Mine**.
- **Mines Triggered to Finish the Game**.

## Task 3: Variable Size Boards

### Description
Design a network that can play Minesweeper on variable-sized boards, specifically K x K where K ≥ 5.

### Model Adaptation
- **Architecture**: Modify the network to handle different board sizes dynamically.
- **Data and Training**: Adjust data preparation and training to accommodate board size variations.

### Comparison Metrics
- **Board Clearance Probability**.
- **Average Steps Before the First Mine**.
- **Mines Triggered to Finish the Game**.

## Bonus Task: Board Generation

### Description
Explore how to generate good Minesweeper boards using a neural network. The model should output playable Minesweeper boards that the trained bots can handle effectively.

### Model Structure
- **Network Design**: Create a model capable of generating Minesweeper boards.
- **Evaluation**: Assess the quality of the generated boards based on how well the bots perform on them.

## Writeup and Requirements

### Key Points
- **Model Structure**: Detail the architecture of your neural networks.
- **Data Generation**: Explain how you generated and utilized data.
- **Training Improvements**: Describe methods used to enhance training and prevent overfitting.
- **Performance Comparison**: Analyze where the neural network bot outperforms or underperforms compared to the Logic Bot.

### Additional Considerations
- **Game Perspective**: Discuss whether the game should be viewed sequentially or if the current state suffices.
- **Attention Mechanisms**: Experiment with and evaluate the applicability of attention mechanisms in your model.

---

*Note: This README provides a structured overview of the project tasks and expectations. Ensure to provide detailed explanations and comparisons in the final writeup.*
