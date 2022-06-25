pipeline {

  agent { label 'kubepod' }

  stages {

    stage('Checkout') {
      steps {
        git url:'https://github.com/SerhiiKravchenko/kube-deploy-app.git', branch:'main'
      }
    }

    stage('Publish') {
      steps {
        script {
          kubernetesDeploy(configs: "kube-deploy-app.yml", kubeconfigId: "mykubeconfigcred")
        }
      }
    }

  }

}