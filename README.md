## 191's AR Pong Game

Welcome to **191's AR Pong Game**, a real-time augmented reality pong experience built with Python, OpenCV, Dlib, and Tkinter. This game overlays a paddle and AR effects (glasses and hat) onto live webcam footage, allowing you to control the paddle by moving a colored object and enjoy fun AR face filters while you play.

---

## Features

* **Real-Time Video Feed**: Streams video from your webcam using OpenCV.
* **Color-Based Paddle Control**: Track a yellow object to move the paddle smoothly on screen.
* **Augmented Reality Effects**: Overlay glasses and a hat onto detected faces using Dlib facial landmarks.
* **Pong Gameplay**: Bouncing ball physics, hit detection, and speed increments for challenging gameplay.
* **Score Tracking**: Displays current hits and high score, persisting high score across sessions.
* **Screenshots**: Capture and save screenshots of the current game frame.
* **Restart and Quit**: Easy controls to restart the game or exit.

---

## Prerequisites

* Python 3.7 or higher
* A webcam (built-in or USB)

### Python Packages

Install required packages via `pip`:

```bash
pip install opencv-python numpy dlib Pillow tkinter
```

> **Note**: On some systems, you may need to install additional OS-level dependencies for Dlib.

---

## Installation

1. **Clone the repository**:

   ```bash
   ```

git clone [https://github.com/yourusername/ar-pong-game.git](https://github.com/yourusername/ar-pong-game.git)
cd ar-pong-game

````

2. **Download Resources**:

Place the following files in the project root:

- `ball.png` — image for the pong ball
- `paddle.png` — image for the paddle
- `glasses.png` — transparent PNG for AR glasses
- `cap.png` — transparent PNG for AR hat
- `shape_predictor_68_face_landmarks.dat` — Dlib facial landmark model (download from http://dlib.net)

3. **Adjust Paths** (if needed):

Open `main.py` (or your script) and update the file paths for the images and model at the top of the file:

```python
self.original_ball_img = cv2.imread(r"path/to/ball.png", cv2.IMREAD_UNCHANGED)
self.original_paddle_img = cv2.imread(r"path/to/paddle.png", cv2.IMREAD_UNCHANGED)
self.PREDICTOR_PATH = r"path/to/shape_predictor_68_face_landmarks.dat"
self.glasses_img = cv2.imread(r"path/to/glasses.png", cv2.IMREAD_UNCHANGED)
self.hat_img = cv2.imread(r"path/to/cap.png", cv2.IMREAD_UNCHANGED)
````

---

## Usage

Run the application with:

```bash
python main.py
```

### Controls

* **Move Paddle**: Present a yellow object (e.g., a tennis ball or sticky note) to the camera; the paddle will follow its motion.
* **Restart Game**: Click the **Restart** button to reset ball position and hit count.
* **Screenshot**: Click the **Screenshot** button to save the current frame under `screenshots/`.
* **Quit Game**: Click the **Quit** button or close the window to exit.

---

## File Structure

```
├── main.py                # Core application code
├── ball.png               # Paddle hit indicator image
├── paddle.png             # Paddle visual image
├── glasses.png            # AR glasses overlay
├── cap.png                # AR hat overlay
├── shape_predictor_68_face_landmarks.dat  # Dlib model
├── highscore.txt          # Stores the high score
└── screenshots/           # Saved screenshots
```

---

## Customization

* **Color Tracking**: Tweak HSV bounds (`lower_color`, `upper_color`) for different colored objects.
* **Game Speed**: Adjust `SPEED_INCREMENT` or `MAX_SPEED` for different difficulty curves.
* **AR Assets**: Replace `glasses.png` and `cap.png` with your own transparent PNGs.

---

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for enhancements, bug fixes, or new features.

---

## License

This project is released under the [MIT License](LICENSE).

---

## Acknowledgments

* [OpenCV](https://opencv.org/) for video processing.
* [Dlib](http://dlib.net/) for face detection and landmark prediction.
* [Tkinter](https://docs.python.org/3/library/tkinter.html) for the GUI.
* [https://github.com/ageitgey/face\_recognition](https://github.com/ageitgey/face_recognition) for reference on AR overlays.
