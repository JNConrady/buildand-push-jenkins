node {

   def registryProjet='forma-jnc/'
   def IMAGE="${registryProjet}app:2.4"

    stage('Clone') {
          checkout scm
    }

    def img = stage('Build') {
          docker.build("$IMAGE",  '.')
          }

    stage('Run') {
          img.withRun("--name run-$BUILD_ID") { c ->
       
          }
    }

    stage('Push') {
       docker.withRegistry('https://registry.ludovic.io/' , 'harbor_id_jnc2') {
              img.push 'latest'
              img.push()
          }
    }

}

