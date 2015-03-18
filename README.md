Datetime picker widget
======================
Bootstrap datetimepicker widget for Yii 2, based on [Eonasdan/bootstrap-datetimepicker](https://github.com/Eonasdan/bootstrap-datetimepicker).

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist nkovacs/yii2-datetimepicker "*"
```

or add

```
"nkovacs/yii2-datetimepicker": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

```php
<?= \nkovacs\datetimepicker\DateTimePicker::widget([
    'name' => 'time',
]); ?>
```

or as an active field:

```php
<?= $form->field($model, 'time')->widget(\nkovacs\datetimepicker\DateTimePicker::className(), [
    'clientOptions' => [
        'extraFormats' => ['YYYY-MM-DD HH:mm'],
    ],
]) ?>
```

To show just a datepicker:

```php
<?= $form->field($model, 'time')->widget(\nkovacs\datetimepicker\DateTimePicker::className(), [
    'type' => 'date',
]) ?>
```

or just a timepicker:

```php
<?= $form->field($model, 'time')->widget(\nkovacs\datetimepicker\DateTimePicker::className(), [
    'type' => 'time',
]) ?>
```

The widget will load the moment locale file for `Yii::$app->language` if it can find it.
It will also use `Yii::$app->formatter->dateFormat`, `Yii::$app->formatter->timeFormat` or `Yii::$app->formatter->datetimeFormat` depending on `type`.
Both can be overriden manually using the `language` and `format` options.
