# 🍽️ Restaurant Recommendation System

## 📌 Project Overview
This project is a **content-based restaurant recommendation system** built using Python and Machine Learning techniques.  
It helps users discover restaurants based on their preferences such as cuisine, location, price range, rating, and other features.

The system uses **cosine similarity** to find and recommend restaurants similar to the user’s input preferences.

---

## 🎯 Business Problem
Users often struggle to choose the best restaurant from thousands of available options.  
The goal of this project is to build a smart recommendation system that suggests restaurants based on:

- Cuisine preference  
- City / locality  
- Price range  
- Ratings and reviews  
- Availability of services (delivery, table booking, etc.)

---

## 🧠 Solution Approach
A **Content-Based Filtering** approach is used:

1. Preprocess restaurant dataset
2. Encode categorical and numerical features
3. Convert text (location) using TF-IDF
4. Convert cuisines using MultiLabelBinarizer
5. Normalize numerical features
6. Combine all features into a single feature matrix
7. Compute cosine similarity
8. Recommend top similar restaurants

---

## 📊 Dataset Features Used

- Restaurant Name  
- Cuisines  
- Average Cost for Two  
- Price Range  
- Aggregate Rating  
- Votes  
- Rating Color  
- Rating Text  
- Has Table Booking  
- Has Online Delivery  
- Is Delivering Now  
- Locality (TF-IDF encoded)  

---

## ⚙️ Technologies Used

- Python 🐍  
- Pandas  
- NumPy  
- Scikit-learn  
- SciPy  
- Matplotlib  
- Seaborn  

---

## 🔧 Data Preprocessing Steps

### 1. Handling Missing Values
- Missing values in **Cuisines** are filled using mode.

### 2. Encoding Categorical Variables
- Binary encoding for:
  - Has Table Booking
  - Has Online Delivery
  - Is Delivering Now

- Ordinal encoding for:
  - Rating Color
  - Rating Text

### 3. Feature Engineering
- Cuisines → MultiLabelBinarizer (multi-hot encoding)
- Locality Verbose → TF-IDF Vectorization

### 4. Feature Scaling
- StandardScaler applied on:
  - Average Cost for Two  
  - Price Range  
  - Aggregate Rating  
  - Votes  

---

## 📌 Model Building

### Step 1: Feature Matrix Creation
All processed features are combined using:

- Sparse numerical features  
- Cuisine encoding  
- TF-IDF location vectors  

### Step 2: Similarity Calculation
Cosine Similarity is used:

- Measures similarity between restaurants  
- Based on user preference vector vs dataset  

---

## 🍴 Recommendation Function

The system provides recommendations using:

```python
recommend_restaurants(
    locality_verbose,
    average_cost,
    has_table_booking,
    has_online_delivery,
    is_delivering_now,
    price_range,
    aggregate_rating,
    rating_color,
    rating_text,
    votes,
    cuisines
)
