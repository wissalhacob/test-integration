pipeline {
    agent any
    environment {
        JAVA_HOME = tool 'jdk-11' // Spécifiez ici la version de Java que vous utilisez pour votre application
    }
	 stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/wissalhacob/test-integration.git'
            }
        }
    stages {
        stage('---clean---') {
            steps {
                bat "ant clean" // Pour nettoyer votre projet Java Swing
            }
        }
        stage('--compile--') {
            steps {
                bat "ant compile" // Pour compiler votre projet Java Swing
            }
        }
		stage('Test') {
    steps {
      bat 'ant test'
    }
  }
  stage('Package') {
    steps {
      bat 'ant package'
    }
  }
	    stage('Build') {
   steps {
      bat 'ant build' // ou 'ant jar'
   }
}
   stage('Run') {
            steps {
                bat 'ant run'
            }
        }



    }
}
