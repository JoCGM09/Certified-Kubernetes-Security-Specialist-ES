## Capitulo 1: Setup de pods
En este capítulo se despliega un ambiente de 3 pods en el namespace "g04".

### Análisis del archivo setup.yaml:

- Crea un namespace llamado g04.
- Crea un pod llamado backend en el namespace g04. 
- Crea un pod llamado frontend en el namespace g04. 
- Crea un pod llamado others en el namespace default.

Paso 1: En el cluster de Kubernetes, crear el archivo setup.yaml y copiar el contenido del archivo.

Paso 2: En la terminal, ejecutar el comando: 

```
kubectl apply -f setup.yaml
```

Salida:

```
root@controlplane:~$ kubectl apply -f setup.yaml
namespace/g04 created
pod/backend created
pod/frontend created
pod/other created
```

Paso 3: Verificar que los pods se ejecuten correctamente en el namespace, ejecutar el comando para verificar las IPs virtuales creadas para los pods de frontend y backend.

```
kubectl get pods -n g04 -o wide
```

Salida:

```
root@controlplane:~$ kubectl get pods -n g04 -o wide
NAME       READY   STATUS    RESTARTS   AGE     IP           NODE     NOMINATED NODE   READINESS GATES
backend    1/1     Running   0          3m31s   10.244.1.6   node01   <none>           <none>
frontend   1/1     Running   0          3m31s   10.244.1.7   node01   <none>           <none>
```

Paso 4: Verificar que el pod others se ejecute correctamente en el namespace default, ejecutar el comando: 

```
kubectl get pods -n default
```

```
root@controlplane:~$ kubectl get pods -n default
NAME    READY   STATUS    RESTARTS   AGE
other   1/1     Running   0          26m
```