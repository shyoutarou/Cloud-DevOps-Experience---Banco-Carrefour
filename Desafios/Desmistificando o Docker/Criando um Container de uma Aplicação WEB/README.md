## Desafio

Docker Compose para executar uma aplicação HTML em um Container Apache.

## Resposta

Crie um diretório website e um arquivo HTML com o seguinte conteúdo:

```bash
<html>

<h1>Meu Primeiro projeto Docker</h1>

</html>
```

<p align="center">
  <img src="../../../assets/Docker_Compose_01.png" alt="Image" width="100%" />
</p>

Execute o comando para instalar o Docker Compose:

```bash
apt install docker-compose
```
<p align="center">
  <img src="../../../assets/Docker_Compose_03.png" alt="Image" width="100%" />
</p>

Depois o seguinte o comando:
```bash
docker-compose up -d
```
<p align="center">
  <img src="../../../assets/Docker_Compose_04.png" alt="Image" width="100%" />
</p>


Voltando ao ambiente cloud, verifique se o tráfego HTTP esteja liberado:
<p align="center">
  <img src="../../../assets/Docker_Compose_05.png" alt="Image" width="100%" />
</p>

Copie o endereço IP público:
<p align="center">
  <img src="../../../assets/Docker_Compose_06.png" alt="Image" width="100%" />
</p>

<p align="center">
  <img src="../../../assets/Docker_Compose_07.png" alt="Image" width="100%" />
</p>

