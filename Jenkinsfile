node {
  stage("Clone the project") {
    git branch: 'main', url: 'https://github.com/nabilfeghali/jenkins-demo.git'
  }

  stage("Compilation") {
    bat "mvnw clean install -DskipTests"
  }

  stage("Tests and Deployment") {
      stage("Running unit tests") {
          bat "mvnw test -Punit"
      }
      stage("Deployment") {
          bat 'start /B mvnw spring-boot:run -Dserver.port=8001'
      }
  }
}
