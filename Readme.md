# NeuralArt 🎨

**NeuralArt** is a web-based application that performs Arbitrary Style Transfer using Adaptive Instance Normalization (AdaIN) in PyTorch. It allows users to upload a content image and a style image, seamlessly blending them to create unique, neural-generated artwork. 

## 📁 Repository Structure

* **`app.py`**: The main web application script that handles routing and model inference.
* **`train.py`**: Script for training the AdaIN style transfer model from scratch.
* **`experiment/`**: Directory meant for storing trained model weights (e.g., `decoder_1.pth`) and training logs.
* **`static/examples/`**: Contains static assets, CSS, and example images for the web interface.
* **`templates/`**: HTML templates rendering the frontend UI.
* **`utils/`**: Utility modules for image preprocessing, tensor operations, and network definitions.
* **`Procfile`**: Configuration file for deploying the application to cloud platforms (like Heroku).
* **`requirements.txt`**: Lists all Python dependencies required to run the project.

## 🚀 Features

* **Arbitrary Style Transfer**: Apply any artistic style to any content image instantly without retraining.
* **Web Interface**: Clean, user-friendly HTML/CSS frontend for easy image uploading.
* **Deployment Ready**: Pre-configured with a `Procfile` for seamless cloud hosting.

## 💻 Getting Started

### Prerequisites

Ensure you have Python 3.x installed. 

### Installation

1. **Clone the repository:**
   ```
   git clone [https://github.com/shristirwt/NeuralArt.git](https://github.com/shristirwt/NeuralArt.git)
   cd NeuralArt
   ```

2. **Create and activate a virtual environment (Recommended):**
    ```
    python -m venv venv
    # On Windows:
    venv\Scripts\activate
    # On macOS/Linux:
    source venv/bin/activate
    ```


3. **Install the dependencies:**
    ```
    pip install -r requirements.txt

    ```


### Running the App Locally

Start the local development server:

```
python app.py
```

The application will be accessible in your web browser, typically at `http://localhost:5000` or `http://127.0.0.1:8000`.

> **Note on Model Weights:** Ensure your trained `.pth` files (like your encoder and decoder weights) are placed in the `experiment/` directory as referenced in `app.py`. If you are running the app on a CPU-only machine, ensure your `torch.load()` functions in `app.py` use the `map_location=torch.device('cpu')` argument to successfully deserialize the weights.

## 🧠 Training Your Own Model

To train the AdaIN model using your own datasets, use the provided training script. You will need a dataset of content images and a dataset of style images.

```
python train.py --content_dir path/to/content --style_dir path/to/style
```

*(Check `train.py` for specific hyperparameter arguments like batch size, learning rate, and iteration count.)*

