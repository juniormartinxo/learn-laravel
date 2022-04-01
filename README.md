# Estudando Laravel

### Criando projeto com Composer
```
composer create-project laravel/laravel example-app
```


### Inciando o servidor
```
php artisan serve
```

### Habilitando Live Reload com o Mix :: BrownserSync
1) Rode o comando `yarn` para instalar as dependências
2) Inicie o servidor com `php artisan serve` e guarde o resultado da saída `Starting Laravel development server:`, ou seja, o endereço que a aplicação irá rodar em `localhost`
3) Edite o arquivo `webpack.mix.js` e coloque no final o seguinte código:

```js
mix.browserSync({
    proxy: 'http://127.0.0.1:8000'
})
```

> O valor de proxy tem que possuir o valor da saída citada no `item 2`


### Gerando uma `key` no Laravel
```
php artisan key:generate
```


### Prettier formatter Laravel Blade no VSCode
1) Instale o plugin do PHP no prettier
```
yarn global add prettier @prettier/plugin-php
```

2) Instalar as extensões no VSCode:
    - Laravel Bladde Formatter (Laravel Blade formatter for VSCode)
    - lararavel-blade (Laravel blade syntax highlighting)

3) Reinicie o VSCode e crie o arquivo `.bladeformatterrc` na raiz do projeto e deixe-o desta forma:
```json
{
    "indentSize": 4,
    "wrapAttributes": "auto",
    "wrapLineLength": 120,
    "endWithNewLine": true,
    "useTabs": false,
    "sortTailwindcssClasses": true
}
```

### Determining If An Uploaded File Is Valid
```php
if (Input::file('photo')->isValid())
{
    //
}
```

### Moving An Uploaded File
```php
Input::file('photo')->move($destinationPath);
Input::file('photo')->move($destinationPath, $fileName);
```

### Retrieving The Path To An Uploaded File
```php
$path = Input::file('photo')->getRealPath();
```

### Retrieving The Original Name Of An Uploaded File
```php
$name = Input::file('photo')->getClientOriginalName();
```

### Retrieving The Extension Of An Uploaded File
```php
$extension = Input::file('photo')->getClientOriginalExtension();
```

### Retrieving The Size Of An Uploaded File
```php
$size = Input::file('photo')->getSize();
```

### Retrieving The MIME Type Of An Uploaded File
```php
$mime = Input::file('photo')->getMimeType();
```
