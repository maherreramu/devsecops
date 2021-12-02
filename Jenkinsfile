pipeline{
    agent any
    
    stages{
        stage('cloning git'){
            git 'https://github.com/maherreramu/devsecops.git'
        }
        stage('sonar analysis'){
            def scannerHome = tool 'sonar'
            WithSonarQubeEnv('sonar'){
                sh "$(scannerHome)/bin/sonar-scanner \
                -Dsonar.projectKey=sonar \
                -Dsonar.sources=. \
                -Dsonar.host.url=http://localhost:9000 \
                -Dsonar.login=5ec91965645172864ac86aafaf8ab8ac3a4cabc0"
            }
        }
    }
}
