pipeline {
    
    agent any

    options {
        timestamps ()
    }

    stages {

        stage('Checkout Stage') {
            steps {
                git branch: 'master',
                url: 'https://github.com/Ation/cicd-sessions-repo.git'
            }
        }

        stage('Parallel Execution') {
            parallel {
                stage('Docs Stage') {
                    steps {
                        echo "it is docs stage"
                        //sh "tox -e docs"
                    }
                }

                stage('Linters Stage') {
                    steps {
                        echo "it is linters stage"
                        //sh "tox -e linters"
                    }
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
