## Capitulo 1: Setup de pods
En este capítulo se despliega un ambiente de 3 pods en el namespace "g04".

### Análisis del archivo setup.yaml:

- Crea un namespace llamado g04.
- Crea un pod llamado backend en el namespace g04. 
- Crea un pod llamado frontend en el namespace g04. 
- Crea un pod llamado others en el namespace g04.

Paso 1: En el cluster de Kubernetes, crear el archivo setup.yaml y copiar el contenido del archivo.

Paso 2: En la terminal, ejecutar ´kubectl apply -f setup.yaml´.