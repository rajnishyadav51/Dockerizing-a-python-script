# Dockerized Python Data Processor

## Project Overview

This project demonstrates how to containerize a Python application using Docker.

The application reads data from a CSV file using the pandas library and displays statistical information about the dataset. By running the application inside a Docker container, the same environment can be reproduced on any machine without manually installing Python or its dependencies.

---

## Technologies Used

- Docker
- Python 3.9
- Pandas
- CSV

---

## Project Structure

```text
docker-python-data-processor/
│
├── Dockerfile
├── process_data.py
├── data.csv
├── requirements.txt
├── README.md
└── screenshots/
```

---

## Application Workflow

1. Read employee data from `data.csv`
2. Load the data using pandas
3. Generate summary statistics using `describe()`
4. Display the output in the terminal

---

## data.csv

```data.csv
Name,Age,Salary
Rahul,25,30000
Amit,30,50000
Neha,28,45000
Ankit,35,60000
```

---

## process_data.py

```process_data.py
import pandas as pd
df = pd.read_csv('data.csv')
print(df.describe())
```

---

## requirements.txt

```requirements.txt
pandas
```

---

## Dockerfile

```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "process_data.py"]
```

---

## Build Docker Image

```bash
docker build -t python-script .
```

---

## Run Docker Container

```bash
docker run python-script
```

---

## Expected Output

The script displays summary statistics for the numeric columns in the dataset.

Example:

```text
             Age   Salary
count   4.000000      4.0
mean   29.500000  46250.0
std     4.203173  12500.0
min    25.000000  30000.0
25%    27.250000  41250.0
50%    29.000000  47500.0
75%    31.250000  52500.0
max    35.000000  60000.0
```

---

## Screenshots

### Project Structure

![Project Structure](screenshots/01-project-directory.png)

---

### Docker Image Build

![Docker Build](screenshots/02-docker-build.png)

---

### Running the Container

![Run Container](screenshots/03-run-container.png)

---

### Application Output

![Output](screenshots/04-output.png)

---

## Learning Outcomes

Through this project I learned how to:

- Containerize Python applications
- Use Docker with Python
- Manage dependencies using `requirements.txt`
- Create lightweight Docker images
- Execute Python scripts inside containers
- Work with CSV files using pandas

---

## Acknowledgement

This project was implemented while practicing Docker concepts through KodeKloud. The implementation, documentation, and repository structure have been prepared by me for my personal learning portfolio.

---

## Author

**Rajnish Yadav**

GitHub: https://github.com/yadavrajnish51

