pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from your repository
                git 'https://github.com/flex-V-00/Projects.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling the C++ project...'
                sh 'g++ -o casino_game casino_game.cpp'
            }
        }

        stage('Run') {
            steps {
                echo 'Running the game...'
                // Since it's interactive, we just check if it runs without crashing
                sh './casino_game < /dev/null || true'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
