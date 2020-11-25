# POSTGRESQL con Docker API FLASK 
## Levantar el servicio 

```sh
docker-compose build 
docker-compose up -d 
```

### Comando inicial de la base de datos

1.- Obtener el id de la imagen de rds-aws_api-flask 
```sh
docker-compose exec  api-flask bash 
```

2.- Crear la base de datos y crear los datos iniciales
```sh
flask db_create && flask db_seed 
```
### Revisar en postgres nuestros datos 

```sql
SELECT * FROM public.quotes
ORDER BY id ASC;
```

### Revisar el API

- Ver health
```sh
curl localhost:5000/
```
- GET all quotes
```sh
curl --location --request GET 'http://0.0.0.0:5000/quotes' --data-raw ''
```
- POST a quote

```sh
curl --location --request POST 'http://0.0.0.0:5000/add_quote' \
--form 'quote_desc=D'\''oh!' \
--form 'quote_type=Motivation' \
--form 'author=Homero Simpson'
```
- PUT a quote

```sh
curl --location --request PUT 'http://0.0.0.0:5000/update_quote/6' \
--form 'quote_desc=D'\''oh!' \
--form 'quote_type=Motivation' \
--form 'author=Homero Jay  Simpson'
```
- POST a quote

```sh
curl --location --request POST 'http://0.0.0.0:5000/add_quote' \
--form 'quote_desc=Tienes el micronfono apagado' \
--form 'quote_type=Motivation' \
--form 'author=Benjamin'
```
- DELETE a quote

```sh
curl --location --request DELETE 'http://0.0.0.0:5000/remove_quote/7'
```