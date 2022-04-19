pipeline {
    agent any

    stages {
        stage('Branch-Name-Print') {
            steps {
                echo 'Branch is dev'
            }
        }
    }
	post {
        always {
            echo "Cleaning Workspace After Pipeline Execution"
            cleanWs()
            deleteDir() /* Cleaning up Workspace */
        }
    }
}
