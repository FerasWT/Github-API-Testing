# GitHub API Testing with Postman & Newman 🚀

This repository demonstrates **automated GitHub API testing** using **Postman**, **Newman**, and **GitHub Actions**. The workflow runs API tests securely using GitHub Secrets and can be triggered manually.

---

## 📌 Features

* ✅ GitHub API tests built with Postman
* 🔁 Automated execution using Newman
* 🔐 Secure token handling via GitHub Secrets
* ⚙️ CI/CD integration with GitHub Actions
* ▶️ Manual workflow trigger (`workflow_dispatch`)

---

## 🧰 Tech Stack

* **Postman** – API test creation
* **Newman** – CLI runner for Postman collections
* **GitHub Actions** – CI pipeline
* **Node.js / npm** – Newman installation

---

## 📂 Project Structure

```
.
├── GitHubAPI.postman_collection.json
├── .github/
│   └── workflows/
│       └── github-api-testing.yml
└── README.md
```

---

## 🔐 Required Secrets

Create the following secret in your repository:

* **TOKEN** → Your GitHub Personal Access Token (PAT)

Steps:

1. Go to **Repository Settings**
2. Open **Secrets and variables → Actions**
3. Click **New repository secret**
4. Name: `TOKEN`
5. Value: *Your GitHub PAT*

---

## ▶️ How to Run the Tests

### Option 1: GitHub Actions (Recommended)

1. Go to the **Actions** tab
2. Select **GitHub API Testing** workflow
3. Click **Run workflow**

### Option 2: Run Locally

```bash
npm install -g newman
newman run GitHubAPI.postman_collection.json \
  --global-var "GitHub_Token=YOUR_TOKEN" \
  --global-var "base_url=https://api.github.com" \
  --global-var "owner=FerasWT" \
  --global-var "repo=api-testing-demo" \
  --global-var "Issue_Number=4"
```

---

## 🧪 Environment Variables Used

| Variable       | Description                  |
| -------------- | ---------------------------- |
| `GitHub_Token` | GitHub Personal Access Token |
| `base_url`     | GitHub API base URL          |
| `owner`        | GitHub repository owner      |
| `repo`         | GitHub repository name       |
| `Issue_Number` | Issue ID for testing         |

---

## 📝 Notes & Best Practices

* Never hardcode tokens in collections or workflows
* Always use **GitHub Secrets** for sensitive data
* Avoid spaces in Postman variable names

---

## 👤 Author

**Feras Waleed Turkestani**
Software Tester / QA Engineer

---

## 📄 License

This project is for learning and testing purposes.
