# PHP Apache2 Basic Auth

A really simple class service for .htaccess Basic Auth using .htpasswd and .htgroups files.

Original HtPasswd and HtGroup classes from
[Yang Yang](http://www.kavoir.com/2012/04/php-class-for-handling-htpasswd-and-htgroup-member-login-user-management.html)

If you want a running app using this lib, see
[PHP Apache2 Basic Auth Manager](https://github.com/rafaelgou/php-apache2-basic-auth-manager)

## Installation

This standard can be installed with the [Composer](https://getcomposer.org/)
dependency manager.

1.  [Install Composer](https://getcomposer.org/doc/00-intro.md)
2.  Install the coding standard as a dependency of your project

```bash
composer require --dev rafaelgou/php-apache2-basic-auth
```

## Using

You need to define a `.htpasswd` file and a optionally a `.htgroups` file.

### Instanciate the Service

```php
<?php

// ...
use Apache2BasicAuth\Service as HTService;

$htService = new HTService(
    'PATH_TO/.htpasswd',
    'PATH_TO/.htgroups'
);
```

### Creating a Group

```php
<?php

// ... Instanciate the Service ...

// Create a new group
$group = $htService->createGroup();
$group->setName('admin')
    ->addUser('mateus')
    ->addUser('tiago');

// Groups can be also set:
$group->setUsers(array('bernardo', 'larissa'));

// Staging to write    
$htService->persist($group);

// Writing to disc
$htService->write();
```

### Editing a Group

```php
<?php

// ... Instanciate the Service ...

// Create a new group
$group = $htService->findGroup('admin');
$group
    ->removeUser('mateus')
    ->addUser('ana');

// Staging to write    
$htService->persist($group);

// Writing to disc
$htService->write();
```

### Deleting a Group

```php
<?php

// ... Instanciate the Service ...

// Create a new group
$group = $htService->findGroup('admin');

// Staging to write    
$htService->htService->removeGroup($group);

// Writing to disc
$htService->write();
```

### Creating a User

```php
<?php

// ... Instanciate the Service ...

// Create a new user
$user = $htService->createUser();
$user->setUsername('rafael')
    ->setPassword('my_pass_123')
    ->setAddGroup('admin')
    ->setAddGroup('finance');

// Groups can be also set:
$user->setGroups(array('opperations', 'support'));

// Staging to write    
$htService->persist($user);

// Writing to disc
$htService->write();
```

**OBS**: When you set a password the hashed password is updated.

### Editing a user

```php
<?php

// ... Instanciate the Service ...

// Finding an existing user
$user = $htService->findUser('rafael');
$user->setPassword('my_pass_123')
    ->removeGroup('admin')
    ->setAddGroup('marketing');

// Staging to write    
$htService->persist($user);

// Writing to disc
$htService->write();
```

**OBS**: When you set a password the hashed password is updated. If not set,
old hash is kept.

### Deleting a user

```php
<?php

// ... Instanciate the Service ...

// Finding an existing user
$user = $htService->findUser('rafael');

// Staging to write    
$htService->htService->removeUser($user);

// Writing to disc
$htService->write();
```

### Listing Groups and Users

```php
<?php

// ... Instanciate the Service ...

// Getting Users
$users = $htService->getUsers();

// The key is the username too
foreach ($users as $username => $user) {
    echo $user->getUsername();
    echo $user->getHash(); // Hashed password
    echo implode(', ', $user->getGroups());
}

// Getting Groups
$groups = $htService->getGroups();

// The key is the username too
foreach ($groups as $groupname => $group) {
    echo $group->getName();
    echo implode(', ', $user->getUsers());
}

```

 ## Full API

See [API](docs/README.md)
