# FastAPI Backend Project

This is a simple FastAPI backend that provides APIs for [KanBeast]. FastAPI is a modern, fast (high-performance), web framework for building APIs with Python 3.

## Prerequisites

Make sure you have the following installed:

- Python 3.7+
- [Pipenv](https://pipenv.pypa.io/en/latest/) or [virtualenv](https://virtualenv.pypa.io/en/latest/) {Optional but recommended}
- [uvicorn](https://www.uvicorn.org/) (ASGI server to serve the FastAPI app) {Optional but recommended}

## Set IT up

1. Set up a virtual environment (optional, but recommended):
    Using `Pipenv`:
    ```bash
    pipenv shell
    ```

    Or using `virtualenv`:
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows use: venv\Scripts\activate
    ```

2. Install the dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Running the Application

1. Make sure you're in [KanBeast_BE] directory.

2. Run the FastAPI app using `uvicorn`:
    ```bash
    uvicorn main:app --reload --port 8002
    ```

    - `main:app`: Points to KanBeast back-end server in the `main.py` file.
    - `--reload`: Enables auto-reloading for development (the server restarts upon code changes).
    - `--port`: Bind to a socket with this port. Default: 8002

3. The application should now be running at:
    ```
    http://127.0.0.1:8002
    ```

4. To view the interactive API documentation, visit:
    - Swagger UI: [http://<127.0.0.1>:8000/docs](http://127.0.0.1:8000/docs)
    - ReDoc: [http://<127.0.0.1>:8000/redoc](http://127.0.0.1:8000/redoc)

## Project Structure
main.py # Main entry point for the FastAPI app

## Testing

1. To run tests, first install `pytest`:
    ```bash
    pip install pytest
    ```

2. Run the test suite:
    ```bash
    pytest
    ```

    You should see test output showing passed or failed tests.

## Deployment

You can deploy the FastAPI app using various platforms. Below are some common options:

### Deploy on Cloud Platforms

- **AWS Lambda**: FastAPI can be deployed on AWS Lambda with [Mangum](https://github.com/jordaneremieff/mangum) {Mangum is an adapter for running ASGI applications in AWS Lambda to handle Function URL, API Gateway, ALB, and Lambda@Edge events.}.
- **Google Cloud**: Use Google App Engine or Cloud Run to deploy your FastAPI app.

### Using Docker

1. Build the Docker image:
    ```bash
    docker build -t kanbeast_be .
    ```

2. Run the container:
    ```bash
    docker run -d --name kanbeast-be-app -p 8002:8002 kanbeast_be
    ```

#### This project is licensed under the GNU General Public License v3.0 - see <p align="center"> <a href="https://github.com/failnot3/KanBeast/blob/main/LICENSE">LICENSE :notebook:</a>  </p>  file for details.

---

### Author

Developed by [Drago Failnot3 Ivanov](https://github.com/failnot3).
