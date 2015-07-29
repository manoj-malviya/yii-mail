# yii-mail

Automatically exported from [code.google.com/p/yii-mail](https://code.google.com/p/yii-mail/)

## About yii-mail

A Mail extension for [Yii](https://github.com/yiisoft/yii) that wraps [Swift Mailer](http://swiftmailer.org/). Uses Yii 1.1.x.

HTML documentation is available in the /doc directory. You can also generate your own using phpDocumentor.

## Yii 1.1: mail

SwiftMailer wrapper

This is an emailing extension that wraps SwiftMailer. This extension
also allows you to *create emails from view files*. For more information
about SwiftMailer can do, see
[http://swiftmailer.org](http://swiftmailer.org/)

### Resources [¶](#hh0)

-   [Google Code](https://code.google.com/p/yii-mail/)
-   [Google Code checkout
    page](https://code.google.com/p/yii-mail/source/checkout)
-   [Download page](http://code.google.com/p/yii-mail/downloads/list)
-   [SwiftMailer home page](http://swiftmailer.org/)

### Requirements [¶](#hh1)

-   Yii 1.1.x

### Documentation [¶](#hh2)

Please see the phpdocs (it is in fact well-documented). First read
through the main phpdoc on the Mail.php file and then the Message.php
file (both in the root directory).

### Quick example to catch your interest [¶](#hh3)

This is an advanced example. It is not *required* that you use view
files to generate the emails.

    $message = new YiiMailMessage;
    $message->view = 'registrationFollowup';
     
    //userModel is passed to the view
    $message->setBody(array('userModel'=>$userModel), 'text/html');
     
     
    $message->addTo($userModel->email);
    $message->from = Yii::app()->params['adminEmail'];
    Yii::app()->mail->send($message);

Change Log [¶](#hh4)
--------------------

See Google Code hosting page

*Matt Kantor* has been so gracious as to provide an update, including:

-   Removed the "debug" option and associated behavior. In its place are
    the "logging" and "dryRun" options. Logging uses Yii::log() (you can
    set up a LogRoute to show flashes for the old behavior).
-   Changed class names to be less likely to cause conflicts (requested
    in several bug reports).
-   Made the extension usable from CConsoleApplication.
-   Plenty of formatting and documentation fixes.
