# Laravel Multi-step Form
[![Latest Version on Packagist](https://img.shields.io/packagist/v/infinitypaul/laravel-multistep-forms.svg?style=flat-square)](https://packagist.org/packages/infinitypaul/laravel-multistep-forms)
[![Build Status](https://img.shields.io/travis/infinitypaul/laravel-multistep-forms/master.svg?style=flat-square)](https://travis-ci.org/infinitypaul/laravel-multistep-forms)
[![Quality Score](https://img.shields.io/scrutinizer/g/infinitypaul/laravel-multistep-forms.svg?style=flat-square)](https://scrutinizer-ci.com/g/infinitypaul/laravel-multistep-forms)
[![Total Downloads](https://img.shields.io/packagist/dt/infinitypaul/laravel-multistep-forms.svg?style=flat-square)](https://packagist.org/packages/infinitypaul/laravel-multistep-forms)

Hi Fellas! So you know how you would like to create a dynamic registration form but then you can't because you feel this is impossible with PHP.

Well, I have good news for ya, this is so POSSIBLE with this package. Yeah that's right, I mean it. Let's get down on the "how":

So we will work with a 3 step form

After installing the package, I will be creating 3 blades for the different steps of the form:
## Installation

You can install the package via composer:

```bash
composer require infinitypaul/laravel-multistep-forms
```

## Usage
1.blade.php
``` php
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>

    @extends('layouts.app')

    @section('content')

        <div class="container">
            <div class="row justify-content-center">
                <div class="col-md-8">
                    <div class="card">
                        <div class="card-header">{{ __('Register') }} </div>
                        <div class="card-body">

                            <form method="POST" action="{{ route('auth.register.1.store') }}">
                                @csrf

                                <div class="form-group row">
                                    <label for="name" class="col-md-4 col-form-label text-md-right">{{ __('Name') }}</label>

                                    <div class="col-md-6">
                                        <input id="name" type="text" class="form-control @error('name') is-invalid @enderror" name="name" value="{{ old('name') ?: $step->name }}" required autocomplete="name" autofocus>

                                        @error('name')
                                        <span class="invalid-feedback" role="alert">
                                            <strong>{{ $message }}</strong>
                                        </span>
                                        @enderror
                                    </div>


                                </div>

                                <div class="form-group row">
                                    <label for="middle" class="col-md-4 col-form-label text-md-right">{{ __('Middle Name') }}</label>
                                    <div class="col-md-6">
                                        <input id="text" type="text" class="form-control @error('middle') is-invalid @enderror" name="middle" value="{{ old('middle') ?: $step->middle }}" required autocomplete="email" autofocus>

                                        @error('middle')
                                        <span class="invalid-feedback" role="alert">
                                            <strong>{{ $message }}</strong>
                                        </span>
                                        @enderror
                                    </div>
                                </div>

                                <div class="form-group row mb-0">
                                    <div class="col-md-6 offset-md-4">
                                        <button type="submit" class="btn btn-primary">
                                            {{ __('Next') }}
                                        </button>
                                    </div>
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    @endsection

```

### Testing

``` bash
composer test
```

### Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Bugs & Fixtures
If you have spotted any bugs, or would like to request additional features from the library, please file an issue via the Issue Tracker on the project's Github page: https://github.com/infinitypaul/laravel-multistep-forms/issues.


### Security

If you discover any security related issues, please email infinitypaul@live.com instead of using the issue tracker.


## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

