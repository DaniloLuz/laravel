node('php'){
    stage('Clean'){
        deleteDir()
        sh 'ls -la'
    }

    stage('Fetch') {
        checkout scm
    }

    stage('Docker Build') {
        sh 'docker build -t danluz/laravel:$BUILD_NUMBER .'
    }

    stage('Docker Ship') {
        sh 'docker push danluz/laravel:$BUILD_NUMBER'
    }
    
    stage('Docker Clean') {
        sh 'docker rmi -f danluz/laravel:$BUILD_NUMBER'
    }
}
