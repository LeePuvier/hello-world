#!groovy
pipeline {
    //在任何可用的代理上执行Pipeline
    agent any
    //常量参数，初始确定后一般不需更改
    options {
        //保持构建的最大个数
        buildDiscarder(logRotator(numToKeepStr: '10')) 
    }
    //pipeline的各个阶段场景
    stages {
        stage('代码获取') {
            steps {
              echo "starting fetchCode ......"
            }
        }
        stage('单元测试') {
            steps {
              echo "starting unitTest......"
            }
        }
        stage('静态检查') {
            steps {
                echo "starting codeAnalyze with SonarQube......"
            }
        }

        stage('部署测试环境') { 
            steps {
                echo "starting deploy to ......"
            }
        }

      stage('接口自动化测试') {
            steps{
                echo "starting interfaceTest......"
            }
        }

        stage('UI自动化测试') { 
             steps{
             echo "starting UITest......"
             //这个项目不需要UI层测试，UI自动化与接口测试的pipeline脚本类似
             }
         }

        stage('性能自动化测试 ') { 
            steps{
                 echo "starting performanceTest......"
                //视项目需要增加性能的冒烟测试，具体实现后续专文阐述
                }
        }

        stage('通知人工验收'){
            steps{
                echo "不需要通知测试人员人工验收"
                }
        }

        stage('发布系统') { 
            steps{
                echo "starting deploy......"
            //    TODO发布环节后续专题阐述
            }
        }
    }
}
