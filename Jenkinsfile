node {
    def commit_id
    stage('Prep') {
        checkout scm
        sh 'git rev-parse --short HEAD > .git/commit-id'
        commit_id = readFile('.git/commit-id').trim()
    }
    stage('test'){
        nodejs(nodeJSInstallationName: 'nodejs') {
            sh 'npm install'
            sh 'npm test'
        }
    }
}