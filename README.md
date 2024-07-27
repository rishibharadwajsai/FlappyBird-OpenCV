# FlappyBird-OpenCV

This is a fork of the original Flappy Bird-style game implemented with Python. In this fork, the game is controlled using facial gestures captured by a webcam. The project uses Pygame for graphics, OpenCV for webcam access, and MediaPipe for face mesh detection.

## Features

- **Face-Controlled Gameplay**: Control the bird's vertical movement using facial gestures. The bird's position adjusts based on the vertical position of your nose tip.
- **Dynamic Obstacles**: Pipes spawn at varying intervals and positions, increasing the difficulty as you progress.
- **Real-Time Updates**: The game updates the screen in real-time with the webcam feed and game elements.

## Original Repository

This repository is a fork of the original [FlappyBirdCV](https://github.com/pr28416/FlappyBirdCV) repository. The primary modifications include:

- Integration of face-controlled input using MediaPipe.
- Adjustments to game mechanics to accommodate face detection.

## Requirements

- Python 3.x
- Pygame
- OpenCV
- MediaPipe
- NumPy (for array operations)

You can install the required Python libraries using pip:

```bash
pip install -r requirements.txt
```

## Installation

1. **Clone the Repository**:
   
   ```bash
   git clone https://github.com/rishibharadwajsai/FlappyBird-OpenCV.git
   cd FlappyBird-OpenCV
   ```

2. **Download Assets**: Ensure you have the required image assets (`bird_sprite.png` and `pipe_sprite_single.png`). Place these image files in the same directory as your script.

3. **Run the Game**:

   ```bash
   python main.py
   ```

## How It Works

1. **Initialization**:
   - The game initializes the webcam feed using OpenCV and sets up the game window with Pygame.
   - It loads the bird and pipe images, sets up initial parameters, and starts the game loop.

2. **Face Detection**:
   - The game uses MediaPipe's Face Mesh model to detect facial landmarks. Specifically, the y-coordinate of the nose tip is used to control the bird's vertical position.

3. **Game Loop**:
   - **Input Handling**: The game checks for user input (e.g., quitting the game).
   - **Frame Processing**: Captures the current frame from the webcam, processes it for face landmarks, and adjusts the bird's position.
   - **Pipe Management**: Pipes are moved across the screen, and new pipes are spawned periodically.
   - **Collision Detection**: Checks if the bird collides with any pipes, which ends the game if true.
   - **Score Tracking**: Updates and displays the score based on the bird passing through the pipes.

4. **Difficulty Progression**:
   - The game increases in difficulty over time by reducing the interval between pipe spawns.

## Customization

- **Bird and Pipe Images**: Replace `bird_sprite.png` and `pipe_sprite_single.png` with your own images to customize the look of the game.
- **Difficulty Settings**: Adjust parameters such as `time_between_pipe_spawn` and `space_between_pipes` to modify the game's difficulty.

## Troubleshooting

- **Empty Frame**: If the webcam feed is empty, ensure the webcam is connected and working properly.
- **Missing Assets**: Ensure that the image files (`bird_sprite.png` and `pipe_sprite_single.png`) are in the correct directory.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
