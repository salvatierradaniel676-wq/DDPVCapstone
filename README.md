# 🌾 Crop Recommendation API

Welcome to the Crop Recommendation API — a machine learning-powered REST API that helps farmers and agri-tech systems choose the **best crop** and **recommended fertilizer** based on soil and weather conditions.

Built using **FastAPI**, this backend service loads trained ML models and serves smart predictions at lightning speed.

---

## 🚀 What Can This API Do?

- 🌱 Suggest the most suitable crop based on your inputs
- 🌾 Recommend the right fertilizer for your field
- 📘 Comes with built-in interactive documentation
- 🐳 Supports Docker for easy deployment
- 🔄 Auto-reloads in development for faster updates

---

## 🧠 How Smart is It?

This project uses a mix of powerful machine learning models, including:

- 🧠 Decision Tree
- 🌳 Random Forest
- 🚀 XGBoost

> These models are trained in advance and stored in the `Models/` folder as `.pkl` files.

---

## 🧰 Tech Stack

Here’s what powers the Crop Recommendation API:

- **FastAPI** – For the backend
- **Uvicorn** – To run the FastAPI app
- **scikit-learn** – For ML model creation
- **XGBoost** – For high-performance gradient boosting
- **pydantic** – For request validation
- **Docker** – For containerization and deployment

---

## 💻 How to Run the Project

You can run this project in two ways: **locally using Python** or **using Docker**.

---

### 🧪 Option 1: Run Locally with Python

#### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/crop-recommendation-api.git
cd crop-recommendation-api
```

#### Step 2: Set Up a Virtual Environment

```bash
python -m venv venv
```

Then activate it:

- On **Windows**:
  ```bash
  venv\Scripts\activate
  ```

- On **macOS/Linux**:
  ```bash
  source venv/bin/activate
  ```

#### Step 3: Install Required Libraries

```bash
pip install -r requirements.txt
```

#### Step 4: Run the Server

```bash
uvicorn app:app --reload
```

Once running, open your browser and go to:

- 🌐 API Base URL: [http://localhost:8000](http://localhost:8000)
- 📘 API Docs (Swagger UI): [http://localhost:8000/docs](http://localhost:8000/docs)

---

### 🐳 Option 2: Run Using Docker

#### Step 1: Build the Docker Image

```bash
docker build -t crop-recommendation-api .
```

#### Step 2: Run the Docker Container

```bash
docker run -d -p 8000:8000 --name crop-api crop-recommendation-api
```

Visit: [http://localhost:8000/docs](http://localhost:8000/docs) to try out the API interactively.

---

## 🔍 How to Use the API

### Endpoint: `POST /crop_recommendation/`

Send a JSON body like this:

```json
{
  "nitrogen": 90,
  "phosphorus": 42,
  "potassium": 43,
  "temperature": 23.5,
  "humidity": 60,
  "ph": 6.5,
  "rainfall": 110
}
```

#### Example using `curl`:

```bash
curl -X POST "http://localhost:8000/crop_recommendation/" \
-H "accept: application/json" \
-H "Content-Type: application/json" \
-d '{
  "nitrogen": 90,
  "phosphorus": 42,
  "potassium": 43,
  "temperature": 23.5,
  "humidity": 60,
  "ph": 6.5,
  "rainfall": 110
}'
```

Expected response:

```json
{
  "recommended_crop": "rice",
  "recommended_fertilizer": "urea"
}
```

> 🛑 Make sure the field names are **exact** — for example, use `"phosphorus"` (not `"phosphorous"`).

---

## 🧪 Test in Your Browser

Thanks to FastAPI, you get automatic docs.

Just open [http://localhost:8000/docs](http://localhost:8000/docs) in your browser and try it out visually. No need for Postman!

---

## 🗂 Project Structure

```
crop-recommendation-api/
├── app.py
├── Models/
│   ├── crop_model.pkl
│   ├── fertilizer.pkl
│   └── encoder.pkl
├── requirements.txt
├── Dockerfile
└── README.md
```

---

## 🛠 Troubleshooting

- **422 Validation Error?**
  - Make sure all fields are present and spelled correctly.
  - Example: `"phosphorus"` is required, not `"phosphorous"`.

- **ModuleNotFoundError (like xgboost)?**
  - Just install it:
    ```bash
    pip install xgboost
    ```

- **Model not loading?**
  - Ensure `.pkl` files exist in the `Models/` directory.

---

## 📜 License

This project is open-source under the [MIT License](LICENSE).

---

## 🤝 Contributions Welcome

Found a bug? Have a feature idea? Open an issue or send a pull request — contributions are highly appreciated!
