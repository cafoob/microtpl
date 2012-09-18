# MicroTpl

MicroTpl is small templating system for PHP.

## Usage

    <?php
    require_once 'microtpl.php';

    $tpl = new MicroTpl();
    $tpl->title = 'MicroTpl';
    $tpl->messages = array(
      array('message' => 'Hello, Earth'),
      array('message' => 'We confiscates this planet.')
    );

    ob_start();

    ?><!DOCTYPE html>
    <html>
      <head>
        <title>{title}</title>
      </head>
      <body>
        <h1>{title}</h1>
        {@messages}
        <p>{message}</p>
        {/messages}
      </body>
    </html><?php

    $tpl->render(ob_get_clean());

## Syntax

    {var}    echo escaped variable
    {&var}   echo unescaped variable
    {@list}  list array
    {?bool}  show block on true
    {!bool}  show block on false
    {/list}  end of array or block
    {-php}   alias for <?php php ?>
