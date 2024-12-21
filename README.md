# Human and Wild Animal Classifier Web Running Application

This project is a web-based image classifier that uses a pre-trained Keras model to distinguish between human and animal faces. The application is built using Django, and it can be run both locally and within a Docker container.

The model is based on [yegekucuk/classifier1](https://github.com/yegekucuk/classifier1) project on GitHub.

## Installation Methods

### 1. Downloading the Docker Image (Recommended Method)
You can download the image from DockerHub and run the application in a Docker container. For this option you don't have to clone the repository on your local machine

#### Prerequisites

- Docker installed on your machine.

#### Steps
1. Build the Docker image:
    ```bash
    docker pull yegekucuk2/classifier
    ```

2. Run the Docker container:
    ```bash
    docker run --name classifier -d -p 80:8000 yegekucuk2/classifier
    ```
3. Access the application by navigating to `http://127.0.0.1` in your web browser.
4. You can stop and remove the application with the following command:
    ```bash
    docker rm -f classifier
    ```

### 2. Building with Docker

You can build the image on your own.

#### Prerequisites

- Docker installed on your machine.

#### Steps

1. Clone the repository:
    ```bash
    git clone https://github.com/yegekucuk/classifier1-on-web.git
    cd classifier1-on-web
    ```
2. Build the Docker image:
    ```bash
    docker build -t classifierimage .
    ```

3. Run the Docker container:
    ```bash
    docker run --name classifier -d -p 80:8000 classifierimage
    ```
4. Access the application by navigating to `http://127.0.0.1` in your web browser.

5. You can stop and remove the application with the following command:
    ```bash
    docker rm -f classifier
    ```

### 3. Running Locally with Python

You can also run the application directly on your local machine.

#### Prerequisites

- Python 3.x and Pip installed on your environment.

#### Steps

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/classifier1-on-web.git
    cd classifier1-on-web
    ```
2. Create a virtual environment and activate it:
    ```bash
    python3 -m venv env
    source env/bin/activate  # On Windows use `env\\Scripts\\activate`
    ```
3. Install the packages:
    ```bash
    pip install -r requirements.txt
    ```
4. Apply migrations and start the Django development server:
    ```bash
    python manage.py migrate
    python manage.py runserver
    ```
5. Access the application by navigating to `http://localhost:8000` in your web browser.

## Project Structure

### Project Files

- **classifier/**: Django application handling image uploads and predictions.
- **project/**: Django project settings and configurations.
- **kube/**: Kubernetes deployment files.
- **Dockerfile**: Instructions to build the Docker image.
- **Jenkinsfile**: CI pipeline configuration.
- **requirements.txt**: Python dependencies required by the project.
- **model.h5**: Pre-trained Keras model used for image classification.

### CI/CD Operations

- **Jenkins**: For CI operations, Jenkins tool is used on Kubernetes cluster.
- **ArgoCD**: For CD operations, ArgoCD tool is used on Kubernetes cluster.

### Model training
The pre-trained model is used. For the main repository of the model [click here](https://github.com/yegekucuk/classifier1).

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
