pipeline{
    agent{
        label "any"
    }
    stages{
        stage("Fetch code"){
            steps{
                echo "========Fetch code========"
                git branch: 'main', url: 'https://github.com/colossus06/20-realtime-devops-projects.git'
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========Fetch code executed successfully========"
                }
                failure{
                    echo "========Fetch code execution failed========"
                }
            }
        }
        stage("Build"){
            steps {
                sh 'mvn install'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}