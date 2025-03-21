---
title: Get Started
deprecated: false
hidden: false
metadata:
  robots: index
---
## 🛠 What's Inside the Box?

This kit comes fully loaded with everything you need to start your backend adventures:

* **FastAPI**: The cool, modern web framework that's got speed in its DNA. Think of it as the Flash of web frameworks.
* **PostgreSQL**: The trusty ol' database that never lets you down. It's like the Gandalf of databases – wise, powerful, and always there when you need it.
* **Poetry**: Not the kind that makes you ponder life's mysteries, but the kind that makes managing Python dependencies as smooth as butter.
* **Docker**: Because who doesn't love shipping containers? 🚢
* **Alembic**: The migration tool that handles your database changes with grace and ease.
* **SQLAlchemy Models**: Built-in SQL models for a smooth and powerful ORM experience, making your database interactions clean and Pythonic.

## 🎓 Development Setup (For the Rebels)

If you want to run this project, here's what you need to do:

**Install Dependencies**

Poetry to the rescue(use 'brew install poetry'):

```bash
poetry install
```

Install Solana CLI via this [link](https://solana.com/docs/intro/installation#install-the-solana-cli) and run the solana local validator to create wallets/topup balance/run payments

```bash
solana-test-validator
```

**Run the Postgres database using docker**

```bash
docker-compose up --build
```

## 🗄 Database Migrations

Use pip to install alembic if not already,

```bash
pip install alembic
```

Run the below command from the project root folder to make sure the database migrations are applied to your postgres docker instance

```bash
alembic upgrade head
```

Just like that, your database is up to date. 🎉

**Run the Application**

Fire up the app with Uvicorn (use 'brew install uvicorn' to install uvicorn cli):

```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 4000
```

You're all set to code like a rockstar. 🎸

**Access the Application**

Boom! Your FastAPI application is live at [http://localhost:4000](http://localhost:4000). Go ahead, give it a whirl!

Swagger docs - [http://localhost:4000/docs](http://localhost:4000/docs)