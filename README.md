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

### Option 1: Run Using Node.js (Local Setup)

1. Clone the repository:

```bash
git clone https://github.com/<your-username>/Walletwise.git
cd Walletwise
```

2. Install Node.js dependencies:

```bash
npm install
```

3. Install R dependencies (run in an R console or RStudio):

```r
install.packages('tidyverse', repos='https://cloud.r-project.org')
install.packages('DBI', repos='https://cloud.r-project.org')
install.packages('RPostgres', repos='https://cloud.r-project.org')
install.packages('dotenv', repos='https://cloud.r-project.org')
```

4. Configure environment variables by creating a `.env` file in the project root:

```env
DB_HOST=localhost
DB_PORT=5432
DB_NAME=walletwise
DB_USER=your_username
DB_PASSWORD=your_password
```

5. Start the application:

```bash
npm start
```

Run the R script for generating plots:

```bash
Rscript scripts/generate_plots.R
```

---

### Option 2: Run Using Docker

1. Prerequisites:

- Docker

2. Build the Docker image:

```bash
docker build -t walletwise .
```

This will:
- Build a Docker image using the provided `Dockerfile`
- Install Node.js and all Node.js dependencies
- Install R and required system dependencies

3. Run the Docker container:

```bash
docker run -p 8080:8080 walletwise
```

This will:
- Start the Node.js application inside the container
- Expose the application on port `8080`

4. Stop the application:

Press `Ctrl + C` in the terminal or stop the container manually:

```bash
docker ps
docker stop <container_id>
```

---

Both methods run the same application.  
Use **Node.js** for local development and debugging, and **Docker** for a consistent, reproducible environment.
