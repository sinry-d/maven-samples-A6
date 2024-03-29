pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/sinry-d/maven-samples-A6.git', branch: 'master')
      }
    }

    stage('bisect') {
      steps {
        sh 'git bisect start'
        sh 'git bisect bad 198644632661c67b6c32f59e9047c11a70685e15'
        sh 'git bisect good 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5'
        sh 'git bisect run mvn clean test'
        sh 'mvn verify'
        sh 'mvn test'
        sh 'mvn clean'
        sh 'git bisect reset HEAD'
      }
    }

  }
  tools {
    maven 'Maven 3.9.6'
    jdk 'JDK-1.8'
  }
}