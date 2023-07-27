# Setting up Phalcon PHP Framework
With Phalcon, all you have to do is install a PHP extension, which takes up very little space. However, you will need root access to do it. Luckily, it is already installed on our shared hosting plans, so the initial setup will not be hard. We will also cover how to set up Phalcon on a Linux VPS running on Ubuntu 16.04. To make it a little easier, we’ll use Phalcon developer tools for both cases. 


## Setting up Phalcon on Hostinger shared hosting
### Firstly, we’ll start by installing the Phalcon devtools.

Important! For this task, we will be using Composer. Click here for more information on how to install it.

To begin, you will need to connect to your hosting account via SSH.

Use the pwd command to check your current location. We recommend setting it up one directory above public_html. This will keep things more organized. If the command shows the following results, you are in the right place:

-bash-4.1$ pwd 
/home/YOUR_USERNAME
Now, let’s create a composer.json file with the following content in it:

{
    "require-dev": {
        "phalcon/devtools": "~4.0"
    }
}
You can do this using File Manager or by writing the following command in SSH:

nano composer.json
This will create your file and open a text editor. Paste the required contents and press CTRL+X to save everything. To install the Phalcon developer tools, execute the following command:

composer install
Wait for the process to finish, as it can take a few minutes. Next, let’s create an alias so that the dev tools would be fully functional. If you followed the exact steps in this tutorial, you’ll be able to create it using the following syntax:

alias phalcon=/home/YOUR_USERNAME/vendor/phalcon/devtools/phalcon
Important! Don’t forget to replace YOUR_USERNAME with your actual username.

Now, we have functional Phalcon developer tools. To check if they are really working, write the following command:

phalcon
And you should receive a similar output to this:

Phalcon DevTools (4.x.x)

Available commands:
info (alias of: i)
commands (alias of: list, enumerate)
controller (alias of: create-controller)
module (alias of: create-module)
model (alias of: create-model)
all-models (alias of: create-all-models)
project (alias of: create-project)
scaffold (alias of: create-scaffold)
migration (alias of: create-migration)
webtools (alias of: create-webtools)
serve (alias of: server)
console (alias of: shell, psysh)
Since our shared hosting servers already have all the ingredients for Phalcon framework to run, you will not need to install any extra extensions. Phalcon framework is loosely coupled, meaning you can have any directory structure that you find convenient.

For simplicity purposes, we’ll be using the structure that Phalcon developer tools provide us with. Let’s navigate to the public_html directory by using the following command:

cd public_html
Once you are there, use the Phalcon developer tool syntax to set everything up:

phalcon create-project example
Now, if you navigate to YourDomain.com/example in the browser, you will see a similar screen:

Phalcon Framework successfully launched on Hostinger shared hosting
Option 2 – Setting up Phalcon on a VPS
Now, let’s learn to set up Phalcon PHP framework on a virtual private server. This will take a little extra time, as we’ll need to install more components.

We will guide you through it, so it won’t be too tough. For this part, we will be using a VPS running on Ubuntu 16.04.

First of all, we will need these components:

Apache

MySQL

PHP 5.5 and up

Composer


Apache, MySQL, and PHP are included by default in most VPS templates. Therefore you’ll only need to install Composer to continue. Once you’re done with that, you’ll need to set up the required Phalcon PHP extension. Execute the following command to do it:

curl -s https://packagecloud.io/install/repositories/phalcon/stable/script.deb.sh | sudo bash


Now that we have all the components, let’s set up Phalcon framework. We will start by getting Phalcon developer tools, which will simplify the framework usage process. Begin by navigating one directory above the domain’s root. In our example, it would be:

cd /var/www

Use this command to create a composer.json file:

nano composer.json

It will create the file and open it in a text editor interface. Paste the following content there:

{
    "require-dev": {
        "phalcon/devtools": "~3.2"
    }
}
Press CTRL+X to save it. Proceed with the developer tool installation by entering this command:

composer install
Once it finishes, create an alias to ensure the Phalcon developer tools are functional. In our example, the syntax should look like this:

alias phalcon=/var/www/vendor/phalcon/devtools/phalcon
Let’s see if they work by executing this command:

phalcon
The output should be:

Phalcon DevTools (4.x.x)

Available commands:
info (alias of: i)
commands (alias of: list, enumerate)
controller (alias of: create-controller)
module (alias of: create-module)
model (alias of: create-model)
all-models (alias of: create-all-models)
project (alias of: create-project)
scaffold (alias of: create-scaffold)
migration (alias of: create-migration)
webtools (alias of: create-webtools)
serve (alias of: server)
console (alias of: shell, psysh)
We are now ready to create a project. This framework is loosely coupled, which lets you have any directory structure. In this example, we will go with the default directory structure provided by the developer tools. Start by navigating to the root directory of your domain. In our example, it is:

cd /var/www/hostinger-tutorials.com/public_html
Next, use this command to create the directory structure and get started:

phalcon create-project example
You may now open your domain in the browser (e.g, YourDomain.com/example) and you should see a similar view:

Phalcon Framework successfully launched on Hostinger VPS
Creating Your First Project With Phalcon PHP Framework
Now, let’s try to create a basic application. Imagine you are creating a project and wish to gather a list of potential users or clients before the launc
