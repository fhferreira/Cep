# CANDUCCI CEP

[![Download Remote Image](https://fulviocanducci.files.wordpress.com/2014/12/cell-6-2-120.png)](https://packagist.org/packages/canducci/down)

## Quick start

### Required setup

In the `require` key of `composer.json` file add the following

```PHP
"canducci/cep": "dev-master"
```

Run the Composer update comand

    $ composer update

In your `config/app.php` add `'Canducci\Down\DownServiceProvider'` to the end of the `providers` array

```PHP
'providers' => array(
    ...,
    'Illuminate\Workbench\WorkbenchServiceProvider',
    'Canducci\Cep\CepServiceProvider',

),
```

At the end of `config/app.php` add `'Down' => 'Canducci\Down\Facade\Down'` to the `aliases` array

```PHP
'aliases' => array(
    ...,
    'View'       => 'Illuminate\Support\Facades\View',
    'Cep '       => 'Canducci\Cep\Facade\Cep',

),
```

##How to Use

To use is very simple, pass the ZIP and calls the various types of returns, like this:

```PHP
$cep = Cep::find('19200000');
```

Type returns:
```PHP    
$cep->toJon();

    {
        "cep": "01414-001",
        "logradouro": "Rua Haddock Lobo",
        "bairro": "Cerqueira César",
        "localidade": "São Paulo",
        "uf": "SP",
        "ibge": "3550308"
    }
```

```PHP    
$cep->toArray();
```

```PHP    
$cep->toObject();
```

```PHP    
$cep->toXml();
```

```PHP    
$cep->toSimpleXml();
```

```PHP    
$cep->toPiped();
```
    
```PHP    
$cep->toQuerty();
```   
    
