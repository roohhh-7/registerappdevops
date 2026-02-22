pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java21'
    maven 'Maven3' 
  }
  stages{
    stages { "Cleanup Workspace"}{
        steps {
        cleanWs()
        }
    }
    stage("Checkout from SCM"){
        steps {
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/roohhh-7/registerappdevops'
        }
    }
    stage( "Build Application"){
        steps{
        sh "mvn clean package"
        }
    }
    stage("Test Application"){
        steps{
              sh "mvn test"
        }
    }
  }      
}
