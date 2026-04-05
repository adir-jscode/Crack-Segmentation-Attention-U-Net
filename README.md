# Crack Segmentation with Attention U-Net

## Overview

This project implements an Attention U-Net model for crack segmentation in images. Crack segmentation is a critical task in structural health monitoring, enabling automated detection and analysis of cracks in infrastructure such as roads, bridges, and buildings. The Attention U-Net architecture enhances the traditional U-Net by incorporating attention gates, which improve the model's ability to focus on relevant features during segmentation.

The implementation is provided as a Jupyter Notebook, making it easy to run and experiment with the code. The model is trained on a crack segmentation dataset and can be used to predict crack masks from input images.

## Features

- **Attention U-Net Architecture**: Utilizes attention gates to improve segmentation accuracy by focusing on salient regions.
- **Data Preprocessing**: Includes image loading, resizing, normalization, and train-validation split.
- **Model Training**: Compiles and trains the model using TensorFlow/Keras with binary cross-entropy loss.
- **Visualization**: Provides functions to visualize original images, ground truth masks, and predicted masks.
- **Scalable**: Easily adaptable to different image sizes and datasets.

## Requirements

To run this notebook, you need the following dependencies:

- Python 3.7+
- TensorFlow 2.x
- NumPy
- OpenCV (cv2)
- Matplotlib
- Scikit-learn

You can install the required packages using pip:

```bash
pip install tensorflow numpy opencv-python matplotlib scikit-learn
```

## Dataset

This project uses the [Crack Segmentation Dataset](https://www.kaggle.com/datasets/balraj98/crack-segmentation-dataset) from Kaggle. The dataset contains images of cracks and their corresponding binary masks.

- **Images**: RGB images of surfaces with potential cracks.
- **Masks**: Binary masks indicating crack locations.

### Data Structure

- Images folder: `crack_segmentation_dataset/images/`
- Masks folder: `crack_segmentation_dataset/masks/`

If running on Kaggle, the dataset should be added as an input. For local execution, download the dataset and update the `image_path` and `mask_path` variables in the notebook.

## Usage

1. **Clone or Download the Repository**:

   ```bash
   git clone https://github.com/your-username/crack-segmentation-attention-u-net.git
   cd crack-segmentation-attention-u-net
   ```

2. **Open the Notebook**:
   Open `crack-segmentation-attentationunet.ipynb` in Jupyter Notebook or JupyterLab.

3. **Update Paths**:
   Modify the `image_path` and `mask_path` variables to point to your dataset locations.

4. **Run the Cells**:
   Execute the cells in order:
   - Import libraries and load data.
   - Define the Attention U-Net model.
   - Compile and train the model.
   - Visualize predictions.

5. **Training**:
   The model is trained for 20 epochs with a batch size of 8. You can adjust these hyperparameters as needed.

6. **Prediction**:
   Use the `visualize_predictions` function to see model performance on validation data.

## Model Architecture

The Attention U-Net consists of:

- **Encoder**: Four convolutional blocks with max pooling for feature extraction.
- **Bottleneck**: Deep convolutional layers at the lowest resolution.
- **Decoder**: Upsampling with attention gates to refine features.
- **Attention Gates**: Applied at each decoder level to focus on relevant encoder features.
- **Output**: Single-channel sigmoid activation for binary segmentation.

The model input shape is (128, 128, 3), and it outputs a (128, 128, 1) mask.

## Results

After training, the model can segment cracks with high accuracy. The visualization function displays:

- Original images
- Ground truth masks
- Predicted masks

Example visualizations are generated in the notebook.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your improvements.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

- Dataset provided by Balraj Ashwath on Kaggle.
- Inspired by the Attention U-Net paper: [Attention U-Net: Learning Where to Look for the Pancreas](https://arxiv.org/abs/1804.03999).

## Contact

For questions or issues, please open an issue on GitHub or contact the maintainer.
