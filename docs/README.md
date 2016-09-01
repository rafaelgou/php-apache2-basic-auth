# PHP Apache2 Basic Auth Manager

## Table of Contents

* [Group](#group)
    * [__construct](#__construct)
    * [setName](#setname)
    * [getName](#getname)
    * [setUsers](#setusers)
    * [getUsers](#getusers)
    * [hasUser](#hasuser)
    * [addUser](#adduser)
    * [removeUser](#removeuser)
    * [formatHT](#formatht)
* [Service](#service)
    * [__construct](#__construct-1)
    * [readGroups](#readgroups)
    * [writeGroups](#writegroups)
    * [readPasswd](#readpasswd)
    * [writePasswd](#writepasswd)
    * [read](#read)
    * [write](#write)
    * [getGroups](#getgroups)
    * [setGroups](#setgroups)
    * [persistGroup](#persistgroup)
    * [removeGroup](#removegroup)
    * [findGroup](#findgroup)
    * [getGroupNames](#getgroupnames)
    * [getUsernames](#getusernames)
    * [createGroup](#creategroup)
    * [getUsers](#getusers-1)
    * [setUsers](#setusers-1)
    * [persistUser](#persistuser)
    * [removeUser](#removeuser-1)
    * [createUser](#createuser)
    * [findUser](#finduser)
    * [persist](#persist)
* [User](#user)
    * [__construct](#__construct-2)
    * [setUsername](#setusername)
    * [getUsername](#getusername)
    * [setPassword](#setpassword)
    * [getPassword](#getpassword)
    * [setGroups](#setgroups-1)
    * [getGroups](#getgroups-1)
    * [addGroup](#addgroup)
    * [removeGroup](#removegroup-1)
    * [hasGroup](#hasgroup)
    * [getHash](#gethash)
    * [setHash](#sethash)
    * [formatHT](#formatht-1)

## Group

Group Model



* Full name: \Apache2BasicAuth\Model\Group


### __construct

Constructor

```php
Group::__construct( string $name = null, array $users = array() )
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$name` | **string** | Group name |
| `$users` | **array** | Users |




---

### setName

Set name

```php
Group::setName( string $name ): \Apache2BasicAuth\Model\Apache2BasicAuth\Model\Group
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$name` | **string** | Group name |




---

### getName

Get name

```php
Group::getName(  ): string
```







---

### setUsers

Set users

```php
Group::setUsers( array $users ): \Apache2BasicAuth\Model\Apache2BasicAuth\Model\User
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$users` | **array** | Users |




---

### getUsers

Get Users

```php
Group::getUsers(  ): array
```







---

### hasUser

Check if group has a user

```php
Group::hasUser( string $user ): boolean
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$user` | **string** | User name |




---

### addUser

Add a user

```php
Group::addUser( string $user ): \Apache2BasicAuth\Model\Apache2BasicAuth\Model\User
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$user` | **string** | User name |




---

### removeUser

Remove a user

```php
Group::removeUser( string $user ): \Apache2BasicAuth\Model\Apache2BasicAuth\Model\User
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$user` | **string** | User name |




---

### formatHT

Format to HT write

```php
Group::formatHT(  ): string
```







---

## Service

HT Service



* Full name: \Apache2BasicAuth\Service


### __construct

Constructor

```php
Service::__construct( string $passwdFile, string $groupFile = null )
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$passwdFile` | **string** | The .htpasswd filename |
| `$groupFile` | **string** | The .htgroups filename |




---

### readGroups

Read .htgroups file from disc

```php
Service::readGroups(  ): \Apache2BasicAuth\Apache2BasicAuth\Service
```







---

### writeGroups

Write .htgroups file to disc

```php
Service::writeGroups(  ): \Apache2BasicAuth\Apache2BasicAuth\Service
```







---

### readPasswd

Read .htpasswd file from disc

```php
Service::readPasswd(  ): \Apache2BasicAuth\Apache2BasicAuth\Service
```







---

### writePasswd

Write .htpasswd file to disc

```php
Service::writePasswd(  ): \Apache2BasicAuth\Apache2BasicAuth\Service
```







---

### read

Read files from disc

```php
Service::read(  ): \Apache2BasicAuth\Apache2BasicAuth\Service
```







---

### write

Write files to disc

```php
Service::write(  ): \Apache2BasicAuth\Apache2BasicAuth\Service
```







---

### getGroups

Get groups

```php
Service::getGroups(  ): array
```







---

### setGroups

Set groups

```php
Service::setGroups( array $groups ): \Apache2BasicAuth\Apache2BasicAuth\Service
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$groups` | **array** | Array of groups |




---

### persistGroup

Persist group

```php
Service::persistGroup( \Apache2BasicAuth\Apache2BasicAuth\Model\Group $group ): \Apache2BasicAuth\Apache2BasicAuth\Service
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$group` | **\Apache2BasicAuth\Apache2BasicAuth\Model\Group** | Group |




---

### removeGroup

Remove group

```php
Service::removeGroup( \Apache2BasicAuth\Apache2BasicAuth\Model\Group $group ): \Apache2BasicAuth\Apache2BasicAuth\Service
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$group` | **\Apache2BasicAuth\Apache2BasicAuth\Model\Group** | Group |




---

### findGroup

Find group by name

```php
Service::findGroup( string $groupname ): \Apache2BasicAuth\Apache2BasicAuth\Model\Group|null
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$groupname` | **string** | Group name |




---

### getGroupNames

Get group names

```php
Service::getGroupNames(  ): array
```







---

### getUsernames

Get usernames

```php
Service::getUsernames(  ): array
```







---

### createGroup

Create a group instance

```php
Service::createGroup( string $groupname = null, array $users = array() ): \Apache2BasicAuth\Apache2BasicAuth\Model\Group
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$groupname` | **string** | Group name |
| `$users` | **array** | Users |




---

### getUsers

Get users

```php
Service::getUsers(  ): array
```







---

### setUsers

Set users

```php
Service::setUsers( array $users ): \Apache2BasicAuth\Apache2BasicAuth\Service
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$users` | **array** | Array of users |




---

### persistUser

Persist user

```php
Service::persistUser( \Apache2BasicAuth\Apache2BasicAuth\Model\User $user ): \Apache2BasicAuth\Apache2BasicAuth\Service
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$user` | **\Apache2BasicAuth\Apache2BasicAuth\Model\User** | User |




---

### removeUser

Remove user

```php
Service::removeUser( \Apache2BasicAuth\Apache2BasicAuth\Model\User $user ): \Apache2BasicAuth\Apache2BasicAuth\Service
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$user` | **\Apache2BasicAuth\Apache2BasicAuth\Model\User** | User |




---

### createUser

Create a user instance and persists to collection

```php
Service::createUser( string $username = null, array $groups = array(), string $password = null ): \Apache2BasicAuth\Apache2BasicAuth\Service
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$username` | **string** | Username |
| `$groups` | **array** | Groups |
| `$password` | **string** | User password |




---

### findUser

Find user by name

```php
Service::findUser( string $username ): \Apache2BasicAuth\Apache2BasicAuth\Model\User|null
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$username` | **string** | User |




---

### persist

Persist user or group

```php
Service::persist( object $object ): \Apache2BasicAuth\Apache2BasicAuth\Service
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$object` | **object** | User or Group |




---

## User

User Model



* Full name: \Apache2BasicAuth\Model\User


### __construct

Constructor

```php
User::__construct( string $username = null, array $groups = array(), string $password = null )
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$username` | **string** | Username |
| `$groups` | **array** | Groups |
| `$password` | **string** | Password |




---

### setUsername

Set username

```php
User::setUsername( string $username ): \Apache2BasicAuth\Model\App\Model\User
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$username` | **string** | Username |




---

### getUsername

Get username

```php
User::getUsername(  ): string
```







---

### setPassword

Set Password

```php
User::setPassword( string $password ): \Apache2BasicAuth\Model\App\Model\User
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$password` | **string** | Password |




---

### getPassword

Get Password

```php
User::getPassword(  ): string
```







---

### setGroups

Set groups

```php
User::setGroups( array $groups ): \Apache2BasicAuth\Model\App\Model\User
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$groups` | **array** | Groups |




---

### getGroups

Get Groups

```php
User::getGroups(  ): array
```







---

### addGroup

Add a group

```php
User::addGroup( string $group ): \Apache2BasicAuth\Model\App\Model\User
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$group` | **string** | Group name |




---

### removeGroup

Remove a group

```php
User::removeGroup( string $group ): \Apache2BasicAuth\Model\App\Model\User
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$group` | **string** | Group name |




---

### hasGroup

Check if user has a group

```php
User::hasGroup( string $group ): boolean
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$group` | **string** | Group name |




---

### getHash

Get Hash

```php
User::getHash(  ): string
```







---

### setHash

Set Hash

```php
User::setHash( string $hash ): \Apache2BasicAuth\Model\App\Model\User
```




**Parameters:**

| Parameter | Type | Description |
|-----------|------|-------------|
| `$hash` | **string** | Hash |




---

### formatHT

Format to HT write

```php
User::formatHT(  ): string
```







---



--------
> This document was automatically generated from source code comments on 2016-09-01 using [phpDocumentor](http://www.phpdoc.org/) and [cvuorinen/phpdoc-markdown-public](https://github.com/cvuorinen/phpdoc-markdown-public)
