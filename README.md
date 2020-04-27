Html2pdfBundle
=====================

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/0e16b696-0da3-4efc-b856-60429a9672b4/mini.png)](https://insight.sensiolabs.com/projects/0e16b696-0da3-4efc-b856-60429a9672b4)
[![Build Status](https://travis-ci.org/OwlyCode/EnseparHtml2pdfBundle.svg?branch=master)](https://travis-ci.org/OwlyCode/EnseparHtml2pdfBundle)

Html2pdf for Symfony 4 or 5 as a service.

How to install ?
----------------

Just add this to your composer.json file:

```js
"require": {
  ...
  "phihuynh/html2pdfbundle": "dev-master",
}
```
How to use ?
------------

In your action:

```php
use Ensepar\Html2pdfBundle\Factory\Html2pdfFactory;

public function yourAction(Request $request, Html2pdfFactory $html2pdfFactory){
  ...
  $html2pdf = $html2pdfFactory->create();
}
```

You can pass every option you would pass to html2pdf, for instance :

```
$html2pdf = $html2pdfFactory->create('P', 'A4', 'en', true, 'UTF-8', array(10, 15, 10, 15));
```

If the previous arguments are not provided, the factory uses its own default values. You can
change this default values by adding the bundle configuration to your `app/config/config.yml` :

```yml
ensepar_html2pdf:
    orientation: P
    format: A4
    lang: en
    unicode: true
    encoding: UTF-8
    margin: [10,15,10,15]
```

How to run the tests ?
----------------------

```
composer install
phpunit
```
