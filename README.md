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
### Contacts
#### - List contacts (Contactos)
```
contacts = client.list_contacts(order_field=None, order="ASC", limit=None, start=None)
# order options = "ASC" or "DESC"
# Max limit = 30
```
#### - Create Contact (Contacto)
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
    "identification": "1018425711",
    "mobile": "38845555610",
    "seller": 1,
    "priceList": 1,
    "term": 1,
    "email": "lina@montoya.com",
    "type": "client"
}
contact = client.create_contact(contacto)
```
#### - List sellers (Vendedores)
```
vendedores = client.list_sellers()
```
### Inventory
#### - List items (Items)
```
items = client.list_items()
```
#### - List item Categories (Categorias de items)
```
item_categorias = client.list_item_categories()
```
#### - List Warehouses (Bodegas)
```
bodegas = client.list_warehouses()
```
#### - List Variant Attributes (Variantes)
```
atributos_variantes = client.list_variant_attributes()
```
#### - List price lists (Lista de precios)
```
lista_precios = client.list_price_lists()
```
### Terms
#### - List Terms (Condiciones de pago)
```
condiciones = client.list_terms()
```
### Taxes
### - List Taxes (Impuestos)
```
impuestos = client.list_taxes()
```
### Accounts
#### - List Accounts (Cuentas)
```
cuentas = client.list_accounts()
```
#### - List Accounts Flatten (Cuentas)
```
# Returns a flatten list of accounts
cuentas = client.list_accounts_flatten()
```