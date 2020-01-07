## Laravel6 Tutorial by Mofassel

Laravel6 Tutorial is a software specially designed & developed to maintain day to day activities of Car selling, washing, reparing shop. We create awesome software for our valuable cients. Don't forget to ask us if you need one.

- [GitHub URL](https://github.com/mofasseldotcom/laravel6-tutorial).

## Laravel6 Tutorial

### Migrate error: "Specified key was too long ...." Issue can be fixed in both way. Use any one mentioned bellow.

	use Illuminate\Support\Facades\Schema;

	public function boot()
	{
	    Schema::defaultStringLength(191);
	}
	-------------------------------------------
	use Illuminate\Database\Schema\Builder;

	public function boot()
	{
	    Builder::defaultStringLength(191);
	}

	
### Add AdminLte template with Laravel

	composer require "almasaeed2010/adminlte=~3.0"

### Create controller with resource route

	php artisan make:controller NameController --resource

### Create migration of Name Table

	php artisan make:migration create_names_table

### Run migrate to create table into database

	php artisan migrate

### Create model, add -m to create migration also

	php artisan make:model Name -m

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
	$image = Image::make('public/foo.jpg')->resize(300, 200)->save();





## Contributing

Thank you for considering contributing 

## Security Vulnerabilities

If you discover a security vulnerability within Laravel6 Tutorial, please send an e-mail to Mofassel via [contact@mofassel.com](mailto:contact@mofassel.com). All security vulnerabilities will be promptly addressed.

## License

Laravel6 Tutorial is open-source software guideline, licensed under the [MIT license](https://opensource.org/licenses/MIT).
