def git_url = 'https://github.com/newbielinux1/nginx-conf.git'
def git_branch = 'main'

pipeline
{
    agent {
        label 'awsserver'
    }
    stages
    {
        stage('Git-checkout')
        {
            steps
            {
                git credentialsId: 'github', url: git_url , branch: git_branch
            }
        }
        stage('nginx-config')
        {
            steps
            {
                sh '''
                sudo cp nginx.conf /etc/nginx/nginx.conf
                sudo systemctl restart nginx
                '''
            }
        }
}
