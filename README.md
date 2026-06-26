# ShareKit: Full Stack Social Media App

A full-stack, asynchronous social media application that allows users to securely register, log in, and share image or video posts with text overlays. 

Built with an API-first approach, this project features a high-performance backend serving an interactive web application, demonstrating modern Python development practices, secure authentication, and seamless third-party media handling.

[🎥 Watch the Demo](Demo.mp4)


## 🚀 Key Features

*   **Asynchronous REST API:** Built with FastAPI for high-performance, non-blocking request handling.
*   **Secure Authentication:** JWT-based user registration and login managed via `fastapi-users`, utilizing Argon2/Bcrypt for password hashing.
*   **Media Management:** Integration with ImageKit for efficient media uploading, storage, and on-the-fly transformations (like dynamic text overlay generation).
*   **Interactive UI:** A lightweight, reactive frontend built entirely in Python using Streamlit.
*   **Relational Database:** Asynchronous SQLite database management using SQLAlchemy and `aiosqlite`.

## 🛠️ Tech Stack

*   **Backend:** Python 3.14+, FastAPI, SQLAlchemy, aiosqlite, Pydantic.
*   **Frontend:** Streamlit, Requests.
*   **Services:** ImageKit API (Media Storage & CDN).
*   **Dependency Management:** `uv` / `pyproject.toml`.

## 📂 Project Structure

```text
├── app/
│   ├── app.py          # FastAPI application factory and main routes
│   ├── db.py           # SQLAlchemy async engine, session maker, and ORM models
│   ├── images.py       # ImageKit configuration and initialization
│   ├── schemas.py      # Pydantic models for validation
│   └── users.py        # Authentication backend and user management
├── frontend.py         # Streamlit user interface
├── main.py             # Uvicorn entry point
├── pyproject.toml      # Project metadata and dependencies
└── .env                # Environment variables
```

## 🗺️ Roadmap & Future Scope

- Migration to PostgreSQL: Transition the database from SQLite to PostgreSQL for robust production-ready concurrency.
- CI/CD Pipeline: Implement GitHub Actions to run automated testing and linting on every pull request.
- Automated Testing: Increase test coverage using pytest and httpx for backend endpoint verification.
- Social Features: Add the ability for users to "like" and comment on media posts.

## ⚙️ Local Setup & Installation

### 1. Prerequisites

Before you begin, ensure you have the following installed:

- Python 3.14 or higher
- `uv` (an extremely fast Python package and project manager)
- An ImageKit.io account (to obtain your API keys for media storage)

### 2. Clone the Repository

```bash
git clone <repository-url>
cd <repository-name>
```

### 3. Configure Environment Variables

Create a `.env` file in the project root and add your ImageKit credentials:

```env
IMAGEKIT_PRIVATE_KEY=your_private_key_here
IMAGEKIT_PUBLIC_KEY=your_public_key_here
IMAGEKIT_URL=your_imagekit_url_endpoint_here
```

### 4. Install Dependencies

Install all project dependencies using:

```bash
uv sync
```

### 5. Run the Application

ShareKit requires both the FastAPI backend and the Streamlit frontend to be running simultaneously. Open two separate terminal windows.

**Terminal 1 – Start the FastAPI backend**

```bash
uv run ./main.py
```

**Terminal 2 – Start the Streamlit frontend**

```bash
python -m streamlit run frontend.py
```