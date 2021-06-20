# Primeiros Passos e Comandos:
kubectl get node = ver informações sobre o Cluster
kubectl run nginx-pod --image=nginx:latest = ele cria um Pod
kubectl get pods = vai mostrar o status de criação como se fosse um tipo de (Docker PS)
kubectl get pods --watch = ele vai começar a acompanhar em tempo real, vizualização parecida com (Docker PS)
kubectl describe pod nginx-pod =  ele vai exibir diversas informações como: Container ID, Conditions, Events e muitos outros
kubectl edit pod nginx-pod = ele vai abrir o Bloco de Notas com as informaçoes pra você editar alguma coisa se caso precisar
kubectl apply -f .\primeiro-pod.yaml = vai applycar as configurações que estão no arquivo Yaml
kubectl delete pod nginx-pod = remove o pod
kubectl delete -f .\primeiro-pod.yaml =  ele vai la no arquivo e remove o POD
kubectl exec -it portal-noticias -- bash = agente entra dentro do container para digitar comandos, como se fosse (Docker Exec .. nome do container)
kubectl get pods -o wide = vai exibir os arquivos. IP e docker-desktop
kubectl get svc = vai listar todas as serviços, e vai mostrar coisas como IP's que foram criado para eles naquele momento e Porta tipo 80/TPC
kubectl exec -it pod-1 --bash e dar um curl no ip como 10.106.130.115:80 = ele vai exibir o código fonte da pagina HTML que no caso deu certo

# Pods
Pods são um conjunto de um ou mais Containers dentro, exemplo vamos pensar numa caixinha, e la dentro temos vários Containers
Sempre que criamos um Pod ele cria autmaticamente um endereço IP que não é mais do Container, mais sim do Pod
Não podemos ter 2 Containers na mesma porta em um mesmo Pod
Caso o Pod morre, o Kubernetes tem a capacidade de criar um outro Pod
Todo IP pertence ao Pod e NÃO aos Containers

Exemplo: Caso tem 2 Containers dentro de um Pod, se 1 Container der pau, o Pod continua normal, mais se caso os 2 der Pau, ai sim o Pod vai criar outro do Zero, não é renascer é criar outro do Zero, NÃO necessariamente com o mesmo Endereço IP 

Qual a grande vantagem de eles compartilhar o mesmo IP?
Reposta: Eles podem fazer a comunicação entre eles no mesmo LocalHost

# Svc = Service
Eles são capases de de conectar aos pods, Exemplo: temos 5 pods, se 1 deles morrer, o novo vai ser reconhecido pelos outros 4
Preveem IP's fixos para a comunicação
Fazem Balanceamento de Cargo

# Cm = ConfigMap
Responsavel por definir configuração que vão ser precisas dentro do Pod, exemplo setar váriaveis de configurações de acesso ao Banco de Dados, os ConfigMap é voltado para esse tipo de responsabilidade. 

# Criando um arquivo yaml 
Criamos um arquivo chamado primeiro-pod.yaml e nele colocamos configurações como:
apiVersion: v1
kind: Pod
metadata:
  name: primeiro-pod-declarativo
spec:
  containers:
    - name: nginx-container
      image: nginx:1.0

E ao entrarmos na pasta do arquivo, damos os comandos:
kubectl apply -f .\primeiro-pod.yaml = para aplicar o arquivo e
kibectl get pods --watch  = acompanhamos o andamento
      

