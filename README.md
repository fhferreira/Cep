# CANDUCCI CEP

[![Download Remote Image](https://fulviocanducci.files.wordpress.com/2014/12/cell-6-2-120.png)](https://packagist.org/packages/canducci/down)

## Quick start

### Required setup

In the `require` key of `composer.json` file add the following

    "canducci/cep": "dev-master"

Run the Composer update comand

    $ composer update

In your `config/app.php` add `'Canducci\Down\DownServiceProvider'` to the end of the `providers` array

    'providers' => array(
        ...,
        'Illuminate\Workbench\WorkbenchServiceProvider',
        'Canducci\Cep\CepServiceProvider',

    ),

At the end of `config/app.php` add `'Down' => 'Canducci\Down\Facade\Down'` to the `aliases` array

    'aliases' => array(
        ...,
        'View'       => 'Illuminate\Support\Facades\View',
        'Cep '       => 'Canducci\Cep\Facade\Cep',

    ),

##How to Use

