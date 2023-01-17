# alegra-python

*alegra-python* is an API wrapper for Alegra (accounting software), written in Python

## Installing
```
pip install alegra-python
```
## Usage
```
client = Client(email, token)
```
### Get company information (Compañía)
```
company = client.get_company_info()
```
### Get current user (Usuario)
```
user = client.get_current_user()
```
### List contacts (Contactos)
```
contacts = client.list_contacts(order_field=None, order="ASC", limit=None, start=None)
# order options = "ASC" or "DESC"
# Max limit = 30
```
### Create Contact (Contacto)
```
contacto = {
    "address": {"city": "Villavicencio", "address": "Calle 10 #01-10"},
    "internalContacts": [
        {
            "name": "Lina",
            "lastName": "Montoya",
            "email": "prueba4@alegra.com",
        }
    ],
    "name": "Lina Montoya",
    "identification": "1018425722",
    "mobile": "38845555610",
    "seller": 1,
    "priceList": 1,
    "term": 1,
    "email": "lina@montoya.com",
    "type": "client"
}
contact = client.create_contact(contacto)
```
### List sellers (Vendedores)
```
vendedores = client.list_sellers()
```
### List price lists (Lista de precios)
```
lista_precios = client.list_price_lists()
```
### List Terms (Lista de condiciones de pago)
```
condiciones = client.list_terms()
```
### List Accounts (Listado de cuentas)
```
condiciones = client.list_accounts()
```