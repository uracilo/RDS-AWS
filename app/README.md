# RDS-AWS

flask db_create
flask db_seed 


export .env



SELECT * FROM posgres.quotes
ORDER BY id ASC 


pip3 install virtualenv
virtualenv p --python=python3  
source p/bin/activate

pip install -r requirements.txt

flask run





curl localhost:5000/

curl --location --request GET 'http://127.0.0.1:5000/quotes' \
--data-raw ''


curl --location --request POST 'http://127.0.0.1:5000/add_quote' \
--form 'quote_desc=D'\''oh!' \
--form 'quote_type=Motivation' \
--form 'author=Homero Simpson'

curl --location --request PUT 'http://127.0.0.1:5000/update_quote/6' \
--form 'quote_desc=D'\''oh!' \
--form 'quote_type=Motivation' \
--form 'author=Homero Jay  Simpson'



curl --location --request POST 'http://127.0.0.1:5000/add_quote' \
--form 'quote_desc=Tienes el micronfono apagado' \
--form 'quote_type=Motivation' \
--form 'author=Benjamin'



curl --location --request DELETE 'http://127.0.0.1:5000/remove_quote/7'












