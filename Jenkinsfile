properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/kedarkadam/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }

stage ("GetInstances") {

    sh "aws ec2 describe-instances --region us-east-1"
}
stage ("CreateInstance") {
    sh "
   aws ec2 run-instances --image-id ami-013be31976ca2c322 
    --count 1 --instance-type t2.micro 
    --key-name kedarkeypair --security-group-ids sg-6c5f6020 
    --subnet-id subnet-3d9acc77 --region us-east-1"

}
    
    
}
