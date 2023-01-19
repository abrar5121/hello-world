pipeline {
    agent any
    stages {
        stage('Source Code checkout') { 
            steps {
                script{
                     
                     git credentialsId: 'b3aa92df-cbee-41bd-ae08-96e4681cb51b', url: 'https://github.com/Bharath5131/hello-world.git' 
                }

            }
        } 

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
                    sh '''
                    export MAVEN_HOME=/opt/maven
                    export PATH=$PATH:$MAVEN_HOME/bin
                    mvn --version
                    mvn clean install
                    '''
                    }
                }
            }
            
        stage(' Deploy the war package on tomcat server ') {
            steps{
                script{
                    sshagent(['DEPLOY']) {
                sh " scp -o StrictHostKeyChecking=no webapp/target/webapp.war ubuntu@34.205.146.153:/opt/tomcat/webapp "
                
                }
                }
            }
        }
        


    }
          
    }
