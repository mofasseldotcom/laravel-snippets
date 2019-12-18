## Laravel6 Tutorial by Mofassel

Laravel6 Tutorial is a software specially designed & developed to maintain day to day activities of Car selling, washing, reparing shop. We create awesome software for our valuable cients. Don't forget to ask us if you need one.

- [GitHub URL](https://github.com/mofasseldotcom/laravel6-tutorial).

## Laravel6 Tutorial

###1. Migrate error: "Specified key was too long ...." Issue can be fixed in both way. Use any one mentioned bellow.

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

	



## Contributing

Thank you for considering contributing 

## Security Vulnerabilities

If you discover a security vulnerability within Laravel6 Tutorial, please send an e-mail to Mofassel via [contact@mofassel.com](mailto:contact@mofassel.com). All security vulnerabilities will be promptly addressed.

## License

Laravel6 Tutorial is open-source software guideline, licensed under the [MIT license](https://opensource.org/licenses/MIT).
