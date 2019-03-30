# Rapid scrum composer




### Para iniciar o projeto (Banco, API, APP) execute

```
docker-compose up
```

Na primeira vez o composer vai criar as imagens e containers e na proxima vez 
ele vai utilizar as imagens e containers gerados.


### Diversos

- Executar o sistema desacoplado do console
```
docker-compose up -d
```


- Executar o sistema forçando o build
```
docker-compose up --build -d
```