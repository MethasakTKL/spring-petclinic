pipeline {
    agent none  // ไม่ใช้ agent โดยรวม แต่จะกำหนดในแต่ละ stage
    stages {
        stage('Maven Install') {
            agent {
                docker {   // ใช้ Docker agent ใน stage นี้
                    image 'maven:3.5.0'
                    args '-v /root/.m2:/root/.m2'  // กำหนด mount ถ้าต้องการให้ใช้ cache ของ Maven
                }
            }
            steps {
                sh 'mvn clean install'  // คำสั่ง Maven ที่จะรันภายใน Docker container
            }
        }
    }
}