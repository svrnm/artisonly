# Artisan + Phar = Artisonly (Standalone Commandline Toolbox)

You can use [box2](https://github.com/box-project/box2/) and this modified version of laravel's [lumen](http://lumen.laravel.com/) to pack the artisan file into a standalone command line tool(box) that you can put into your shell's search path. So you can call ***inspire*** wherever you are!

## Installation

1. clone this project:

```
# https://github.com/svrnm/artisonly artisonly
```

2. Call composer from within the newly created directory:

```
# composer update
```

3. If not available, install [box2](https://github.com/box-project/box2/) globally:

```
composer global require kherge/box --prefer-source
```

4. Create the ```artisan.phar``` binary:

```
# box build
```

5. If the build process succeeds, test if you can call inspire:

```
# ./artisan.phar inspire
```

6. Finally, if you like you can install it globally and call inspire:

```
# sudo cp ./artisan.phar /usr/local/bin/artisonly
# sudo ln /usr/local/bin/artisan.phar /usr/local/bin/inspire
# inspire
```


## Usage

By default the (modified) artisan command does only provide a simple version of ```inspire```. Unlikey laravel there is (currently) no convenient ```php artisan make:console``` command, but you can just copy (or rename) the inspire example:

```
# cp app/Console/Commands/Inspire.php app/Console/Commands/HelloWorld.php
```

Edit this file as you like and provide a unique signature:

```php
protected $signature = 'hello-world';
```
Next you can build the ```artisan.phar``` using ```box build``` and if you like you can install your tools globally:

```
# sudo cp ./artisan.phar /usr/local/bin/artisonly
# sudo ln /usr/local/bin/artisan.phar /usr/local/bin/hello-world
# hello-world
```



## License

This is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
