# Primeiros Passos e Comandos:
kubectl get node = ver informações sobre o Cluster
kubectl run nginx-pod --image=nginx:latest = ele cria um Pod
kubectl get pods = vai mostrar o status de criação como se fosse um tipo de (Docker PS)
kubectl get pods --watch = ele vai começar a acompanhar em tempo real, vizualização parecida com (Docker PS)
kubectl describe pod nginx-pod =  ele vai exibir diversas informações como: Container ID, Conditions, Events e muitos outros
kubectl edit pod nginx-pod = ele vai abrir o Bloco de Notas com as informaçoes pra você editar alguma coisa se caso precisar

# Pods
Pods são um conjunto de um ou mais Containers dentro, exemplo vamos pensar numa caixinha, e la dentro temos vários Containers
Sempre que criamos um Pod ele cria autmaticamente um endereço IP que não é mais do Container, mais sim do Pod
Não podemos ter 2 Containers na mesma porta em um mesmo Pod
Caso o Pod morre, o Kubernetes tem a capacidade de criar um outro Pod
Todo IP pertence ao Pod e NÃO aos Containers

Exemplo: Caso tem 2 Containers dentro de um Pod, se 1 Container der pau, o Pod continua normal, mais se caso os 2 der Pau, ai sim o Pod vai criar outro do Zero, não é renascer é criar outro do Zero, NÃO necessariamente com o mesmo Endereço IP 

Qual a grande vantagem de eles compartilhar o mesmo IP?
Reposta: Eles podem fazer a comunicação entre eles no mesmo LocalHost

