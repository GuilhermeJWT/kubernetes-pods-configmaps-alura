# Primeiros Passos e Comandos:
kubectl get node = ver informações sobre o Cluster

# Pods
Pods são um conjunto de um ou mais Containers dentro, exemplo vamos pensar numa caixinha, e la dentro temos vários Containers
Sempre que criamos um Pod ele cria autmaticamente um endereço IP que não é mais do Container, mais sim do Pod
Não podemos ter 2 Containers na mesma porta em um mesmo Pod
Caso o Pod morre, o Kubernetes tem a capacidade de criar um outro Pod
Todo IP pertence ao Pod e NÃO aos Containers

Exemplo: Caso tem 2 Containers dentro de um Pod, se 1 Container der pau, o Pod continua normal, mais se caso os 2 der Pau, ai sim o Pod vai criar outro do Zero, não é renascer é criar outro do Zero, NÃO necessariamente com o mesmo Endereço IP 

Qual a grande vantagem de eles compartilhar o mesmo IP?
Reposta: Eles podem fazer a comunicação entre eles no mesmo LocalHost

