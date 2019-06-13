pipeline {
    agent any

    stages {
        stage('Preparation') {
            steps {
                echo 'Preparation..'
            }
        }
        stage('Build') {
            steps {
		sh './gradlew clean build'
                echo 'Build..'
            }
        }
        stage('Results') {
            steps {
		junit '**/build/test-results/test/TEST-*.xml'
		archiveArtifacts 'build/libs/*'
                echo 'Results......'
            }
        }
    }
}
