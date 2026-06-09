pipeline {
    agent any

    stages {

        stage('Clonar Proyecto') {
            steps {
                echo 'Repositorio descargado correctamente'
            }
        }

        stage('Compilar') {
            steps {
                echo 'Compilando proyecto'
            }
        }

        stage('Pruebas') {
            steps {
                echo 'Ejecutando pruebas'
            }
        }

        stage('Generar Reporte') {
            steps {
                script {
                    writeFile file: 'reporte.html', text: '''
                    <html>
                        <body>
                            <h1>Reporte Jenkins</h1>
                            <p>Build ejecutado correctamente</p>
                        </body>
                    </html>
                    '''
                }
            }
        }
    }

    post {
        always {
            publishHTML([
                allowMissing: false,
                alwaysLinkToLastBuild: true,
                keepAll: true,
                reportDir: '.',
                reportFiles: 'reporte.html',
                reportName: 'Reporte de Build'
            ])
        }
    }
}