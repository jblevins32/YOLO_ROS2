# Real-Time YOLO in ROS2
This repo contains the publishers and subscriber nodes for receiving camera images and outputting bbox data and yolo-curated images.

## How It Works
1. **Exploration:** The robot navigates the scene, collecting data on detected objects and their positions.
2. **Data Storage:** Scene data (objects and global positions) and relevant features are logged in a structured text format for processing.
3. **Reasoning Agent:** Large language model filters the scene data for objects relevant to the query and solves the referring expression.
   
# File Structure:
- `src`: Source code
  - `YOLO`: You only look once model for object tracking
    - `imgs`: images to process and saved images are all stored here
    - `models`: YOLO models (.pt files)
    - `output_data`: Generated output data
    - `get_data.py`: Function for parsing data from YOLO results to readable txt file
    - `yolo_subscriber.py`: Subscriber node to run YOLO tracking (runs yolo_world_ROS.py)
    - `yolo_world.py`: Main script for general inference, data collection, and visualization
    - `yolo_world_ROS.py`: Main script for ROS implementation for inference and data collection
- `environment.yaml`: environment for running the code. Not sure if we need this.
