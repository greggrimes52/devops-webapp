pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/greggrimes52/devops-webapp.git'
      }
    }

    stage('Build') {
      steps {
        def GRADLE_HOME = tool(name: 'gradle-4.10.2', type: 'hudson.plugins.gradle.GradleInstallation')
        sh '${GRADLE_HOME}/bin/gradle tasks'
        sh '${GRADLE_HOME}/bin/gradle build'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts 'build/lib/*.war'
      }
    }

  }
}
