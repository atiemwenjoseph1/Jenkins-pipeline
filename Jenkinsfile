pipeline {
  agent any
  stages {
    stage("build") {
      steps {
        sh """
          docker build -t atiemwenjoseph/pipeline .
        """
      }
    }
    stage("Login") {
      steps {
        // This step should not normally be used in your script. Consult the inline help for details.
withDockerRegistry(credentialsId: 'Demo-creds-DockerHub', url: 'https://registry.hub.docker.com') {
    // some block
  sh 'docker push atiemwenjoseph/pipeline:latest'
}
      }
    }
  }
}
