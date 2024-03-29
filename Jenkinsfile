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
        gitbisect(goodStartCommit: '98ac319c0cff47b4d39a1a7b61b4e195cfa231e5', badEndCommit: '198644632661c67b6c32f59e9047c11a70685e15', jobToRun: 'mvn clean test', searchIdentifier: '1', revisionParameterName: '1', retryCount: 1, minSuccessfulIterations: 1, continuesBuild: true, overrideGitCommand: true, gitCommand: 'none')
      }
    }

  }
}