pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage('Git-Checkout'){
            steps{
                git url: 'https://github.com/siasankalpsiripuram/HomeRepo.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean install package'
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'Tomcat-User', path: '', url: 'http://54.210.201.159:8090/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
