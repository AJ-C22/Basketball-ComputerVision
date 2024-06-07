# 🏀 AI-Enhanced Basketball Score Counter

This project is an AI-enhanced basketball score counter using YOLO for object detection and DeepSORT for tracking. It detects the ball, players, and rim to automatically count the scores for two teams.

## 📋 Requirements

- Python 3.x
- OpenCV
- YOLOv5
- DeepSORT
- SciPy
- NumPy
- collections (defaultdict)

## 🛠️ Installation

1. **Clone the repository:**

    ```sh
    git clone https://github.com/your-username/ai-basketball-score-counter.git
    cd ai-basketball-score-counter
    ```

2. **Install the dependencies:**

    ```sh
    pip install -r requirements.txt
    ```

3. **Download the YOLO model:**

    Ensure you have a trained YOLO model named `best.pt` in the project directory.

## 🚀 Usage

1. **Run the script:**

    ```sh
    python shot.py
    ```

2. **Control Instructions:**

    - **Mouse Click:** 🖱️ Assigns a player to team 2 (Orange) or toggles back to team 1 (Blue).
    - **Press 'q':** ❌ Quit the application.

## 🌟 Features

- **Object Detection:** Utilizes YOLO for detecting the ball, players, and rim.
- **Object Tracking:** Uses DeepSORT to track players and ball movements.
- **Scoring Mechanism:** 
  - Detects when the ball passes through the rim to count scores.
  - Maintains separate scores for two teams (Orange and Blue).
- **Interactive Team Assignment:** 
  - Click near a player to assign them to a team.
  - Team 1 (Blue) and Team 2 (Orange) can be distinguished by bounding box colors.
- **Shooting Zone Detection:** 
  - Identifies the shooting zone for each player.
  - Changes color to indicate the ball's presence in the shooting zone.

## 💡 Implementation Details

### YOLO Model

- The YOLO model is used for object detection with a custom-trained model `best.pt`.
- Classes detected include `ball`, `person`, and `rim`.

### DeepSORT Tracker

- DeepSORT is used to track detected players.
- Each player is assigned a unique ID.
- Players can be interactively assigned to teams.

### Scoring Logic

- The ball's position relative to the rim is used to determine scores.
- Separate counters for each team track the number of successful shots.

### Dots for Ball Trajectory

- The ball's trajectory above the rim is visualized using green dots.
- Gaussian filtering smooths the ball's trajectory for better visualization.

## 🔧 Customization

- **Frame Skip:** Adjust the `self.frame_skip` variable to process every nth frame for performance optimization.
- **Confidence Threshold:** Modify the `conf > 0.4` line to change the detection confidence threshold.
- **Box Sizes:** Change `box_width` and `box_height` for the rim boxes to adjust the size of the top and bottom scoring zones.

## 📌 Notes

- Ensure your webcam is properly connected for real-time video capture.
- The performance may vary based on the hardware and quality of the YOLO model used.

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [YOLO](https://github.com/ultralytics/yolov5)
- [DeepSORT](https://github.com/nwojke/deep_sort)

