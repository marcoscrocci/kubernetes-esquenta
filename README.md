# Informações

### 1) Instalar o Kind:
https://kind.sigs.k8s.io/docs/user/quick-start/#installation

### 2) Criar um cluster:
kind create cluster --name=esquenta-k8s

### 3) Ativar os comando no contexto do computador o acesso ao cluster:
kubectl cluster-info --context kind-esquenta-k8s

### 4) Executar os comandos no servidor:
kubectl

### 5) Verificar os nodes:
kubectl get nodes


### 6) Criar um projeto GoLang:
go mod init webserver

### 7) Criar o arquivo main.go:
Visualizar este arquivo nesta pasta.

### 8) Executar o arquivo main.go:
go run main.go

### 9) Construir o binário do arquivo main.go:
go build

### 10) Criar o arquivo Dockerfile:
Visualizar este arquivo nesta pasta.

### 11) Criar a imagem do arquivo Dockerfile:
docker build -t <seu-usuario-docker-hub>/esquentak8s .

### 12) Executar o container com base na imagem criada no passo anterior:
docker run --rm -p 4000:4000 marcoscrocci/esquentak8s

### 13) Publicar a imagem no Docker Hub:
docker login
docker push marcoscrocci/esquentak8s

### 14) Criar a pasta k8s
Utilizar o VS Code

### 15) Criar o arquivo pod.yaml
No VS Code com a extensão do Kubernetes instalada, digitar pod e alto completar. Arquivo pronto nessa pasta.

### 16) Executar o comando no terminal para criar o pod:
kubectl apply -f k8s/pod.yaml
pod/webserver created

### 17) Listar os pods criados:
kubectl get pods

### 18) Definir a porta do computador local para acessar a porta do container que está no Kubernetes
kubectl port-forward pod/webserver 4000:4000

### 19) Para excluir um pod:
kubectl delete pod webserver

### 20) Para garantir que os pods sempre estarão em execução, mesmo se até mesmo forem excluídos, criamos um arquivo replicaset.yaml:
Arquivo pronto nessa pasta

### 21) Executar o comando no terminal para criar os pods com base no arquivo replicaset:
kubectl apply -f k8s/replicaset.yaml

### 22) Listar os replicasets:
kubectl get replicaset

### 23) Excluir um replicaset:
kubectl delete replicaset webserver

### 24) Com o kind: ReplicaSet, ao excluir um pod, um outro é criado no lugar com a nova versão ficando os demais na versão antiga. Se o kind: Deployment, todos são atualizados. Mudar e repetir o comando:
kubectl apply -f k8s/replicaset.yaml

### 23) Criar o arquivo service.yaml para gerenciar os acessos por load balance:
Arquivo pronto nessa pasta

### 24) Executar o comando no terminal para criar o service:
kubectl apply -f k8s/service.yaml

### 25) Listar o(s) service(s):
kubectl get svc

### 26) Definir o acesso ao service na porta especifica:
kubectl port-forward service/webserver 4000:80


Vídeo da live:
https://www.youtube.com/watch?v=54Cw3M4k19w&t=4161s
