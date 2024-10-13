# Drone Detection System

## Overview
This project implements a drone-based detection system using a DJI Tello drone, YOLO object detection, and a Pygame-based user interface. The system is designed for search and rescue operations, capable of detecting humans and animals in the drone's field of view.

## Features
- Real-time video feed from the Tello drone
- YOLO-based object detection for humans and animals
- Interactive map displaying drone position and detected entities
- Pygame-based user interface for drone control and status display
- Twilio integration for sending alerts to rescue teams
- Flask server for receiving external alert triggers

## Requirements
- Python 3.7+
- pygame
- opencv-python (cv2)
- numpy
- djitellopy
- ultralytics (YOLO)
- Flask
- twilio

## Setup
1. Install the required packages:
   ```
   pip install pygame opencv-python numpy djitellopy ultralytics Flask twilio
   ```

2. Download the YOLO model file (`yolo11n.pt`) and place it in the project directory.

3. (Optional) Download the "PixeloidSans-Bold.ttf" font file and place it in the project directory for the Forager-inspired UI.

4. Configure Twilio:
   - Sign up for a Twilio account and obtain your Account SID and Auth Token
   - Replace the placeholder values in the code:
     - `TWILIO_ACCOUNT_SID`
     - `TWILIO_AUTH_TOKEN`
     - `TWILIO_PHONE_NUMBER`
     - `RESCUE_TEAM_PHONE_NUMBER`

## Usage
1. Connect your computer to the Tello drone's Wi-Fi network.

2. Run the script:
   ```
   python drone_detection_system.py
   ```

3. Use the Pygame window to control the drone and view the detection results:
   - Click the "Take Off" button or press 'E' to start flying
   - Use arrow keys to move the drone
   - Use W/S keys to adjust altitude
   - Use A/D keys to rotate the drone
   - Click the "Land" button or press 'Q' to land the drone

4. The system will display detected objects and their positions on the map.

5. To trigger an external alert, send a POST request to `http://localhost:5000/alert` with JSON data:
   ```json
   {
     "danger_detected": true,
     "location": "coordinates or description",
     "severity": "high"
   }
   ```

## Safety and Legal Considerations
- Always follow local drone regulations and obtain necessary permissions before flying.
- Ensure the drone's battery is sufficiently charged before each flight.
- Operate the drone in a safe, open area away from people, animals, and obstacles.
- Be prepared to land the drone immediately in case of any issues or loss of control.

## Limitations and Future Improvements
- The current system uses a simulated map. Integration with real GPS data could enhance accuracy.
- Add support for more diverse terrains and weather conditions.
- Implement collision avoidance mechanisms for safer autonomous flight.
- Enhance the alert system with more detailed information and multiple communication channels.

## Contributing
Contributions to improve the system are welcome. Please submit pull requests or open issues to discuss proposed changes.

## License
[Specify your chosen license here]
