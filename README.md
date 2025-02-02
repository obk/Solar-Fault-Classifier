
# Solar Fault Classifier

This project implements a Convolutional Neural Network (CNN) for classifying solar panel faults from images. The model detects four types of faults:
- Bypass Diode Activated
- Junction Box
- Multicell Hotspot
- Single Cell Hotspot

## Project Structure

```
.
├── app.ipynb              # Jupyter notebook for model training
├── test.ipynb             # Jupyter notebook for model evaluation
└── images_classed/        # Images directory
```

## Dependencies

Install required packages using:
```bash
pip install -r requirements.txt
```

*Note: A GPU is recommended for faster training.*

## Usage

### 1. Model Training (`app.ipynb`)

1. Organize your dataset in the `images_classed/` directory with subfolders for each class
2. Run all cells in `app.ipynb`:
   - Trains the CNN model with data augmentation
   - Monitors training progress through accuracy/loss metrics
   - Saves final model as `solar_fault_classifier.h5`

### 2. Model Evaluation (`test.ipynb`)

1. Execute all cells in `test.ipynb`:
   - Evaluates model performance (using same images due to data limitations)
   - Displays accuracy metrics and visualizations
   - Shows prediction comparisons with actual labels

![Evaluation Metrics](./output1.png)

### 3. Prediction Examples

Sample evaluation output:
```text
Testing images from class: Bypass_Diode_activated
Image: img001.jpg | Actual: Bypass_Diode_activated | Predicted: Bypass_Diode_activated
...
Testing images from class: Single_cell_hotspot 
Image: img005.jpg | Actual: Single_cell_hotspot | Predicted: Multicell_hotspot
...
```

![Prediction Visualization](./output2.png)

## Key Components

- `app.ipynb`: Model training notebook
  - CNN architecture with convolutional layers and dropout
  - Uses ImageDataGenerator for augmentation/validation
  - Saves trained model weights

- `test.ipynb`: Model evaluation notebook
  - Loads pretrained model
  - Generates performance metrics
  - Creates visualizations of predictions

- `images_classed/`: Image dataset structure  
  ```
  images_classed/
  ├── Bypass_Diode_activated
  ├── Junction_box
  ├── Multicell_hotspot
  └── Single_cell_hotspot
  ```

## Specifications

- Input image size: 150 × 150 pixels (RGB)
- Data augmentation applied during training
- Comprehensive evaluation metrics included
- Visualizations for model interpretation

For questions or issues, please open an issue in the repository.
