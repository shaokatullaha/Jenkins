# Jenkins Pipeline – Full Stack CRUD Project (React + Node + MySQL)

This repository contains a sample **Jenkins Pipeline** that clones a full-stack CRUD project built with **React, Node.js, and MySQL** from GitHub.

---

## 🚀 Overview

This Jenkins Pipeline demonstrates how to:
- Connect Jenkins to a GitHub repository
- Clone a specific branch
- Verify repository contents via shell commands

---

## 🧩 Jenkins Pipeline Code

```groovy
pipeline {
    agent any

    environment {
        GIT_REPO_LINK = 'https://github.com/mahadihassanrazib/full-stack-crud-project-with-react-node-mysql.git'
        REPO_BRANCH = 'main'
    }

    stages {
        stage("Clone Repository") {
            steps {
                echo "Cloning Repository from ${GIT_REPO_LINK} (branch: ${REPO_BRANCH})"
                git branch: "${REPO_BRANCH}", url: "${GIT_REPO_LINK}"
                sh "ls -lah"
            }
        }
    }
}

