# Greenhouse Job Board API integration

Easy access to a simple JSON representation of your company's offices, departments, and published jobs. You can build careers pages with a unique look and feel, construct department-level pages, and more!

## Installation

To install the library, simply:

```shell
$ git clone git@github.com:minnur/GreenhouseJobBoardAPI.git
$ cd GreenhouseJobBoardAPI
$ composer install
```

## Requirements

1. The PHP library works with PHP 5.4, 5.5, 5.6, and HHVM.
2. [PHP Curl Class](https://github.com/php-curl-class/php-curl-class) (version 4.6.9 recommended).

## Quick Start and Examples

```php
require '../vendor/autoload.php';
require '../src/GreenhouseJobBoardAPI.php';

use \GreenhouseJobBoardAPI\GreenhouseJobBoardAPI;

$api_url = "https://api.greenhouse.io/v1/boards/{{CLIENT_CODE}}/embed/";
$greenhouse = new GreenhouseJobBoardAPI($api_url);
```

##### Methods

```php
// The method returns a list of all of your organization's
// departments and jobs, grouped by office.
$offices = $greenhouse->getOffices();

// The method returns a list of your organization's departments
// and jobs for the given [OFFICE_ID].
$office = $greenhouse->getOffice([OFFICE_ID]);

// The method returns a list of your organization's
// departments and jobs. 
$departments = $greenhouse->getDepartments();

//  The method returns a list of jobs for a given [DEPARTMENT_ID].
$department = $greenhouse->getDepartment([DEPARTMENT_ID]);

// The method returns the list of all jobs, with or
// without description. 
$jobs = $greenhouse->getJobs(true);

// The method returns a single job corresponding to the given [JOB_ID].
// Setting second parameter to `true` will include the list
// of job application fields [optional]
$job = $greenhouse->getJob([JOB_ID], true);

// The board method returns your organization's name
// and job board content.
$board = $greenhouse->getBoard();
```

See also `examples/example.php` for working examples.
