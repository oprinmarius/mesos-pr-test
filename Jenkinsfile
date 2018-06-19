pipeline {
    agent { label 'dummy-slave' }
    stages {
        stage('init') {
            steps {
	    	sh 'git log'
                echo "Init result: ${currentBuild.result}"
                echo "Init currentResult: ${currentBuild.currentResult}"
            }
        }
        stage('generate windows blob') {
            steps {
                echo "During Build result: ${currentBuild.result}"
                echo "During Build currentResult: ${currentBuild.currentResult}"
            }
            post {
                always {
                    echo "Post-Build result: ${currentBuild.result}"
                    echo "Post-Build currentResult: ${currentBuild.currentResult}"
                }
            }
        }
        stage('dcos testing') {
            steps {
                sh 'git log'
                sh 'echo Test'
            }
        }
        stage('post result') {
            steps {
                sh 'echo Deploy'
                echo "post result: ${currentBuild.result}"
                echo "post currentResult: ${currentBuild.currentResult}"
            }
        }
    }
}

