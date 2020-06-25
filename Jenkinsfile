pipeline {
  agent any
stages {
  stage('Git_checkout') {
    steps {
       echo "This is my first step Git_checkout"
       git credentialsId: '2e056a28-f3ea-4f64-b920-f14da3ae288d', url: 'https://github.com/aman5050/repos0.git'
    }
  }
  stage('Build') {
    steps {
       echo "This is my build step"
       powershell label: '', script: 'javac Hello.java'
    }
  }
  stage('Test') {
    steps {
       echo "This is my Test step"
    }
  }
  stage('Deploy') {
    steps {
       echo "This is my Deploy step"
    }
  }
}
  post {
    always {
      echo 'always runs regardless of the completion status of the Pipeline run'
    }
    success {
      echo 'step will run only if the build is successful'
    }
    failure { 
echo 'only when the Pipeline is currently in a "failed" state run, usually expressed in the Web UI with the red indicator.'
    }
    unstable {
      echo 'current Pipeline has "unstable" state, usually by a failed test, code violations and other causes, in order to run. Usually represented in a web UI with a yellow indication.'
    }
    changed {
      echo 'can only be run if the current Pipeline is running at a different state than the previously completed Pipeline'
    }
  }
}
