#!groovy

@Library('jenkinslib') _     

def tools = new org.devops.tools()

pipeline{
    //指定运行此流水线的节点
    agent { node { label "build"}}

    //流水线的阶段
    stages{
        //阶段1 获取代码
        stage("CheckOut"){
            steps{
                script{
                    println("获取代码")
                    tools.PrintMes("获取代码",'green')
                    input id: 'Test', message: '是否继续', ok: '是', parameters: [choice(choices: ['是', '否'], name: '是否继续')], submitter: 'admin'
                }
            }
         }

        stage("Build"){
            steps{
                script{
                     println("运行构建")
                     tools.PrintMes("运行构建",'green')
                        
                }
            }    
        }
    }
    post {
        always{
            script{
                println("流水线结束后，经常做的事情")
            }
        }
        
        success{
            script{
                println("流水线成功后，要做的事情")
            }
        
        }
        failure{
            script{
                println("流水线失败后，要做的事情")
            }
        }
        
        aborted{
            script{
                println("流水线取消后，要做的事情")
            }
        }
    }
}
