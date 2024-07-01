# Ellipse Prediction and Visualization for SEM Images

This project is a neural network-based approach to predict and visualize ellipses in Scanning Electron Microscope (SEM) images. The code preprocesses an input SEM image, segments it to detect ellipses, predicts the ellipse parameters using a trained neural network model and visualizes the results on the original image. 

## Features

- Load and preprocess SEM images.
- Segment SEM images to detect ellipses.
- Predict ellipse parameters using a trained neural network model.
- Visualize predicted ellipses on the original SEM image.
- Plot histograms of predicted radii and asymmetries.

## Requirements

- Python 3.x
- numpy
- matplotlib
- scikit-image
- tensorflow
- scikit-learn

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/andreaiorio/ellipse-prediction-se-images.git
    ```
2. Navigate to the project directory:
    ```sh
    cd ellipse-prediction-se-images
    ```
3. Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```

## Usage

1. **Load and preprocess the SEM image:**
    ```python
    path = 'Picture1.png'
    image = load_image(path)
    segmented_image = segment_image(image, plot=True)
    extracted_circles, extracted_scales, extracted_bboxes = extract_circles(segmented_image, image, plot=False)
    ```

2. **Prepare the test data:**
    ```python
    X_test = np.array(extracted_circles).reshape(-1, extracted_circles[0].shape[0], extracted_circles[0].shape[1], 1)
    ```

3. **Visualize predictions and histograms:**
    ```python
    visualize_predictions_and_histograms(image, X_test, extracted_scales, extracted_bboxes, num_samples=5)
    ```

## Functions

- `load_image(path)`: Loads and preprocesses the SEM image.
- `resize(image, size)`: Resizes the image to the specified size.
- `segment_image(image, plot)`: Segments the image to detect ellipses.
- `extract_circles(labeled_image, original_image, plot)`: Extracts ellipses from the segmented image.
- `visualize_predictions_and_histograms(original_image, X_test, scales, bboxes, num_samples)`: Visualizes predictions and plots histograms
- 
## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. 
