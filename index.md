## Salesforce API Open pay

Documentación Salesforce uso de API 

### Cuentas Bancarias

Se pueden almacenar múltiples cuentas bancarias por cliente o por comercio para posteriormente retirar fondos.


#### Crear Cuenta Bancaria
###### BankAccount Objeto Cuenta Bancaria

#### Petición

Propiedad | Descripción
------------ | -------------
holder_name |	**string** (requerido, longitud = 80)
alias |	**string** (opcional, longitud = 45) 
clabe |**string** (requerido, longitud = 45)

```java
//======================================================================================================
// Crea y asigna una cuenta bancaria al cliente espeficado.
//======================================================================================================
OpenpayAPI api = new OpenpayAPI('https://sandbox-api.openpay.mx',
'{Llave Privada}', '{MERCHANT_ID}');

BankAccount request = new BankAccount();
request.Clabe('032180000118359719');
request.Alias('Cuenta principal');
request.HolderName('Juan Hernández Sánchez');

request = api.bankAccounts().create('aqiyel6y0zfvpa6eptav',request);
system.debug('>>>request'+ request);

```

##### Respuesta 
Regresa un objeto cuenta bancaria


#### Obtener una cuenta bancaria
Obtiene los detalles de una cuenta bancaria asignada a un cliente

#### Petición

Propiedad | Descripción
------------ | -------------
id |	**string** (requerido, longitud = 45)


```java
//==================================================================
// obtiene cuenta bancaria al cliente espeficado.
//==================================================================
OpenpayAPI api = new OpenpayAPI('https://sandbox-api.openpay.mx',
'{Llave Privada}', '{MERCHANT_ID}');

//(ID Customer , BankAccount ID )
BankAccount request = new BankAccount();
request = api.bankAccounts().get('aqiyel6y0zfvpa6eptav',
                                'bzyrdyyrbzkkb9aehh5d');
system.debug('>>>request'+ request);
```
##### Respuesta 
Regresa un objeto cuenta bancaria

#### ELimina una cuenta bancaria
Obtiene los detalles de una cuenta bancaria asignada a un cliente

#### Petición

Propiedad | Descripción
------------ | -------------
id |	**string** (requerido, longitud = 45)


```java
//==================================================================
// Elimina cuenta bancaria al cliente espeficado.
//==================================================================
OpenpayAPI api = new OpenpayAPI('https://sandbox-api.openpay.mx',
'{Llave Privada}', '{MERCHANT_ID}');

BankAccount request = new BankAccount();
request.Clabe('032180000118359719');
request.Alias('Cuenta principal');
request.HolderName('Juan Hernández Sánchez');

request = api.bankAccounts().remove('aqiyel6y0zfvpa6eptav',request);
system.debug('>>>request'+ request);

```
##### Respuesta 
Si la cuenta bancaria se borra correctamente la respuesta es vacía,
 si no se puede borrar se regresa un objeto error indicando el motivo.


#### ELimina una cuenta bancaria
Obtiene los detalles de una cuenta bancaria asignada a un cliente

#### Petición

Propiedad | Descripción
------------ | -------------
id |	**string** (requerido, longitud = 45)


```java
//==================================================================
// listado de cuenta bancarias.
//==================================================================
OpenpayAPI api = new OpenpayAPI('https://sandbox-api.openpay.mx',
'{Llave Privada}', '{MERCHANT_ID}');

SearchParams searchparams = new SearchParams ();
List<BankAccount> ListbankAccount  = 
api.bankAccounts().getList('ato3eklzedfccxho1yiz',searchparams.limitSize (2));
system.debug('>>>ListbankAccount'+ ListbankAccount);

```
##### Respuesta 
Listado de objetos cuenta bancaria

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/JuliomOrtega/OPPAPISF1/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
