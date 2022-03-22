pipeline {
   agent any

   stages {
      stage('build') {
         steps {
            sh "./build.sh"
         }
      }
      stage ('build-docker') {
         steps{
            sh '''
               mkdir -p tmp-dir
               docker build --pull -t ubuntu-dotnet:latest -f Dockerfile tmp-dir
            '''
         }
      }
         stage ('use-docker') {
            agent {
               docker{
                  image 'ubuntu-dotnet:latest'
               }
            }
            steps{
               sh'dotnet --version'
            }
        }   
    }   
}
