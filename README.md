# Jenkins
<h1><br> This is the Fist Jenkins Pipelin Code for test <br><h1>
<br>For start the New Jenkins Pipeline first we need to login to our Jenkins using our Jenkins IP and Password <br>
<br>After login to the Jenkins we need to give an item name and select type as Pipeline then click okay<br>

#Sample Pipeline
<br>
'''bash
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

'''

