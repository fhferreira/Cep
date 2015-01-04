# Download Remote Image

[![Download Remote Image](https://fulviocanducci.files.wordpress.com/2014/12/cell-6-2-120.png)](https://packagist.org/packages/canducci/down)

## Quick start

### Required setup

In the `require` key of `composer.json` file add the following

    "canducci/down": "dev-master"

Run the Composer update comand

    $ composer update

In your `config/app.php` add `'Canducci\Down\DownServiceProvider'` to the end of the `providers` array

    'providers' => array(
        ...,
        'Illuminate\Workbench\WorkbenchServiceProvider',
        'Canducci\Down\DownServiceProvider',

    ),

At the end of `config/app.php` add `'Down' => 'Canducci\Down\Facade\Down'` to the `aliases` array

    'aliases' => array(
        ...,
        'View'       => 'Illuminate\Support\Facades\View',
        'Down'       => 'Canducci\Down\Facade\Down',

    ),

##How to Use

__To save an image that is in any internet address do:__

    $pathAndNameImagem = Down::load('http://imagem.com/0001.jpg')->save('imagens/');
    
__If you want to spend a name to save this image do:__

    $pathAndNameImagem = Down::load('http://imagem.com/0001.jpg')->save('imagens/', 'nameImage');
    
__You can also reduce the image size:__    

    $pathAndNameImagem = Down::load('http://imagem.com/0001.jpg')->resize(500,200)->save('imagens/');

__or__

    $pathAndNameImagem = Down::load('http://imagem.com/0001.jpg')->resize(500,200)->save('imagens/', 'nameImage');
    
__You can also generate a file in the base 64 like this:__

    $down   = Down::load($url);
	$base64 = $down->render64();
	
__Finally, you can generate a route to be loaded and an img tag type like this:__

**html**

    <img src="/call/image">

**function**

    public function image(){
		$url = 'http://imagem.com/0001.jpg';
		$down = Down::load($url); 
		return $down->render();
	}
	

