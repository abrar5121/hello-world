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
                    sh ' mvn clean install '
                    
                    }
                }
            }
            

          
    }
}

