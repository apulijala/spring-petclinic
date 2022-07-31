pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh '/opt/apache-maven-3.8.6/bin/mvn -B -DskipTests clean package' 
            }
        }

        stage("Deploy to S3"){
            steps{
                sh 'aws s3 ls' 
            }
            
        }
    }
}
