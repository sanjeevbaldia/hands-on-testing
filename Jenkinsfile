pipeline {
  agent {
    node {
      label any
    }
  }

  triggers {
    pollSCM 'H/2 * * * *'
  }

  stages {
    stage('checkout') {
      steps {
        checkout scm: [$class: 'GitSCM',
          userRemoteConfigs: [[url: "https://github.com/sanjeevbaldia/hands-on-testing.git"]],
                              branches: [[name: "refs/heads/$BRANCH_NAME"]]
        ], poll: true
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
