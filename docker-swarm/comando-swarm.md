## Criar um Cluster de Nodes
```unix
docker swarm init --advertise-addr=<IP>
```

## Ver nós Nodes de um Swarm
```unix
docker node ls
```

## Criar um Serviço
```unix
docker service create --name <nome> <imagem>
```

## Ver os Serviços de um Swarm
```unix
docker service ls
```

## Remover os Serviços de um Swarm
```unix
docker service rm <nome> (OU) <HashID>
```

## Aumentar o Número de Replicas
```unix
docker service create --name <nome> --replicas <Número> <Imagem>
```

## Ver o Token de Conexão do Swarm
```unix
docker swarm join-token manager
```

## Remover o Swarm de Um Node
```unix
docker swarm leave
```

## Remover nós Nodes de um Swarm
```unix
docker node rm <ID>
```

## Inspecionar um Serviço no Swarm
```unix
docker service inspect <ID>
```

## Ver quais containers estão rodando em um serviço do Swarm
```unix
docker service ps <ID>
```

## Rodar Compose no Swarm
```unix
docker stack deploy -c <ARQUIVO.YAML> <NOME>
```

## Aumentar o número de Réplicas 
```unix
docker service scale <NOME>=<REPLICAS>
```

## Atualizar uma imagem de um Service
```unix
docker service update --image <IMAGEM> <SERVIÇO>
```