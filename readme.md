Sample project using Vuetable-2 with Laravel 5.4 and Laravel Mix 
----

## Trying this sample project
- clone the repo to your local machine
- `cd` into the directory
- install laravel dependency packages using `composer install`
- create `.env` file and generate APP_KEY using `cp .env.example .env && php artisan key:generate`
- install client-side javascript packages dependency by `npm install`
- run the project using `php artisan serve` or whatever appropriate in your machine setup.

You should see something like this.

![image](https://raw.githubusercontent.com/ratiw/images/master/vuetable-2/vuetable-2-laravel-5.4-mix.png)

## Steps to use Vuetable-2 in your Laravel 5.4 project
- create laravel 5.4 project
    ```
      laravel new vuetable-l54
    ```

- go into the project directory and install node packages
    ```
      npm install
    ```

- create `.env` file by copying from `.env.example`
    ```
      cp .env.example .env
    ```

- generate APP_KEY
    ```
      php artisan key:generate
    ```

- generate authentication files
    ```
      php artisan make:auth
    ```

- replace `welcome.blade.php` with the version in the repo or just add component
- install additional babel plugins
    ```
      npm install babel-plugin-transform-runtime babel-preset-stage-2 bable-preset-es2015 --save-dev
    ```

- install vuetable-2
    ```
      npm install vuetable-2 --save-dev
    ```

- install vuetable-2 dependencies
    ``` npm install accounting lodash moment vue-events --save-dev

- create your Vue component in `resources\assets\js\components`
- register the component in `resources\assets\js\app.js`
    ```javascript
      Vue.component('my-vuetable', require('./components/MyVuetable.vue'));
    ```

- compile using Laravel-Mix by running
    ```
      npm run dev
    ```
