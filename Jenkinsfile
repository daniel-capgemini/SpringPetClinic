pipeline {
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('Checkout'){
            steps {
                git url: 'https://github.com/daniel-capgemini/SpringPetClinic.git', branch: 'main'
            }
        }
        stage('Build'){
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps {
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps {
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps {
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
