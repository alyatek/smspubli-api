⚠ DISCLAIMER : This is not even close to ready for production. This is my first public package so I have a lot to learn first.

<p align="center">
  <img alt="logo" src="https://i.imgur.com/ac9RgHZ.png">
</p>
<p align="center">
<img alt="phpv" src="https://img.shields.io/packagist/php-v/alyatek/smspubli-api">
<img alt="codacy" src="https://api.codacy.com/project/badge/Grade/8fcdb2abf1cd4cae8abd358605caede3">
<img alt="codeclimate" src="https://codeclimate.com/github/alyatek/smspubli-api/badges/gpa.svg">
<img alt="scrutinizer" src="https://scrutinizer-ci.com/g/alyatek/smspubli-api/badges/build.png?b=master">  
<img alt="packagyst" src="https://img.shields.io/packagist/l/alyatek/smspubli-api">  
</p>

Even though their api documentation is super simple and easy to understand I wanted an even simpler way of using it.
The package is currently very simple and only does one thing, sends a sms, even though it validates the numbers and certain contents, I want to improve it in the future.

## Installation

Use composer to install the package.

```bash
composer require alyatek/smspubli-api
```

Make sure you also have an account at [SMSPUBLI](https://www.smspubli.com/) and get your [key](https://panel.smspubli.com/app/api/api_key/).

## Usage

### Pay attention to the following before using!
- Make sure the `SMS NAME` is not longer than 11 characters or it will throw an error - spaces count as a character so be warned.
- The contact needs to have the country code before the actual contact without the plus sign. e.g : 351321321321
- ❗ For now only Portuguese(+351) contacts can be filtered because the package is being used on a product for PT contacts. 
  - Maybe I'll add support for more contacts in the future. If you don't want to wait just fork it and add to your needs, or if you want help this grow, open a pull request with the contact country code validation for the code you want.


![Example Code](https://i.imgur.com/yEDyni6.png)

The request returns an array with a variable `status`, with the server request status(200 if request was ok).

If it is success - return an array a `success_msg`, `sms_id` and if it is an error - it returns an array with `success_msg`, `sms_id`.

If Guzzle throws an error, it is returned a message with a status of false.

### Testing
For testing copy the ```phpunit.example.xml``` and define the variables with the SMS PUBLI api key and the others.
Then just run ```./vendor/bin/phpunit tests``` to test.

-------

This is not an official package of smspubli.com, in the time of writing this is not, in anyway, affiliated or partned with smspubli.com .
If I'm infringing any violation with the company image please let me know @ cesar@cesarcorreia.pt

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate if that is the case.

## License
[MIT](https://choosealicense.com/licenses/mit/)
