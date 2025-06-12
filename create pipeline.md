

# 🚀 Create Maven Build Pipeline in Azure DevOps

### 🎯 **Aim**

To create a simple **Maven build pipeline** in Azure DevOps that automatically builds Java code from a GitHub repository using Maven.

---

## 🛠️ Prerequisites

* ✅ A **GitHub** account with a Java Maven project (`pom.xml` required)
* ✅ An **Azure DevOps** account
* ✅ A **free Azure DevOps Organization** & project created

---

## 📦 Step-by-Step Procedure

### 🔹 1. Create a GitHub Repository (if not already)

* Push your Java Maven project to **GitHub**
* Ensure your repo contains a valid `pom.xml` file

---

### 🔹 2. Create a Project in Azure DevOps

* Visit: [https://dev.azure.com](https://dev.azure.com)
* Click **New Project**
* Enter a **Project Name** and click **Create**

---

### 🔹 3. Connect Azure DevOps to GitHub

1. In your Azure DevOps Project → go to **Pipelines**
2. Click **Create Pipeline**
3. Select **GitHub** and authorize access
4. Choose your Maven project repository

---

### 🔹 4. Configure the Pipeline (YAML)

Azure may auto-detect your Maven setup. If not, choose **Starter pipeline** and replace the content with:

```yaml
trigger:
- main

pool:
  vmImage: 'ubuntu-latest'

steps:
- task: Maven@3
  inputs:
    mavenPomFile: 'pom.xml'
    goals: 'package'
```

---

### 🔹 5. Save and Run the Pipeline

* Click **Save and Run**
* The pipeline will:

  * Fetch code from GitHub
  * Run `mvn package`
  * Show build status in the logs (success/failure)

---

## ✅ Output

Azure DevOps will:

* Pull your Java Maven project from GitHub
* Execute the Maven build using `mvn package`
* Display logs of the build and test process

---

## 🏁 Result

Successfully created an **automated Maven build pipeline** in Azure DevOps that compiles and packages your Java project whenever code is pushed to the repository 🎉


