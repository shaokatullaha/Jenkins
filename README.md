# Jenkins

## This is the First Jenkins Pipeline Code for Test

For starting a new Jenkins Pipeline, first we need to:
1. Login to Jenkins using the Jenkins IP and password.  
2. After login, provide an **item name**, select **type: Pipeline**, and click **OK**.

---

### 🧩 Sample Pipeline

```groovy
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}