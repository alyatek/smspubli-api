⚠ DISCLAIMER : This is not even close to ready for production. This is my first public package so I have a lot to learn first.

# SMSPUBLI API

SMSPUBLI API is a library that makes even easier the usage of the [SMSPUBLI](https://www.smspubli.com/) api

## Installation

Use composer to install the package.

```bash
composer require alyatek/smspubli-api
```

Make sure you also have an account at [SMSPUBLI](https://www.smspubli.com/).

## Usage

### Pay attention to the following before using!
- Make sure the `SMS NAME` is not longer than 11 characters or it will throw an error - spaces count as a character so be warned.
- The contact needs to have the country code before the actual contact without the plus sign. e.g : 351321321321
- ❗ For now only Portuguese(+351) contacts can be filtered because the package is being used on a product for PT contacts. 
  - Maybe I'll add support for more contacts in the future. If you don't want to wait just fork it and add to your needs, or if you want help this grow, open a pull request with the contact country code validation for the code you want.

```php
<?php

use SmsPubli\SmsClient;

$sms_client = new SmsClient(SMSPUBLIKEY, 'SMS NAME');
$send = $sms_client->send_sms(SMSNUMBER, 'Your Message')->getStatus();

```

The request returns an array with a boolean variable `status`, and a response from the server according to the answer received.
If it is `true` results in a `success_msg`, `sms_id` and if it is an error it returns `success_msg`, `sms_id`.


For testing you need to create a config.php file inside tests and declare the following
```php
<?php

define('SMSPUBLIKEY', 'YOUR API KEY');
define('SMSNUMBER', 'CONTACT TO SEND');

```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate if that is the case.

## License
[MIT](https://choosealicense.com/licenses/mit/)
