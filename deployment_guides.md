# Software Deployment Guides - Lab 10

This document provides step-by-step instructions for deploying the `SchoolApp` applications to various cloud platforms.

## 1. Microsoft Azure (Recommended for ASP.NET)

### Step 1: Push Image to Azure Container Registry (ACR)
1. Log in to Azure: `az login`
2. Create ACR: `az acr create --resource-group MyRG --name myregistry --sku Basic`
3. Log in to ACR: `az acr login --name myregistry`
4. Tag: `docker tag schoolappcoremvc myregistry.azurecr.io/schoolappcoremvc:v1`
5. Push: `docker push myregistry.azurecr.io/schoolappcoremvc:v1`

### Step 2: Deploy to Azure App Service
1. In Azure Portal, create **Web App for Containers**.
2. Select **Docker** as the image source.
3. Choose your ACR and the image/tag.
4. Set PORT 80 in Configuration.

---

## 2. Amazon Web Services (AWS)

### Step 1: Push to Amazon ECR
1. Create a repository in ECR Console.
2. Authenticate: `aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.us-east-1.amazonaws.com`
3. Tag and Push.

### Step 2: Deploy to AWS Elastic Beanstalk
1. Create a new environment.
2. Choose **Docker** as the platform.
3. Upload a `dockerrun.aws.json` file or use the image URI from ECR.

---

## 3. Vercel (Special Exercise)

Vercel is primarily designed for frontend frameworks. However, you can deploy .NET applications to Vercel using the following methods:

### Option A: Static Site Generation (SSG)
If your application has a decoupled frontend (e.g., React/Vue) and uses .NET as a backend API:
1. Push your frontend code to GitHub.
2. Connect Vercel to your GitHub repository.
3. Vercel will automatically build and deploy the frontend.

### Option B: Serverless Functions (Experimental)
You can use the `@vercel/dotnet` runtime to run .NET serverless functions on Vercel.
1. Create a `vercel.json` file in your project root.
2. Define the runtime for your API endpoints.

```json
{
  "builds": [
    { "src": "api/*.cs", "use": "@vercel/dotnet" }
  ]
}
```

### Option C: Container Deployment (Vercel Alternatives)
If you must use Vercel-like experience for containers, consider **Railway** or **Render**, as Vercel does not natively support long-running Docker containers yet.

---

## 4. Ubuntu Server (Exercise 3)

### Using Docker Compose
1. Transfer the project folder to the server.
2. Ensure Docker and Docker Compose are installed.
3. Run: `sudo docker-compose up -d`
