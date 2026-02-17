# Register App

A Java-based web application designed for DevOps learning purposes. This project demonstrates a multi-module Maven architecture, integrating various DevOps tools and practices.

## 🚀 Features

- **User Registration**: A simple web interface for user registration.
- **Multi-Module Maven Project**: Separated into `server` (logic) and `webapp` (UI) modules.
- **CI/CD Ready**: Includes a `Jenkinsfile` for automated building, testing, and deployment.
- **Containerization**: Docker support for easy containerized deployment.
- **Code Quality**: Integrated with SonarQube for static code analysis.

## 🛠️ Tech Stack

- **Language**: Java 17
- **Build Tool**: Maven 3
- **Frontend**: JSP (JavaServer Pages), HTML, CSS
- **Testing**: JUnit, Mockito
- **DevOps**: Jenkins, Docker, SonarQube

## 📂 Project Structure

```
register-app/
├── server/     # Backend logic and unit tests
├── webapp/     # Web application (JSP) and WAR packaging
├── Jenkinsfile # CI/CD Pipeline configuration
├── Dockerfile  # Docker image configuration
└── pom.xml     # Root Maven configuration
```

## ⚙️ prerequisites

- Java Development Kit (JDK) 17 or higher
- Maven 3.x
- Docker (optional, for containerization)

## 🏗️ Build and Run

### Locally with Maven and Jetty

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Ashfaque-9x/register-app.git
   cd register-app
   ```

2. **Build the project:**
   ```bash
   mvn clean install
   ```

3. **Run the web application:**
   ```bash
   # Run from the root directory
   mvn jetty:run -pl webapp
   ```
   Access the application at `http://localhost:8080/webapp`.

### Using Docker

1. **Build the Docker image:**
   ```bash
   docker build -t register-app .
   ```

2. **Run the container:**
   ```bash
   docker run -p 8080:8080 register-app
   ```

## 🔄 CI/CD Pipeline

The project includes a `Jenkinsfile` that defines the following stages:
1. **Cleanup**: Cleans the workspace.
2. **Checkout**: Pulls code from SCM.
3. **Build**: Runs `mvn clean package`.
4. **Test**: Runs unit tests (`mvn test`).
5. **Analysis**: Performs SonarQube analysis.
6. **Docker Build & Push**: Builds and pushes the Docker image.
7. **Security Scan**: Scans the image using Trivy.
8. **Deploy**: Triggers a CD pipeline.

## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request.
