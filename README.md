# DevSecOps Challenge (Cost-Optimized Version)

Este proyecto implementa una aplicación serverless con un pipeline de CI/CD que incluye prácticas DevSecOps, priorizando la reducción de costos.

## Arquitectura

1. AWS Lambda: corre el código Python sin servidores permanentes.
2. API Gateway: expone un endpoint HTTP para la función Lambda.
3. (Opcional) DynamoDB: base de datos NoSQL con modelo de pago por uso.
4. AWS Security Hub: centraliza hallazgos de seguridad.

## Pasos para Deploy

1. Clonar el repositorio
2. Instalar dependencias `pip install -r requirements.txt`
3. Instalar Serverless Framework `npm install -g serverless`
4. `serverless deploy` (asegurarte de tener credenciales de AWS configuradas)

## CI/CD Pipeline

- **SAST** con Bandit
- **SCA** con OWASP Dependency-Check
- **Despliegue** a AWS Lambda vía Serverless
- (Opcional) **Envío de findings** a AWS Security Hub

## Estrategia de Prioridad de Vulnerabilidades

1. CVSS Score
2. Exposición del componente
3. Criticidad de los datos afectados

## Costo

- **Lambda** y **API Gateway** poseen capas gratuitas.
- **DynamoDB** ofrece un nivel gratuito.
- **AWS Security Hub** tiene 30 días de prueba gratis y luego cobra por hallazgo.
- Sin servidores “always on”, se pagan solo los recursos consumidos.