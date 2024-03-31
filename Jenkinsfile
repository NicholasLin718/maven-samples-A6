pipeline {
  agent any
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/NicholasLin718/maven-samples-A6', branch: 'master')
      }
    }

    stage('run') {
      steps {
        sh 'mvn test'
      }
    }

    stage('run2') {
      steps {
        sh 'mvn verify'
      }
    }

    stage('run3') {
      steps {
        sh 'mvn clean'
      }
    }

    stage('find_bug') {
      steps {
        sh 'git bisect start 198644632661c67b6c32f59e9047c11a70685e15  98ac319c0cff47b4d39a1a7b61b4e195cfa231e5'
        sh 'git bisect run mvn clean test'
      }
    }

  }
  tools {
    maven 'MVN'
    jdk 'JDK'
  }
}