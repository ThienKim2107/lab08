# SE Lab 10 Summary Report: Software Deployment

**Student Name:** Vo Thi Thien Kim  
**Student ID:** 521h0092  
**Date:** April 22, 2026

---

## 1. Introduction
The purpose of these exercises was to gain hands-on experience with modern software deployment techniques. This included containerization using Docker, orchestration with Docker Compose, automating workflows with CI/CD (GitHub Actions), and deploying to various cloud platforms such as Azure, AWS, and Vercel.

## 2. Exercises Completed

### Exercise 1: Setting up ASP.NET Core applications to support Docker
- **Activity:** Created multi-stage Dockerfiles for both `SchoolAppCoreMVC` and `SchoolAppCoreRazor`.
- **Learning:** I learned how to use the .NET SDK image to build the app and the ASP.NET runtime image to run it, significantly reducing the final image size.

### Exercise 2: Deploy with Docker Desktop on Windows
- **Activity:** Verified Docker installation, built images locally, and ran containers to ensure the applications were reachable at `localhost:8081` and `localhost:8082`.
- **Learning:** Understanding how port mapping (`-p 8080:80`) bridges the host machine and the containerized environment.

### Exercise 3: Deploy to an Ubuntu Server
- **Activity:** Created a `docker-compose.yml` file to manage both app containers simultaneously.
- **Learning:** Docker Compose simplifies managing multi-container applications and environment variables.

### Exercise 4: Automating deployment with CI/CD
- **Activity:** Set up a GitHub Actions workflow (`docker-push.yml`) to automatically build and push images to Docker Hub whenever code is pushed to the repository.
- **Learning:** CI/CD pipelines ensure consistency and speed up the delivery process by removing manual steps.

### Exercise 5 & 6: Cloud Deployment (Azure & AWS)
- **Activity:** Researched and documented the process for deploying containers to Azure App Service and AWS Elastic Beanstalk.
- **Learning:** Cloud providers offer managed container services that provide scalability and high availability.

### Special Exercise: Production Deployment with Vercel
- **Activity:** Investigated Vercel deployment strategies. While Vercel is optimized for frontend, I documented how to connect it via GitHub and the potential for serverless .NET functions.
- **Learning:** Choosing the right hosting service depends on the architecture of the application.

---

## 3. Screenshots

| Step | description | Screenshot Placeholder |
| :--- | :--- | :--- |
| 1 | Dockerfile creation in Visual Studio | [Insert Image Here] |
| 2 | `docker build` command execution | [Insert Image Here] |
| 3 | `docker-compose up` running containers | [Insert Image Here] |
| 4 | GitHub Actions pipeline successful run | [Insert Image Here] |
| 5 | Applications running on localhost | [Insert Image Here] |

---

## 4. Conclusion
This lab provided a comprehensive overview of the software deployment lifecycle. Transitioning from manual deployment to automated containerized workflows is essential for modern software engineering. The most challenging part was ensuring the networking between containers, which was effectively managed by Docker Compose.

---

## 5. Appendix: GitHub Repository Link
[GitHub Repository - Lab 10 Deployment](https://github.com/521h0092-VoThiThienKim/lab08)
