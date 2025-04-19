## Chaves Mais Utilizadas

- **ApiVersion:** Versão Utilizada da Ferramenta
- **Kind:** Tipo de Arquivo (Deployment, Service, Pod, etc)
- **Metadata:** Descrever algum Objeto, inserindo chaves como name, namespace, labels, annotations, ownerReferences, creationTimestamp, etc.
- **Replicas:** Quantidade de réplicas do Pod que o Deployment deve manter em execução.
- **Containers:** Descrever o Container, inserindo chaves como name, image, ports, env, volumeMounts, resources, livenessProbe, readinessProbe, etc.

## Executar arquivo YAML (Deployment, Service, etc)

```bash
kubectl apply -f <ARQUIVO>.yaml
```

## Executar arquivo YAML (Deployment, Service, etc)

```bash
kubectl delete -f <ARQUIVO>.yaml
```

## Atualizar um Projeto
- Primeiro, crie uma nova versão da imagem
- Fazer o push para o Hub
- Alterar o arquivo YAML com a nova versão da imagem
- E reaplicar o comando `kubectl apply -f <ARQUIVO>.yaml`

## Unir Aquivos do Projeto
- Vamos precisar unir o Deployment e o Service em um único arquivo YAML
- A Separação de Objetos no arquivo YAML é feita através de três traços `---` (três hífens)
- Dessa forma, o Kubernetes vai entender que são dois objetos diferentes e vai aplicar os dois ao mesmo tempo
- Uma boa prática é colocar o `Service` antes do `Deployment` no arquivo YAML.