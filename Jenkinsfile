pipeline { 
    agent any 
    environment { 
        NODE_VERSION = '20' 
    } 
 
    stages { 
        stage('Checkout') { 
            steps { 
                echo "📥 Clonando el repositorio..." 
                checkout scm 
            } 
        } 
 
        stage('Build') { 
            steps { 
                script { 
                    try { 
                        echo "⚙️ Instalando dependencias..." 
                        bat 'npm install' 
                        bat 'npm run build' 
                    } catch (Exception e) { 
                        error("❌ Error en la etapa de Build") 
                    } 
                } 
            } 
        } 
 
        stage('Test') { 
            steps { 
                script { 
                    try { 
                        echo "🧪 Ejecutando pruebas..." 
                        bat 'npm run test' 
                    } catch (Exception e) { 
                        error("❌ Error en la etapa de Test") 
                    } 
                } 
            } 
        } 
 
        stage('Deploy') { 
            steps { 
                script { 
                    try { 
                        echo "🚀 Desplegando aplicación..." 
                        bat 'npm start &' 
                    } catch (Exception e) { 
                        error("❌ Error en la etapa de Deploy") 
                    } 
                } 
            } 
        } 
    } 
 
    post { 
        success { 
            echo "✅ Pipeline completado con éxito" 
        } 
        failure { 
            echo "❌ El pipeline ha fallado" 
        } 
    } 
}