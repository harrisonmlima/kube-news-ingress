# Projeto kube-news

### Sobre o projeto
O projeto kube-news é um projeto desenvolvido em Python. O projeto tem como objetivo ser um exemplo para a criação de ambiente com containers usando Python.

### Observações do projeto
A aplicação é exposta usando a porta 80 e 8080

### Observação do build
Ir para a pasta src, e então executar o docker build para geração da imagem, e então alterar na pasta k8s/api/deployment.yaml

### Observação do inicio do cluster
Executar kubectl apply -f k8s/db -f k8s/api -f k8s/adb
watch 'kubectl get pods', quando os pods estiverem no status Running, executar kubectl apply -f k8s/ingress

### Acesso dos 2 programas
Na hora de criar o cluster k3d, você tem q dar port binding, como mostrado abaixo:
k3d cluster create meucluster -p "80:30000"
Onde o localhost acessa kube-news e o mongo-express acessa pelo localhost/mongo

# Project kube-news

### About the project
The project kube-news is a project developed in Python. The project goal is to be a example to environment creation with containers using Python.

### Project observation
The application runs using PORT 80 and 8080

### Build Observation
Go to src folder, then execute docker build to generate the image, then changes the image name in the file deployment-web.yaml in k8s folder

### Cluster initialize Observation
Execute kubectl apply -f k8s/db -f k8s/api -f k8s/adb
watch 'kubectl get pods', after every pod goes to status Running, execute kubectl apply -f k8s/ingress

### Access both programs
Before create the cluster k3d, You have to port binding both of them, as shown next:
k3d cluster create meucluster -p "8080:30000"
localhost access kube-news and localhost/pgadmin access mongo-express 