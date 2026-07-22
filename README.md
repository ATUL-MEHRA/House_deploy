# 🏠 House Price Prediction API

A Machine Learning-based REST API that predicts house prices based on property features. The application is built using **Python**, **Flask**, **Scikit-learn**, and deployed on **Render**.

---

## 📌 Project Overview

This project uses a trained Machine Learning model to estimate house prices based on various property attributes.

The API accepts property details in JSON format and returns the predicted house price.

---

## 🚀 Tech Stack

- Python 3.x
- Flask
- Scikit-learn
- Pandas
- Pickle
- Gunicorn
- Render (Deployment)

---

## 📂 Project Structure

```
House_Price_Prediction/
│
├── app.py                 # Flask API
├── house_model.pkl        # Trained ML Model
├── requirements.txt       # Project dependencies
├── README.md
└── .gitignore
```

---

## 📊 Features Used for Prediction

The model was trained using the following features:

| Feature | Description |
|----------|-------------|
| Area | Area of the house (sq. ft.) |
| Bedrooms | Number of bedrooms |
| Bathrooms | Number of bathrooms |
| Material_Masonry | 1 = Masonry, 0 = Otherwise |
| Locality_Riverside | 1 = Riverside, 0 = Otherwise |
| Locality_Summit View | 1 = Summit View, 0 = Otherwise |

---

## API Endpoints

### Home

```
GET /
```

Response

```
House Price Prediction API is running!
```

---

### Health Check

```
GET /health
```

Response

```json
{
    "status":"healthy"
}
```

---

### Predict House Price

```
POST /predict
```

Request Body

```json
{
    "Area":1200,
    "Bedrooms":3,
    "Bathrooms":2,
    "Material_Masonry":1,
    "Locality_Riverside":0,
    "Locality_Summit View":1
}
```

Response

```json
{
    "prediction":[250000]
}
```

*(Prediction value shown above is an example.)*

---

## Running Locally

### Clone Repository

```bash
git clone <repository-url>
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Flask App

```bash
python app.py
```

The application will start on

```
http://localhost:8000
```

---

## Deployment

The API is deployed using **Render**.

Deployment includes:

- Flask Application
- Gunicorn Web Server
- Machine Learning Model (.pkl)
- REST API Endpoints

---

## Testing the API

Example using Python

```python
import requests

url = "https://house-deploy-v9oi.onrender.com/predict"

data = {
    "Area": 2500,
    "Bedrooms": 3,
    "Bathrooms": 2,
    "Material_Masonry": 1,
    "Locality_Riverside": 0,
    "Locality_Summit View": 1
}

response = requests.post(url, json=data)

print(response.json())
```

---

## Requirements

```
Flask
gunicorn
pandas
scikit-learn
numpy
```

---

## Future Enhancements

- Web-based User Interface
- Docker Support
- Model Versioning
- CI/CD Pipeline using GitHub Actions
- Cloud Monitoring
- Input Validation
- Interactive Swagger API Documentation

---

## Author

**Atul Mehra**

Certified AI & Machine Learning Professional

---

## License

This project is created for educational and portfolio purposes.
