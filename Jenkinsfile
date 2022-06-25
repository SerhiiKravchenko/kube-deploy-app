pipeline {

  agent { label 'kubepod' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/SerhiiKravchenko/kube-deploy-app.git', branch:'main'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "kube-deploy-app.yml", kubeconfigId: "mykubeconfigcred")
        }
      }
    }

  }

}