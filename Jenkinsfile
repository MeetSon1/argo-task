node {

    // this stage is for cloning scripts and credentials in jenkins server  
    stage('clone repository'){
    sh 'echo "Cloning the repository"'
    checkout scm
    }

    stage("SSH Into argocd Server") {

        sh 'echo "connecting via ssh to master node"'
        def remote = [:]
        remote.name = 'meetvm2'
        remote.host = '4.240.61.198'
        remote.user = 'meet'
        remote.password = 'meet'
        remote.allowAnyHosts = true

        sh 'echo "completed ssh"' 

        // stage('Put deployment.yaml into k8smaster') {
        //     sshPut remote: remote, from: 'main.sh', into: '.'
        // } 

        // stage('Put deployment.yaml into k8smaster') {
        //     sshPut remote: remote, from: 'variables.sh', into: '.'
        // } 

        stage('Testing command works or not') {
            // sh 'echo "Testing pwd command"' 
            sshCommand remote: remote, command: "pwd"
            // sh 'echo "testing mkdir command"' 
            sshCommand remote: remote, command: "mkdir ./meet"
            sshCommand remote: remote, command: "ls"
        }
    } 
}
