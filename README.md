# hybrid-bigdata-serverless-engine
Requisitos Previos:

Scala 2.13 y sbt instalados.

Apache Spark 3.x configurado en el entorno.

NVIDIA CUDA Toolkit (para compilar la parte C++).

Cuenta de AWS/Azure para despliegue Serverless.

Pasos de Ejecución:

Compilar el binario GPU:
Navega a /src/gpu y ejecuta nvcc normalize.cu -o normalize -Xcompiler -fopenmp.

Desplegar Función Serverless:
Sube el binario compilado como capa (Layer) en tu AWS Lambda e interactúa vía API Gateway.

Ejecutar el Sistema Akka:
En la raíz del proyecto, ejecuta sbt run. El sistema iniciará el servidor HTTP en el puerto 8080 y quedará a la espera de peticiones POST en /api/v1/process.
