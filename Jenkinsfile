pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/KanavJETHI/simple_project.git'
            }
        }

        stage('Show HTML') {
            steps {
                echo "Project updated. Launching HTML..."
                // Optional: You can run a local server to serve the HTML
                sh '''
                    mkdir -p serve_dir
                    cp index.html serve_dir/
                    cd serve_dir
                    python3 -m http.server 8080 &
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment complete.'
        }
        failure {
            echo 'Something went wrong.'
        }
    }
}