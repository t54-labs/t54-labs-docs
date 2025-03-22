---
title: tLedger Backend Sandbox
deprecated: false
hidden: false
metadata:
  robots: index
---
# tLedger Backend

## 🛠 What's Included?

This toolkit contains all the essentials to quickly get started with your backend development:

* **FastAPI**: A modern, high-performance web framework built for speed and reliability.
* **PostgreSQL**: A robust, reliable database solution perfect for secure data storage.
* **Poetry**: Effortless Python dependency management, simplifying your project's setup.
* **Docker**: Containerization technology to ensure consistent deployment across environments.
* **Alembic**: Seamless database migration tool to manage schema changes effectively.
* **SQLAlchemy Models**: Powerful and intuitive ORM models for clean and efficient database interactions.

## 🎓 Development Setup

Follow these steps to set up the tLedger Backend on your local environment:

### Step 1: Install Dependencies

Ensure you have [Poetry](https://python-poetry.org/docs/) installed. If not, install using Homebrew:

```bash
brew install poetry
```

Install project dependencies:

```bash
poetry install
```

Install the Solana CLI from [here](https://solana.com/docs/intro/installation#install-the-solana-cli), then start the Solana local validator for wallets, balance management, and transaction testing:

```bash
solana-test-validator
```

### Step 2: Launch PostgreSQL Database

Run the PostgreSQL database locally using Docker:

```bash
docker-compose up --build
```

### Step 3: Database Migrations

Install Alembic (if not installed already):

```bash
pip install alembic
```

Apply the latest database migrations:

```bash
alembic upgrade head
```

Your database is now up to date.

### Step 4: Run the Application

Start the FastAPI application server using Uvicorn (install Uvicorn via Homebrew if needed):

```bash
brew install uvicorn
uvicorn app.main:app --reload --host 0.0.0.0 --port 4000
```

The application is now live and ready for development.

### Step 5: Access the Application

Your FastAPI application is accessible at:

* Application: [http://localhost:4000](http://localhost:4000)
* Swagger Docs: [http://localhost:4000/docs](http://localhost:4000/docs)

You are now fully set up to develop and test your backend services!