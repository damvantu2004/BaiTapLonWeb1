pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: '<URL-repository-GitHub>', branch: 'main'
            }
        }
        stage('Build') {
            steps {
               sh 'mkdir -p build' // Tạo thư mục build
               sh 'cp -r * build/' // Copy các file HTML/CSS
           }
        }
        stage('Katalon Test') {
            steps {
                 katalonExecute(
                     katalonProjectPath: 'C:\Users\damva\Katalon Studio\web',
                     testSuitePath: 'katalonc -noSplash -runMode=console -projectPath="C:\Users\damva\Katalon Studio\web\web.prj" -retry=0 -testSuitePath="Test Suites/ts1" -browserType="Chrome" -executionProfile="default" -apiKey="fd673576-cda8-4b57-a1e3-4f3655550b60" --config -proxy.auth.option=NO_PROXY -proxy.system.option=NO_PROXY -proxy.system.applyToDesiredCapabilities=true -webui.autoUpdateDrivers=true',
                     browserType: "Chrome",
              
                 )
            }
       }
   }
}
