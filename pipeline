pipeline {
    agent any
    parameters {
        choice(name: 'type', choices: ['app', 'infra'], description: 'Run on specific platform')
    }
    stages {
        stage('app') {
            when {
                expression { params.type == "app" }
            }
            steps {
                git(
                    url: "https://github.com/Souravjaish/pipelinesetup.git",
                    branch: "main"
            )
                sh '''
                echo "this is app"
                cd app
                cat *
                '''
            }
        }
        stage('infra') {
            when {
                expression { params.type == "infra" }
            }
            steps {
                git(
                    url: "https://github.com/Souravjaish/pipelinesetup.git",
                    branch: "main"
            )
                sh '''
                echo "this is infra"
                cd infra
                cat *
                '''
            }
        }
    }
}
