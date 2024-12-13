pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/damvantu2004/BaiTapLonWeb1.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
               bat 'mkdir build' // Tạo thư mục build
               bat 'xcopy /e . build' // Sao chép tất cả file vào thư mục build
            }
        }
       stage('Katalon Test') {
            steps {
                 katalonExecute(
                     katalonProjectPath: 'C:/Users/damva/Katalon Studio/web', // Đường dẫn đến project Katalon của bạn
                     testSuitePath: 'Test Suites/ts1',
                     browserType: "Chrome",
                     apiKey: "fd673576-cda8-4b57-a1e3-4f3655550b60"  // Nếu bạn cần dùng API key
                 )
            }
       }
    }
}
