# Cospic Webservice

This is the Webservice for the [Cospic Project](https://github.com/cfspluscosmos). This piece of software receives data from Cosmos, organize it and inset into the Firebase Database. This Webservice is ready to be integrated "as a Service".

The Websiervice was built on [Lumen Framework](http://lumen.laravel.com/docs/installation) and [Firebase-php Library](https://github.com/ktamas77/firebase-php).

Note: [Webservice](https://en.wikipedia.org/wiki/Web_service) !== [Webserver](https://en.wikipedia.org/wiki/Web_server)

## Getting Started

Note 2: if you intend to run this application in a remote webserver, read "Running on a Web Server" down here first!

First of all, you need to setup the [Cospic Android Application](https://github.com/cfspluscosmos/app-android).

Clone the project

After cloning, change to its directory

`cd cospic-webservice`

Install the dependencies using [Composer](https://getcomposer.org/)

`composer install`

And wait for all the files to be installed.


## Setting up the Firebase

First of all, create an account on [Firebase](https://firebase.google.com) and create a new project. If you have done so, enter in you project and go to "Add Firebase to your web app". It will open an window with some credentials we are going to use next.

Then, you need to setup your Firebase credentials on the webservice. Go to the `.env.example` file, inside the project root, and set your `FIREBASE_AUTH_DOMAIN` and `FIREBASE_DB_URL`. Save this file as `.env` (remove the ".example"). These two informations can be found on the window that just opened on Firebase website. All the information on how to get the credentials can be found on the [Firebase documentation](https://www.firebase.com/docs/rest/). Next, you need to setup the `FIREBASE_SECRET` inside the `.env` you just saved. Go to Firebase again and on the left menu click on the gear and click on "Project Settings". Then, on the horizontal menu, go to "Database" and a "Database secrets" will show up. Hover on the black dots and a "show" button will appear. Click on that to reveal the secret. Copy it to the `FIREBASE_SECRET` on the `.env` file and you are done with this step.

## Running the Webservice

You can run the webservice basically by two ways: on your local network or on a remote webserver like AWS or Digital Ocean.

### Running on a Local network
To run locally, you should [setup an Apache webserver](https://www.digitalocean.com/community/tutorials/how-to-configure-the-apache-web-server-on-an-ubuntu-or-debian-vps) OR use the PHP's built-in webserver running `sudo php -S localhost:80` inside the `public` folder.

### Running on a Web Server
To run in a remote webserver, follow [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu) on how to setup a webserver to run the webservice. You can skip the MySQL installation, since we are using Firebase. After setting up the webserver, change to the WWW folder, go to the step "Getting Started" and install the application.

### Finishing Up

As soon as you launch the webservice, you need to take note of the address in which you are running it. For example, if you chose to use the built-in webserver using the boilerplate command `sudo php -S localhost:80`, then the address in which the webservice is running is `http://localhost:80`. You should inform this address, adding the path `/posts`, on on the second line of the file `script_runner_files/log_app/config.txt`, which is inside the [cFS-Cosmos](https://github.com/cfspluscosmos/cfs-cosmos) folder. So the full address to be informed would be `http://localhost:80/posts`. If you are using a remote webserver, you should inform the IP address, followed by the path `/posts` such as `http://192.168.0.1/posts`

### Configuring Ngrok for local environments with multiple computers
Ngrok creates a TLS connection, so you can access your local server in remote places. Create an account at [Ngrok](https://ngrok.com/), download their file, unzip and place it on the `public` folder. Start the service:

`./ngrok http 80`

Take note of the address informed by Ngrok and go to the step "Finishing Up"

## License

The Copsic Webservice is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
