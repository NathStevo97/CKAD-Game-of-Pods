# GOP Fileserver Deployment - Pento
In this challenge you will work with the following:

- Troubleshooting a Kubernetes API Server - https://kodekloud.com/courses/539883/lectures/9808356
- Troubleshooting KubeConfig files - https://kodekloud.com/courses/539883/lectures/9808356
- Drain/Cordon/UnCordon worker nodes - https://kodekloud.com/courses/539883/lectures/9808231
- Create Persistent Volumes and Persistent Volume Claims - https://kodekloud.com/courses/539883/lectures/9808276
- Deploy a simple file server application - https://kodekloud.com/courses/539883/lectures/9808165

---

## Tasks

### Master-Node
- Master node: coredns deployment has image: 'k8s.gcr.io/coredns:1.6.7'
- Fix kube-apiserver. Make sure its running and healthy.
- kubeconfig = /root/.kube/config, User = 'kubernetes-admin' Cluster: Server Port = '6443'

### Node01
- node01 is ready and can schedule pods?

### /web
- node01 has hostPath created = '/web'

### data-pv
- Create new PersistentVolume = 'data-pv'
- PersistentVolume = data-pv, accessModes = 'ReadWriteMany'
- PersistentVolume = data-pv, hostPath = '/web'
- PersistentVolume = data-pv, storage = '1Gi'

### data-pvc
- Create new PersistentVolumeClaim = 'data-pvc'
- PersistentVolume = 'data-pvc', accessModes = 'ReadWriteMany'
- PersistentVolume = 'data-pvc', storage request = '1Gi'
- PersistentVolume = 'data-pvc', volumeName = 'data-pv'

### gop-file-server
- Create a pod for fileserver, name: 'gop-fileserver'
- pod: gop-fileserver image: 'kodekloud/fileserver'
- pod: gop-fileserver mountPath: '/web'
- pod: gop-fileserver volumeMount name: 'data-store'
- pod: gop-fileserver persistent volume name: data-store
- pod: gop-fileserver persistent volume claim used: 'data-pvc'

### gop-fs-service
- New Service, name: 'gop-fs-service'
- Service name: gop-fs-service, port: '8080'
- Service name: gop-fs-service, targetPort: '8080'