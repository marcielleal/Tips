# LaravelTips
This is a repository to store some tips and tricks that I discovered about Laravel 5.

Author: [Marciel Leal](https://github.com/marcielleal)

Email: marcielmanoel15@gmail.com
## App
### Making models to another directory
If you need to create Models to another directory, do this:
```ShellScript
$ php artisan make:model Path/to/Directory/Model
```
This code will create the file Model.php into app/Path/to/Directory. Its namespace will be the same of your directory's path.

### Changing the User Model from the default namespace
If you changed the User Model namespace, the authentication only works if you change the configurations of auth. Open config/auth.php file and looks for something like that:
```php
'providers' => [
  'users' => [
    'driver' => 'eloquent',
    'model' => App\User::class,
  ],
],
```
Change the **App\User::class** for **Your\New\Namespace\User::class**

## Database
### Foreign keys on Laravel's migrations
You **need** to declare the foreign key as an unsigned integer. Nobody seems to know why exactly.

### Model
#### create
Static method from Model that create and save the model in database. It instanciates a new model and runs save method, then return model.

#### forceCreate
Do same as create, but ignores fillable attributes

## Views
### Scripts
Apparently, all scripts outside of sections are not executed.
So, if you need to put different scripts on your pages, you can yield a section for scripts on your parent view and call this section on your child views.

### Validation
Ways to create new rules:
* Creating a new Rule class (you can do that using make:rule artisan command
* Declaring a closure in rules array
* Extending validator on AppProvider

## Routes
### route vs url
Both generates a full url from a string. 
* **url** needs a parameter which is a local url from the project. 
* **route** needs a parameter which is the name of a Route (routes are declared on routes/something.php).

**route** depends only on the Route name. So if you name a Route and use **route** to generate a link for this route, you can change anytime the actual url of this Route and the link generated by **route** will be changed too.

### Route resources
You can declare all tradicional routes of a CRUD controller in one line (at routes/web.php or another route file that you are using):
```php
Route::resource('example','ExampleController');
```
This will create all necessary routes under '/example' url. To see all routes that this method creates:
```ShellScript
$ php artisan route:list
```
If you want a custom CRUD:
```php
Route::resource('lotacoes', 'LotacoesController',[
  'only' => ['index', 'create', 'store'],
]);
```
This will create only the routes index, create and store. Or you can do this:
```php
Route::resource('lotacoes', 'LotacoesController',[
  'except' => [ 'show' ]
]);
```
This will create all routes except the show route.
