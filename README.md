## Laravel6 Snippets by Mofassel

Laravel Tutorial is a software specially designed & developed to maintain day to day activities of Car selling, washing, reparing shop. We create awesome software for our valuable cients. Don't forget to ask us if you need one.

- [GitHub URL](https://github.com/mofasseldotcom/laravel-snippets).

## Laravel Snippets

### Migrate error: "Specified key was too long ...." Issue can be fixed in both way. Use any one mentioned bellow.

    // on top of class declaration
    use Illuminate\Support\Facades\Schema;

    // inside boot method
    Schema::defaultStringLength(191);

### Create migration of Name Table

    php artisan make:migration create_names_table

### Run migrate to create table into database

    php artisan migrate

### Create model, add -m to create migration also

    php artisan make:model Name -m

### Create controller

    php artisan make:controller NameController
    // Resource Controller
    php artisan make:controller NameController --resource

### Create seeder for Users Table

    php artisan make:seeder UsersTableSeeder
    // Add bellow code into DatabaseSeeded.php file
    $this->call(UsersTableSeeder::class);

### Create factory for Post model, add --m=Post to prefill model name

    php artisan make:factory PostFactory --model=Post
    // Add bellow code into DatabaseSeeded.php file
    factory(\App\Model::class,10)->create();

### Use intervention/image to resize or fit image

    composer require intervention/image

    // add on top of controller
    use Intervention\Image\Facades\Image::class
    // Insert bellow code inside function to make it useable
    \$image = Image::make('public/foo.jpg')->resize(300, 200)->save();

### Add AdminLte template with Laravel

    composer require "almasaeed2010/adminlte=~3.0"

### Form validation

    // inside store / update method of controller file

    $request->validate([
    	'feildName' => 'required'
    	],
    	[
    		'fieldName.required' => 'custorm error message',
    	]
    )

    // inside blade file
    @if ($errors->any())
    <div class="alert alert-danger">
    <ul>
    	@foreach ($errors->all() as $error)
    	<li>{{ $error }}</li>
    	@endforeach
    </ul>
    </div>
    @endif

    // beside input field
    @error('fieldName')
    	<div class="alert alert-danger">{{ $message }}</div>
    @enderror

## REST API development essentials

### Need to write route in api.php route file

    // get/post/put/delete
    Route::get('routename', ControllerName@methodName);
    // resource route
    Route::apiResource('routename', ControllerName);

### Model & controller as like regular CRUD development

    // json message returing
    if(is_null($data)){
    return response()->json(['message' => 'Actual message to show'], 404);
    }

    // json data returning
    return response()->json([
    'message' => 'Actual message to show',
    'data' => $data
    ], 200);

### validation

    // on top of class name declartion
    use Validator;

    // inside store / update method of controller file
    $rules = [
    	'fieldName' => 'required',
    ];

    $validator = Validator::make($request->all(), $rules);
    if($validator->fails()){
    	return response()->json($validator->errors(), 400);
    }

### Token generation for api access

    // need to create a middleware
    php artisan make:middleware AuthKey

    // inside handle method of newly created AuthKey middleware file

    $token = $request()->header('APP_KEY');
    if($token != 'ABCDEDFG'){
    	return response()->json('message' => 'APP_KEY not found!', 401);
    }
    return $next($request);

    // inside Http kernel file, api array
    \App\Http\Middleware\AuthKey::class,

### Basic Authentication for api access

    // need to create a middleware
    php artisan make:middleware AuthBasic

    // inside handle method of newly created AuthBasic middleware file
    if(Auth::onceBasic()){
    	return response()->json('message' => 'Auth failed!', 401);
    }
    return $next($request);

    // on top of this middleware file include
    \Illuminate\Support\Facades\Auth;

    // inside Http kernel file, api array
    \App\Http\Middleware\AuthBasic::class,

## Contributing

Thank you for considering contributing

## Security Vulnerabilities

If you discover a security vulnerability within Laravel6 Tutorial, please send an e-mail to Mofassel via [contact@mofassel.com](mailto:contact@mofassel.com). All security vulnerabilities will be promptly addressed.

## License

Laravel6 Tutorial is open-source software guideline, licensed under the [MIT license](https://opensource.org/licenses/MIT).
