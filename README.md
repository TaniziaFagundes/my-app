# Tutorial Kubernetes

## Implantando um Minikube

O Minikube é útil para desenvolvedores e engenheiros que desejam experimentar o Kubernetes ou desenvolver aplicativos que serão implantados em clusters Kubernetes. 
Ele permite que você crie um cluster Kubernetes em sua máquina local, permitindo que você teste e depure seus aplicativos antes de implantá-los em um ambiente de produção.


### Iniciando o Minikube



O seguinte comando é usado para iniciar um cluster Kubernetes local com o Minikube usando o Docker como driver de máquina virtual. Isso significa que o Minikube usará o Docker para criar contêineres que funcionarão como os nós do cluster Kubernetes em sua máquina local.

***```minikube start --driver docker```*** 

Comando principal para iniciar um cluster Kubernetes local com o Minikube.

***```minikube status```***


Depois de executar esse comando com sucesso, o Minikube configurará e inicializará o cluster Kubernetes local usando o Docker como a tecnologia subjacente. Você poderá usar esse cluster local para desenvolver, testar e depurar aplicativos que serão implantados em clusters Kubernetes de produção. Certifique-se de que o Docker esteja instalado e em execução em sua máquina antes de usar o driver Docker com o Minikube.

### Configurando a senha e usuário do banco de dados mongoDB

Nos dois comandos a seguir adicione os codigos base64 gerados no arquivo de configuração mongo-secret em mongo-user e mongo-password
```
echo -n mongouser | base64
echo -n mongopassword | base 64
```

### Aplicando as configurações dos arquivos criados 

Nos comando a seguir certifique-se de que os arquivos YAML contenham as definições corretas para seus recursos e que os nomes dos arquivos e caminhos estejam corretos. 
Certifique-se também de que o ***kubectl*** esteja configurado corretamente para se conectar ao cluster Kubernetes onde deseja implantar esses recursos. 
```
kubectl apply -f mongo-config.yaml
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongo.yaml
kubectl apply -f webapp.yaml
```


### listando os pods, services e deployments 

Comando para visualizar a implementação 

```kubectl get all``` 



### Acessando a aplicação

```minikube service webapp-service``` 


