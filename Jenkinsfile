pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This will checkout your code from the GitHub repository
                git 'https://github.com/rahulsingh178FHKiel/ASEProjectJenkins'
            }
        }

        stage('Sync to S3') {
            steps {
                // This will sync your file to the S3 bucket
                sh '''
                aws s3 cp index.html s3://ase-project-website/ --region ${{ secrets.AWS_REGION }}
                '''
            }
        }
    }
}
