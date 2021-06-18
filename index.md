## Salesforce API Open pay

Documentación Salesforce uso de API 

### Cuentas Bancarias

Se pueden almacenar múltiples cuentas bancarias por cliente o por comercio para posteriormente retirar fondos.


### BankAccount  
Objeto Cuenta Bancaria

### Petición

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

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/JuliomOrtega/OPPAPISF1/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
