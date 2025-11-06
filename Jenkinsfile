pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the GitHub repository...'
                git 'https://github.com/yourusername/your-streamlit-repo.git'
            }
        }

        stage('Setup Python Environment') {
            steps {
                echo 'Setting up Python environment...'
                sh '''
                python3 -m venv venv
                source venv/bin/activate
                pip install --upgrade pip
                pip install streamlit
                '''
            }
        }

        stage('Run Streamlit App') {
            steps {
                echo 'Starting Streamlit app...'
                sh '''
                source venv/bin/activate
                nohup streamlit run app.py --server.port 8501 &
                '''
                echo 'App is running on http://localhost:8501'
            }
        }
    }

    post {
        success {
            echo '✅ Streamlit app deployed successfully using Jenkins!'
        }
        failure {
            echo '❌ Build failed. Please check logs.'
        }
    }
}

