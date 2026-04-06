# 🚀 Introduction to CI/CD Pipelines

A foundational guide to understanding how modern software teams automate the journey from code to production.

---

## 🛠 What is CI/CD?

**CI/CD** is a method of frequently delivering apps to customers by introducing automation into the stages of app development. It bridges the gap between development and operations teams.

### The Three Pillars
* **Continuous Integration (CI):** Developers merge code daily. Every push triggers an automated **build and test** to catch bugs early.
* **Continuous Delivery (CD):** The code is always in a "deployable" state. The final release to production is ready but usually requires a **manual approval**.
* **Continuous Deployment (CD):** Every change that passes the automated tests is **automatically released** to production with no human intervention.

---

## 🏗 The Pipeline Flow

A standard pipeline follows these logical steps:

1.  **Source:** Triggered when you push code to GitHub.
2.  **Build:** The application is compiled (e.g., creating a Docker image or an executable).
3.  **Test:** Automated suites (Unit, Integration, Linting) verify the code works.
4.  **Deploy:** The "clean" code is moved to a server or cloud provider (AWS, Vercel, etc.).

---

## 📈 Why It Matters
* **Speed:** Ship features to users faster.
* **Safety:** Automated tests act as a safety net for your code.
* **Reliability:** Eliminates the "it works on my machine" excuse by using standardized build environments.

---

## ⚡ Quick Example: GitHub Actions
GitHub uses YAML files to define pipelines. Here is a simple CI configuration:

```yaml
name: CI Workspace
on: [push]
jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Install Dependencies
        run: npm install
      - name: Run Tests
        run: npm test
