## Fundamentos do Kubernetes

- **Control Plane:** Onde é gerenciado o controle dos processo do Nodes.
- **Nodes:** Máquinas que são gerenciados pelo Control Plane.
- **Deployment:** A execução de uma imagem/projeto em um pod.
- **Pod:** um ou mais containers que estão em um Node.
- **Services:** Serviços que expõe os Pods ao mundo externos
- **Kubectl** Clientes de linha de comando para ## Fundamentos do Kubernetes

## Deployment

- Parte fundamental do Kubernetes
- Com ele criamos os serviços que irão rodar no Pods
- Definimos uma imagem e um nome, para posteriormente ser replicado entre servidores
- A partir da criação do deployment teremos containers rodando
- Vamos precisar de uma imagem no hub do Docker para gerar um Deployment

## Services

- As aplicações do Kubernetes não tem conexão com o mundo externo
- Por isso precisamos criar um `Service`, que possibilita expor os pods.
- Isso acontece pois os pods são criados para serem destruídos e perderem tudo, ou seja, os dados gerados deles serão apagados.
- Entre o Service é uma entidade separada dos Pods, que expõe eles a uma rede

## Ver as Configurações do Kubernetes

```bash
kubectl config view
```

## Criar um Service

- **NOME**: Nome do Deployment
- **TIPO**: Há vários, mas usa `LoadBalancer`
- **PORTA**: Porta em que o serviço é consumido

```bash
kubectl expose deployment <NOME> --type=<TIPO> --port<PORT>
```

## Gerar um IP para o Service

```bash
minikube service <NOME>
```

## Verificar um Service

```bash
kubectl get services
```

## Verificar Detalhes de um Service

```bash
kubectl describe services/<NOME>
```

## Criar um Deployment

```bash
kubectl create deployment <NOME> --image<IMAGE>
```

## Verificar um Deployment

```bash
kubectl get deployments
```

## Ver Detalhes um Deployment

```bash
kubectl describe deployments
```

## Verificar um Pod

```bash
kubectl get pods
```

## Ver Detalhes um Pods

```bash
kubectl describe pods
```

## Replicando uma aplicação (Escalando)

```bash
kubectl scale deployment/<NOME> --replicas<NUMERO>
```

- Pode ver no Dashboard
- Pode ver no `kubectl get pods`

## Verificar o Número De Réplicas

```bash
kubectl get rs
```

## Diminuindo a escala de uma aplicação

```bash
kubectl scale deployment/<NOME> --replicas<NUMERO MENOR>
```

- Pode ver no Dashboard
- Pode ver no `kubectl get pods`

## Atualizar a Imagem

```bash
kubectl set image deployment/<NOME> <NOME_CONTAINER>=<NOVA_IMAGEM>
```

## Verificar uma Alteração

```bash
kubectl rollout status deployment/<NOME>
```

## Voltar/Desfazer uma Alteração

```bash
kubectl rollout undo deployment/<NOME>
```

## Deletando um Service

```bash
kubectl delete service <NOME>
```

## Deletando um Deployment

```bash
kubectl delete deployment <NOME>
```
