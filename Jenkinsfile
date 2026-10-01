pipeline {
    agent any

    stages {

        stage('Check HTML File') {
            steps {
                sh 'test -f index.html'
            }
        }

        stage('Test Required Elements') {
            steps {
                sh '''
                    grep -q '<form' index.html
                    grep -q 'name="name"' index.html
                    grep -q 'name="email"' index.html
                    grep -q 'name="phone"' index.html
                    grep -q 'name="dob"' index.html
                    grep -q 'name="gender"' index.html
                    grep -q 'name="course"' index.html
                    grep -q 'name="address"' index.html
                    grep -q 'type="submit"' index.html
                '''
            }
        }

        stage('Build Test Result') {
            steps {
                echo 'Student registration form passed all Jenkins tests.'
            }
        }
    }
}
