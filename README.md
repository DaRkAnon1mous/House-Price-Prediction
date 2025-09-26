# 🏠 House Price Prediction

A machine learning web application that predicts house prices in California using linear regression. Built with Flask and deployed on Railway using Docker.

## 🚀 Live Demo

**[Try the Application](https://web-production-c2dac.up.railway.app/)**

## 📋 Project Overview

This project implements an end-to-end machine learning pipeline for predicting California house prices using the famous California Housing dataset from scikit-learn. The model is trained on 20,640 samples from the 1990 U.S. census data and deployed as a user-friendly web application.

### 🎯 Features

- **Interactive Web Interface**: Clean, responsive UI for entering house features
- **Real-time Predictions**: Get instant price predictions based on input features
- **RESTful API**: JSON API endpoint for programmatic access
- **Dockerized Deployment**: Containerized application deployed on Railway
- **Linear Regression Model**: Trained on California Housing dataset with feature scaling

## 📊 Dataset Information

The California Housing dataset contains the following 8 features:

| Feature | Description |
|---------|-------------|
| **MedInc** | Median income in block group |
| **HouseAge** | Median house age in block group |
| **AveRooms** | Average number of rooms per household |
| **AveBedrms** | Average number of bedrooms per household |
| **Population** | Block group population |
| **AveOccup** | Average number of household members |
| **Latitude** | Block group latitude |
| **Longitude** | Block group longitude |

- **Target Variable**: Median house value (in units of $100,000)
- **Dataset Size**: 20,640 samples
- **No Missing Values**: Complete dataset with all features populated

## 🛠️ Tech Stack

- **Backend**: Flask (Python web framework)
- **Machine Learning**: scikit-learn, numpy, pandas
- **Model**: Linear Regression with StandardScaler
- **Frontend**: HTML5, CSS3, Bootstrap
- **Deployment**: Docker + Railway
- **Model Serialization**: Pickle

## 🏗️ Project Structure

```
House-Price-Prediction/
├── Notebooks/
│   └── Linear Regression.ipynb    # Model training and analysis
├── Models/
│   ├── linregmodel.pkl           # Trained linear regression model
│   └── scaling.pkl               # Feature scaler
├── templates/
│   └── home.html                 # Web interface template
├── app.py                        # Flask application
├── requirements.txt              # Python dependencies
├── Dockerfile                    # Container configuration
├── Procfile                      # Railway deployment config
└── README.md                     # Project documentation
```

## 🔧 Installation & Setup

### Prerequisites
- Python 3.12+
- pip package manager
- Git

### Local Development

1. **Clone the repository**
```bash
git clone https://github.com/DaRkAnon1mous/House-Price-Prediction.git
cd House-Price-Prediction
```

2. **Create virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Run the application**
```bash
python app.py
```

5. **Access the application**
   - Open your browser and navigate to `http://localhost:5000`
   - Use the prediction interface at `http://localhost:5000/predict`

### Docker Deployment

```bash
# Build the Docker image
docker build -t house-price-prediction .

# Run the container
docker run -p 5000:5000 house-price-prediction
```

## 📡 API Usage

### Web Interface
Visit the live application at: https://web-production-c2dac.up.railway.app/

### REST API Endpoint

**Endpoint**: `POST /predict_api`

**Request Format**:
```json
{
  "data": {
    "MedInc": 8.3252,
    "HouseAge": 41.0,
    "AveRooms": 6.984127,
    "AveBedrms": 1.023810,
    "Population": 322.0,
    "AveOccup": 2.555556,
    "Latitude": 37.88,
    "Longitude": -122.23
  }
}
```

**Response**:
```json
4.526
```

### Example cURL Request

```bash
curl -X POST https://web-production-c2dac.up.railway.app/predict_api \
  -H "Content-Type: application/json" \
  -d '{
    "data": {
      "MedInc": 8.3252,
      "HouseAge": 41.0,
      "AveRooms": 6.984127,
      "AveBedrms": 1.023810,
      "Population": 322.0,
      "AveOccup": 2.555556,
      "Latitude": 37.88,
      "Longitude": -122.23
    }
  }'
```

## 🧠 Model Information

### Algorithm
- **Linear Regression**: Simple yet effective algorithm for price prediction
- **Feature Scaling**: StandardScaler used to normalize input features
- **Training Data**: 20,640 samples from 1990 California census

### Model Pipeline
1. **Data Loading**: California Housing dataset from scikit-learn
2. **Preprocessing**: Feature scaling using StandardScaler
3. **Model Training**: Linear Regression with scikit-learn
4. **Model Serialization**: Saved using pickle for deployment
5. **Prediction**: Real-time inference through web interface

### Performance
The model provides reliable predictions for California house prices based on the 8 input features. Performance metrics and validation details are available in the Jupyter notebook.

## 🚀 Deployment

This application is deployed on **Railway** using Docker containerization:

- **Platform**: Railway Cloud Platform
- **Container**: Docker with Python 3.12 base image
- **Web Server**: Gunicorn with 4 workers
- **Auto-scaling**: Handled by Railway infrastructure

### Deployment Configuration

- **Dockerfile**: Multi-stage build for optimized container
- **Procfile**: Gunicorn server configuration
- **Port**: Dynamic port binding for Railway deployment

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Areas for Improvement

- [ ] Add more regression algorithms (Random Forest, XGBoost)
- [ ] Implement cross-validation and model comparison
- [ ] Add data visualization dashboards
- [ ] Improve UI/UX with modern frameworks
- [ ] Add input validation and error handling
- [ ] Implement model monitoring and performance tracking

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **scikit-learn** team for the California Housing dataset
- **Flask** community for the excellent web framework
- **Railway** for providing easy deployment platform
- **StatLib repository** for the original dataset source

## 📞 Contact

**Developer**: DaRkAnon1mous  
**GitHub**: [@DaRkAnon1mous](https://github.com/DaRkAnon1mous)  
**Project Link**: [House-Price-Prediction](https://github.com/DaRkAnon1mous/House-Price-Prediction)

---

⭐ **Star this repository if you found it helpful!** ⭐