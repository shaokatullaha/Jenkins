# Jenkins Pipeline – Full Stack CRUD Project (React + Node + MySQL)

This repository contains a **Jenkins Pipeline** that clones a full-stack CRUD project built with **React, Node.js, and MySQL** from GitHub.  

The pipeline now includes **post-build actions** to handle success, failure, and cleanup.

---

## 🚀 Overview

This Jenkins Pipeline demonstrates how to:
- Connect Jenkins to a GitHub repository
- Clone a specific branch using credentials
- Verify repository contents
- Run post-build actions: success, failure, and workspace cleanup

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
                git branch: "${REPO_BRANCH}", url: "${GIT_REPO_LINK}", credentialsId: 'github-credentials'
                sh "ls -lah"
            }
        }
    }

    post {
        always {
            echo "This will always run after the stages complete."
            echo "Cleaning up workspace..."
            cleanWs()
        }
        failure {
            echo "The build has failed. Please check the logs for details."
        }
        success {
            echo "The build was successful!"
        }
    }
}
```


## 🧑‍💻 Author

**Md Shaokat Ullaha**  
Senior Systems Engineer | DevOps & Cloud Expert  

📧 [contact@shaokat.me](mailto:contact@shaokat.me)  
🌐 [LinkedIn](https://www.linkedin.com/in/shaokat-ullaha) | [GitHub](https://github.com/shaokat)