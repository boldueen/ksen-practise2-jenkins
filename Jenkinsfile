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
                echo 'Publishing...'
                sh """
                ls -la
                curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
                . $HOME/.cargo/env
                export PATH=$HOME/.cargo/bin:$PATH
                rustc --version

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
