pipeline {
   agent any

   stages {
      stage('Checkout SCM') {
         steps {
            git 'https://github.com/tapenderk/jenkins_tutorial.git'
         }
      }
      stage('build') {
         steps {
            sh "./build.sh"
         }
      }
   }
}
