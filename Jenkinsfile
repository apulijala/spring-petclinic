pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                
                sh '/opt/apache-maven-3.8.6/bin/mvn -B -DskipTests clean package' ;
                archive 'target/*.jar';
                
            }
        }

        stage("Deploy to S3"){
            steps{
                sh 'aws s3 cp target/spring-petclinic-2.7.0-SNAPSHOT.jar s3://datta-unique/' 
            }
            
        }
    }
}
