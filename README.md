# Cospic Webservice

This is the Webservice for the [Cospic Project](https://github.com/cfspluscosmos). This piece of software receives data from Cosmos, organize it and inset into the Firebase Database. This Webservice is ready to be integrated "as a Service".

The Websiervice was built on [Lumen Framework](http://lumen.laravel.com/docs/installation) and [Firebase-php Library](https://github.com/ktamas77/firebase-php).

## Getting Started
Clone the project

`git clone`

Install it using [Composer](https://getcomposer.org/)

`composer install`

And wait for the project to be installed.


## Setting up the Firebase

First of all, you need to create an account on Firebase and setup a new "Web" application.

You need to setup your Firebase credentials. Go to the `.env.example` file, inside the project root, and set your `FIREBASE_SECRET`, `FIREBASE_AUTH_DOMAIN` and `FIREBASE_DB_URL`. Save this file as `.env` (remove the ".example").
All these information can be found on the [Firebase documentation](https://www.firebase.com/docs/rest/).


### License

The Lumen framework is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
