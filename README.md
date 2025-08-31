# Lesson 23 – Final Project: Weather Web App 🌦️

## What I Did
- Built a **Python Flask web app** to fetch and display current weather conditions.
- Connected to the **OpenWeatherMap API** with an API key stored securely in a `.env` file (loaded using `python-dotenv`).
- Structured the project into clear parts:
  - **`weather.py`** → Handles API requests and returns JSON data.
  - **`app.py`** → Flask routes and application logic.
  - **Templates** → `index.html` (input form), `weather.html` (results), `city-not-found.html` (error page).
  - **Static files** → CSS styles for frontend design.
- Used **Waitress** WSGI server for running the app (instead of Flask’s default development server).

---

## How It Works
1. User visits `/` or `/index` → presented with a form to enter a city.
2. On submission → Flask calls `/weather`:
   - Reads the city from the form input.
   - Calls `get_current_weather(city)` from `weather.py`.
   - Handles edge cases:
     - Empty input → defaults to **London**.
     - Invalid city (`cod != 200`) → shows `city-not-found.html`.
   - For valid cities:
     - Extracts data (status, temperature, feels-like).
     - Passes data into `weather.html` template for display.
3. App is served locally with Waitress on port **8000**.

---

## What I Learned
- How to **integrate Flask with an external API**.
- Best practices for **storing API keys** securely with `.env` files.
- Using **Flask templates** (`render_template`, Jinja2) to display dynamic data.
- Deploying Flask with a **production-ready server** (Waitress).
- Writing code with **clear separation of concerns** between logic, routes, and frontend.

---

## Reflection
This project tied together everything I learned in previous lessons:
- **Backend**: Python with Flask + Requests.
- **Frontend**: HTML templates + CSS.
- **API Integration**: OpenWeatherMap with secure environment variables.

It gave me my **first taste of a real full-stack app**. While simple, it demonstrates:
- API consumption
- Input validation & error handling
- Passing dynamic data to templates

This was a solid capstone for the course and a great foundation for more complex web apps.

---

## 🚀 How to Run
1. Clone the repo and enter the folder:
   ```bash
   git clone https://github.com/hkeays09/Python-Beginner-Course.git
   cd Python-Beginner-Course/Lesson23-FinalProject
