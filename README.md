![](https://img.shields.io/badge/version-0.1.1-success) ![](https://img.shields.io/badge/Python-3.8%20|%203.9%20|%203.10%20|%203.11-4B8BBE?logo=python&logoColor=white)
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
items = client.list_items(order_field=None, order="ASC", limit=None, start=None)
# order options = "ASC" or "DESC"
# Max limit = 30
```
#### - Create item (Item)
```
item = {
    "name": "PS5",
    "description": "Play Station 5",
    "reference": "PS5 nuevo",
    "price": 3750000,
    "category": {"id": 5064},
    "inventory": {
        "unit": "unit",
        "unitCost": 40000,
        "negativeSale": False,
        "warehouses": [{"initialQuantity": 4, "id": 1, "minQuantity": 2, "maxQuantity": 10}],
    },
    "tax": 2,
    "type": "product",
    "customFields": [{"id": 1, "value": "BHUJSK888833"}, {"id": 2, "value": 44}, {"id": 3, "value": 44.45}],
    "itemCategory": {"id": 1}
}
item_created = client.create_item(item)
```
#### - List item Categories (Categorias de items)
```
item_categorias = client.list_item_categories()
```
#### - List Warehouses (Bodegas)
```
bodegas = client.list_warehouses()
```
#### - List Item Custom Fields (Campos adicionales)
```
campos = client.list_item_custom_fields()
```
#### - List Variant Attributes (Variantes)
```
atributos_variantes = client.list_variant_attributes()
```
#### - List price lists (Lista de precios)
```
lista_precios = client.list_price_lists()
```
### Invoices
#### - List invoices (Facturas de venta)
```
items = client.list_invoices(order_field=None, order="ASC", limit=None, start=None, date=None)
# order options = "ASC" or "DESC"
# Max limit = 30
# Date format YYYY-MM-DD
```
### Terms
#### - List Terms (Condiciones de pago)
```
condiciones = client.list_terms()
```
### Taxes
#### - List Taxes (Impuestos)
```
impuestos = client.list_taxes()
```
### Accounts
#### - List Accounts (Cuentas)
```
cuentas = client.list_accounts(format_acc="tree", type_acc=None)
# format_acc options = "tree" or "plain"
# type_acc options = "income", "expense", "asset", "liability" or "equity"
```
