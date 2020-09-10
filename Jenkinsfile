node {
    checkout scm
    docker.image('agung3wi/alpine-rsync:1.1').inside('-u root') {
        sshagent (credentials: ['ssh-access-pttas']) {
            sh 'mkdir -p ~/.ssh'
            sh 'ssh-keyscan -H "192.168.88.40" > ~/.ssh/known_hosts'
            sh "rsync -rav --delete . pttas@192.168.88.40:/home/pttas/sites/laravelci-staging.pttas.xyz/public --exclude=.git"
        }
    }
}
