
# Docker 


Comando para visualizar containers em execução:

```
docker ps
```

Comando para visualizar containers existentes:
```
docker ps -a
```

Comando para executar uma imagem no docker:

```
docker run hello-world 
```

Comando para executar uma imagem do ubunto e mante um processo em execução:

```
docker run -it ubuntu bash
```
Comando para interagir com um container já criado:

```
docker exec -iti (id-conatiner) (comand)
```
exemplo:

```
docker exec -iti aff79ade9f02 bash
```

Mapeamento de porta do container: Mapeamento alaetorio ou padrão

```
docker run -P (imagem) 
```

Mapeamento de porta do container: Porta especifica

```
docker run -p porta-desejada: porta-do0-container (imagem) 
```