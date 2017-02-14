Sample project using Vuetable-2 with Laravel 5.4 and Laravel Mix 
----

## Setting up
- create laravel 5.4 project
    ```
      laravel new vuetable-l54
    ```

- go into the project directory and install node packages
    ```
      npm install
    ```

- generate authentication files
    ```
      php artisan make:auth
    ```

- replace `welcome.blade.php` to extend from `layouts.app`
    ```php
      @extends('layouts.app')

      @section('content')
        <div class="container">
            <my-vuetable></my-vuetable>
        </div>
      @endsection
    ```

- install additional babel plugins
    ```
      npm install babel-plugin-transform-runtime babel-preset-stage-2 --save-dev
    ```

- install vuetable-2
    ```
      npm install vuetable-2 --save-dev
    ```

- create your Vue component in `resources\assets\js\components`
- register the component in `resources\assets\js\app.js`
    ```javascript
      Vue.component('my-vuetable', require('./components/MyVuetable.vue'));
    ```

- compile using Laravel-Mix by running
    ```
      npm run watch
    ```
