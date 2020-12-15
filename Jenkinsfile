pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/greggrimes52/devops-webapp'
      }
    }

    stage('Build') {
      steps {
        tool(name: 'gradle-4.10.2', type: 'hudsen.plugins.gradle.GradleInstallation')
        sh 'sh "${GRADLE_HOME}/bin/gradle tasks"'
        sh 'sh "${GRADLE_HOME}/bin/gradle build"'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts 'build/lib/*.war'
      }
    }

  }
}