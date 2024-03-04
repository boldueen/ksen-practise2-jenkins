pipeline {
    agent {
        docker { image 'rust:latest' }
    }

    stages {
        stage("test"){
            steps {
                echo 'building an app'
            }
        }
        stage("deploy"){
            steps {
                echo 'Publishing...'
                sh """
                ls -la

                echo 'building an app'
                cat ./src/main.rs
                rustc ./src/main.rs

                ./main
                """

            }
        }


    }   
    post {

        success {
            echo 'YEAH IM COOL'
            archiveArtifacts artifacts: 'main', fingerprint: true
        }
    }
}
