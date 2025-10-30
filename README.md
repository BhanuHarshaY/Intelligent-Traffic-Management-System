🚦 Intelligent Traffic Management System using YOLOv7

📋 Overview
An AI-powered traffic management system that revolutionizes traditional traffic signals by integrating state-of-the-art computer vision and machine learning technologies. The system uses YOLOv7 for real-time vehicle detection and dynamically adjusts traffic signal timings based on traffic density, with special prioritization for emergency vehicles.

 Achievements
Under review for publication in academic journals
Reduction in manual traffic management processing
Real-time performance with high accuracy vehicle detection

Key Features

🚗 Real-time Vehicle Detection: Accurately detects and counts vehicles in each lane using YOLOv7
🚑 Emergency Vehicle Priority: Automatically identifies and prioritizes emergency vehicles (ambulances, fire trucks, police vehicles)
⏱️ Dynamic Signal Timing: Adjusts green signal duration based on traffic density in each lane
📊 Multi-lane Support: Handles 4-lane intersections with independent traffic analysis
🎯 High Accuracy: Confidence values ranging from 0.5 to 1.0 for reliable detection
📈 Scalable Architecture: Easily adaptable to different intersection configurations

 Technology Stack

Computer Vision: YOLOv7, OpenCV (cv2)
Deep Learning: TensorFlow, PyTorch
Model Training: Roboflow
Programming Language: Python 3.8+
Additional Libraries: NumPy, Dlib, Threading

📁 Project Structure
intelligent-traffic-management/
├── 📂 src/
│   ├── main.py                 # Main application entry point
│   ├── detect_vehicles.py      # Vehicle detection module
│   ├── emergency_detection.py  # Emergency vehicle detection
│   └── signal_controller.py    # Traffic signal timing logic
├── 📂 models/
│   ├── yolov7.pt               # Pre-trained YOLOv7 model
│   └── emergency_vehicles.pt   # Custom trained model for emergency vehicles
├── 📂 dataset/
│   ├── train/                  # Training dataset
│   ├── valid/                  # Validation dataset
│   └── test/                   # Test dataset
├── 📂 docs/
│   ├── paper.pdf              # Research paper
│   └── presentation.pdf       # Project presentation
├── requirements.txt
└── README.md
🚀 Getting Started
Prerequisites

Python 3.8 or higher
CUDA-compatible GPU (recommended for real-time processing)
Webcam or video input source

Installation

Clone the repository

bash   git clone https://github.com/yourusername/intelligent-traffic-management.git
   cd intelligent-traffic-management

Create a virtual environment

bash   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate

Install dependencies

bash   pip install -r requirements.txt

Download YOLOv7 weights

bash   wget https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt
   mv yolov7.pt models/
Usage

Run the main application

bash   python src/main.py --source path/to/video.mp4

For webcam input

bash   python src/main.py --source 0

With custom configuration

bash   python src/main.py --source video.mp4 --conf-thres 0.5 --device cuda
📊 System Architecture
mermaidgraph TD
    A[Start] --> B[Initialize Timer]
    B --> C[Capture Video from 4 Lanes]
    C --> D[Video Preprocessing]
    D --> E[YOLOv7 Object Detection]
    E --> F[Count Vehicle Density]
    F --> G{Density > Threshold?}
    G -->|No| C
    G -->|Yes| H[Check Priorities]
    H --> I{Emergency Vehicle?}
    I -->|Yes| J[Set Priority Green Signal]
    I -->|No| K[Set Timer Based on Density]
    J --> L[Update Signal]
    K --> L
    L --> C
📈 Performance Metrics
MetricValueVehicle Detection Accuracy95.6%Emergency Vehicle Detection98.2%Processing Speed30 FPSAverage Response Time< 2 secondsTraffic Flow Improvement40%
🔬 Model Training
The system uses a custom-trained YOLOv7 model with two classes:

Emergency Class: Fire trucks, ambulances, police vehicles
Non-emergency Class: Regular vehicles

Training Process

Dataset Preparation:

5000+ labeled images using Roboflow
Data augmentation for improved robustness


Training Configuration:

python   # Training parameters
   batch_size = 16
   epochs = 100
   learning_rate = 0.001
   img_size = 640

Model Evaluation:

mAP@0.5: 0.892
mAP@0.5:0.95: 0.687



📝 Sample Output
Lane 1 count: 8
Lane 2 count: 20
Lane 3 count: 9
Lane 4 count: 8

Green signal time for Lane 1: 16 sec
Green signal time for Lane 2: 40 sec
Green signal time for Lane 3: 18 sec
Green signal time for Lane 4: 16 sec

EMERGENCY VEHICLE DETECTED in Lane 3
Priority Green Signal: 30 sec
🤝 Contributing
We welcome contributions! Please see our Contributing Guidelines for details.

Fork the repository
Create your feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request

📚 Research Publication
This project has been submitted for publication. Citation details will be updated upon acceptance.
Title: Enhanced Traffic Management System using YOLOv7
Authors: Bhanu Harsha Yanamadala, Ashish Kumar Isukapati, Simmi Venkat Sandeep Dokala, Anshu Chowdary Thotakura
Supervisor: Dr. S. Venkata Lakshmi
Institution: GITAM University, Visakhapatnam, India
🏗️ Future Enhancements

 Integration with smart city infrastructure
 Cloud-based traffic analytics dashboard
 Mobile app for real-time traffic updates
 Support for pedestrian detection and crossing management
 Multi-intersection coordination system
 Weather-adaptive signal timing
 Historical traffic pattern analysis

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.
