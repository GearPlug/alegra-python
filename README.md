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
contacts = client.list_contacts()
```
### List sellers (Vendedores)
```
vendedores = client.list_sellers()
```