pipeline {
    agent any

    stages {
        stage("test"){
            steps {
                echo 'building an app'
            }
        }
        stage("deploy"){
            steps {
                echo 'building an app'
                sh 'rustc src/main.rs'
                sh './main'
            }
        }


    }   
    post {

        success {
            echo 'YEAH IM COOL'
        }
    }
}

