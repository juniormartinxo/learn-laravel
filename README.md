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
2) Inicie o servidor com `php artisan serve` e guarde o resultado da saída `Starting Laravel development server:`
3) Edite o arquivo `webpack.mix.js` e coloque no final o seguinte código:

```js
mix.browserSync({
    proxy: 'http://127.0.0.1:8000'
})
```

> O valor de proxy tem que possuir o valor da saída citada no `item 2`

