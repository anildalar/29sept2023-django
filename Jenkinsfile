
pipeline {
    agent any
    tools {
        nodejs 'nodejs'
    }
    parameters {
        choice(name:'VERSION', choices:['1.0', '1.1', '1.2'], description:'Choose the version of the project')

        booleanParam(name :'executeTests', description:'Execute the tests', defaultValue:false)
    }

    stages {
        stage('Build And Deploy') {
            steps {
                sh 'python3 -m venv .venv'
                sh 'source .venv/bin/activate'
                sh 'python3 -m pip install -r requirements.txt'
                sh 'python3 manage.py runserver 0.0.0.0:1010'
                // sh 'npm run build'
            }
        }
    }
}