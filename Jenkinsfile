pipeline {

  agent { label 'kubepod' }

  stages {

    stage('Checkout') {
      steps {
        git url:'https://github.com/SerhiiKravchenko/kube-deploy-app.git', branch:'main'
      }
    }

    stage('Deploy') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}