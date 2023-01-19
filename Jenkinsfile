pipeline {
    agent any
    stages {

        stage (" know the present workind directory"){
             steps{
                script{
                    sh ' pwd '
                }
             }
        }
        
        stage(' find out what present') {
            steps{
                script{
                   sh  '''
                     export MAVEN_HOME=/opt/apache-maven-3.6.3
                     export PATH=$PATH:$MAVEN_HOME/bin
                     mvn --version

                     mvn clean install 

                     '''
                    
                    }
                }
            }
            

          
    }
}

