# Walletwise

Walletwise is a web-based expense tracking application used to record and analyse personal spending.  
The backend is built using **Node.js**, and **R** is used to generate analytical plots from the stored expense data.

---

## Tech Stack

- Node.js
- R
- PostgreSQL
- Docker (optional, for containerised execution)

---

## How to Run the Application

You can run Walletwise in **two ways**:
1. Using Node.js directly
2. Using Docker

---

## Option 1: Run Using Node.js (Local Setup)

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/Walletwise.git
cd Walletwise
```

---

### 2. Install Node.js dependencies

All backend dependencies are defined in `package.json`.

```bash
npm install
```

---

### 3. Install R dependencies

Install the required R libraries using an R console or RStudio:

```r
install.packages('tidyverse', repos='https://cloud.r-project.org')
install.packages('DBI', repos='https://cloud.r-project.org')
install.packages('RPostgres', repos='https://cloud.r-project.org')
install.packages('dotenv', repos='https://cloud.r-project.org')
```

---

### 4. Configure environment variables

Create a `.env` file in the project root:

```env
DB_HOST=localhost
DB_PORT=5432
DB_NAME=walletwise
DB_USER=your_username
DB_PASSWORD=your_password
```

---

### 5. Start the application

Start the Node.js backend:

```bash
npm start
```

Run the R script for generating plots (example):

```bash
Rscript scripts/generate_plots.R
```

---

## Option 2: Run Using Docker

This method runs the application in a containerised environment using Docker.

### 1. Prerequisites

- Docker
- Docker Compose

---

### 2. Build and start the application

From the project root:

```bash
docker compose up --build
```

This will:
- Build the Node.js application image
- Install all Node.js and R dependencies
- Start the application using the configuration defined in `docker-compose.yml`

---

### 3. Stop the application

```bash
docker compose down
```

---

Both methods run the same application.  
Use **Node.js** for local development and debugging, and **Docker** for consistent, reproducible environments.
