## CPanel/WHM API for PHP library

## Contents
- [Installation Guide](#installation-guide)
- [Usage](#usage)
- [Functions](#functions)
- [Feedback & Contribution](#feedback-&-contribution)

### Installation Guide

To install this package, you can run this code via your terminal
```shell
	composer require gufy/cpanel-whm:dev-master
```
Or update your `composer.json` by adding this line
```json
	"gufy/cpanel-php":"~1.0"
```

Then, run this code
```shell
	composer update
```

### Usage

For example, if you would like to get list accounts of your whm server, you can do this.

```php
  <?php
  $cpanel = new \Gufy\CpanelPhp\Cpanel([
      'host'        =>  'https://123.456.789.123:2087', // ip or domain complete with its protocol and port
      'username'    =>  'root', // username of your server, it usually root.
      'auth_type'   =>  'hash', // set 'hash' or 'password'
      'password'    =>  'password', // long hash or your user's password
  ]);

  $accounts = $cpanel->listaccts(); // it will returned as array

```

### Functions

- [Defining Configuration on constructor](#defining-configuration-on-constructor)
- [Overriding Current configuration](#overriding-current-configuration)
- [Get defined configuration](#get-defined-configuration)

#### Defining Configuration on constructor
This is the example when you want to define your configuration while creating new object

```php
  <?php
  $cpanel = new \Gufy\CpanelPhp\Cpanel([
      'host'        =>  'https://123.456.789.123:2087', // required
      'username'    =>  'root', // required
      'auth_type'   =>  'hash', // optional, default 'hash'
      'password'    =>  'password', // required
  ]);
```

#### Overriding current configuration
Somehow, you want to override your current configuration. To do this, here is the code

```php
  <?php
  // change username andd (password or hash)
  $cpanel->setAuthorization($username, $password);

  // change host
  $cpanel->setHost($host);

  // change authentication type
  $cpanel->setAuthType($auth_type);
```

#### Get defined configuration
After you define some of your configuration, you can get it again by calling this functions

```php
  <?php
  // get username
  $cpanel->getUsername();

  // get password
  $cpanel->getPassword();

  // get authentication type
  $cpanel->getAuthType($auth_type);

  // get host
  $cpanel->getHost();
```

#### Feedback and contribution

This package is free and open source, feel free to fork and report some issue to this package. :-)