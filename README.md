# bdxio2016-timelion

Ce repository contient le docker-compose permettant de lancer kibana et elasticsearch contenant des données de démo.
Ce sont les mêmes données qui m'ont servies lors de la présentation au Bdx.io 2016.


Une fois dans le répertoire, lancer la commande :
```
docker-compose up
```

Bien entendu, vous devez avoir installé Docker-engine et une version récente de Docker-compose (>=1.8)

Kibana sera alors accéssible depuis l'url [http://localhost:5601](http://localhost:5601)


### Slides en version 16/9 ou 4/3

Dans le docker compose, il suffit de remplacer le tag docker de l'image jmonsinjon/bdxio-kibana par 4.3 ou 16.9

#### 16/9
```yml
kibana-16.9:
  image: jmonsinjon/bdxio-kibana:16.9
  links:
    - "elasticsearch:elasticsearch"
  ports:
    - "5601:5601"
  environment:
    ELASTICSEARCH_URL: http://elasticsearch:9200
```

#### 4/3
```yml
kibana-4.3:
  image: jmonsinjon/bdxio-kibana:4.3
  links:
    - "elasticsearch:elasticsearch"
  ports:
    - "5601:5601"
  environment:
    ELASTICSEARCH_URL: http://elasticsearch:9200
```
