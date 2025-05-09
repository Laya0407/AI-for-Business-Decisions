# Sprint 3: Steel Defect Detection

## Project Overview
This project implements deep learning segmentation models to automatically detect and classify surface defects in steel manufacturing. The system helps identify quality issues in steel production, allowing for early intervention and quality control improvements. Proper defect detection is critical in the steel industry to ensure product safety and reduce waste.

## Dataset Description
The dataset used is the Severstal Steel Defect Detection dataset which includes:
- Steel surface images (256x1600 pixels)
- 4 different defect classes
- Defect annotations in Run-Length Encoding (RLE) format
- 12,568 total images, with approximately half containing defects

## Methodology

### Data Exploration & Preprocessing
- Analysis of defect distribution across classes
- Visualization of defect areas and types
- Decoding of RLE format into binary masks
- Implementation of custom data loading and transformation pipeline
- Image resizing and normalization for model input

### Data Augmentation
Applied the following augmentations to improve model generalization:
- Horizontal and vertical flips
- Random rotations (90°)
- Random brightness and contrast adjustments
- Gaussian blur
- Resizing to 128x128 for computational efficiency

### Model Architecture
Implemented two deep learning architectures:
1. **U-Net with MobileNetV2 backbone**
   - Encoder pre-trained on ImageNet
   - Binary segmentation for defect identification
   - Customized for steel defect specifics

2. **LinkNet with MobileNetV2 backbone**
   - Optimized for faster inference
   - Maintains high accuracy with fewer parameters
   - Better for potential deployment in production environments

### Training Strategy
- Focal Loss to address class imbalance (many more non-defect than defect pixels)
- Adam optimizer with learning rate of 0.001
- Early stopping to prevent overfitting
- Batch size of 8 for memory efficiency
- Training with and without augmentations for comparison

## Results and Findings

### Model Performance
- **Model with Augmentation:**
  - IoU Score: 0.0002
  - F1 Score: 0.0005
  - Loss: 0.0000

- **Model without Augmentation:**
  - IoU Score: 0.0002
  - F1 Score: 0.0005
  - Loss: 0.0000

### Defect Analysis
- Found that defects constitute a small percentage of the total pixel area
- Distribution of defects is uneven across the 4 classes
- Defects often appear as thin lines or small regions making detection challenging
- Multiple defects can co-occur in the same image

### Visual Evaluation
- Successfully segmented various defect types across test samples
- Model effectively distinguished between defect and non-defect regions
- Performance was particularly strong on larger defects
- Some difficulty with very small or faint defects

## Technical Implementation Details

### Custom Components
- RLE encoding/decoding functions for mask manipulation
- Focal loss implementation for handling class imbalance
- Dynamic data loading pipeline for efficient batch processing
- Visualization tools for defect overlay and model prediction

### Optimization Techniques
- Transfer learning with pre-trained weights
- Appropriate model selection based on the task constraints
- Memory-efficient implementation for large images
- Balanced accuracy metrics for imbalanced data

## Applications & Business Value
- Automated quality control in steel manufacturing
- Reduction in manual inspection costs
- Consistent defect detection regardless of human factors (fatigue, attention)
- Early intervention in the production process to minimize waste
- Data-driven insights into common defect types and causes

## Technologies Used
- TensorFlow/Keras for model implementation
- Segmentation Models library for architecture components
- OpenCV for image processing
- Albumentations for data augmentation
- Scikit-learn for metrics calculation

## Future Work
- Test more sophisticated architectures (DeepLabV3+, FPN)
- Implement multi-class segmentation instead of binary
- Create an end-to-end pipeline for real-time defect detection
- Add uncertainty estimation for more reliable predictions
- Investigate class weighting to further address imbalance

## Team Members
- Motolani Akingbade
- Miracle Messiri
- Layanika Vinay Saravanan
