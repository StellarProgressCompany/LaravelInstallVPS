# How to install Laravel + React project
  
NOTE: I will be using Ubuntu 22.04. 

##### How to enable clipboard in ubuntu?

```
sudo VBoxClient --clipboard
```

NOTE: A text editor is needed, I used Visual Studio Code.


## Step 1: Set Up

### 1.1-Install XAMPP (Apache+MariaDB+PHP+Perl)
  You need to go to this web: www.apachefriends.org
  
  Then download the Linux installer.
  
  After being installed run this commands:
  
  ![image](https://github.com/user-attachments/assets/15005d6d-d044-48a4-842a-3e92ae91faaa)
  
  When the installation finishes, go to Manage Servers in the installation file and start running both Apache Web Server and MySQL Database. If they can't run (they are already used), go to configuration and    change the port (add 1).
  
  ![image](https://github.com/user-attachments/assets/9917ef7b-8cba-4edb-9c58-d837e3b3dbab)

  🆗🆗INSTALLATION COMPLETED🆗🆗

  Visit this, with the apache port (myadmin).
```
http://localhost:81
```


### 1.2-Install Composer
  https://shaonmajumder.medium.com/how-to-install-composer-on-ubuntu-22-04-a12b07fddecd

  Use this web guide, it's really good.

  🆗🆗INSTALLATION COMPLETED🆗🆗

### 1.3-Install Node.js (for npm)

```
# installs fnm (Fast Node Manager)
curl -fsSL https://fnm.vercel.app/install | bash

# download and install Node.js
fnm use --install-if-missing 22

# verifies the right Node.js version is in the environment
node -v # should print `v22.5.1`

# verifies the right NPM version is in the environment
npm -v # should print `10.8.2`
```

  🆗🆗INSTALLATION COMPLETED🆗🆗

### 1.4-Create a Laravel Project
  1.Navigate to the directory you want to create your project and create a directory which will contain it (I will name it LaravelProject).
```
cd Desktop/
mkdir LaravelProject
cd LaravelProject/
```

  2.Install Laravel installer
```
composer global require laravel/installer
```

  3.Create Laravel project (I named it laravel-react-example)
```
composer create-project laravel/laravel laravel-react-example
```

  4.Run Laravel's local development server
```
cd laravel-react-example
php artisan serve
```

### 1.5-DataBase
  1.Run XAMPP
```
sudo /opt/lampp/manager-linux-x64.run
```
  Then start running both MySQL Database and Apache Web Server 

  2.Visit the MySqlDatabase
```
http://localhost:81/dashboard/
```

  3.Add your first table
  Click on new, change the "type" to "uft8mb4_unicode_ci" and put the name desired to the table, in my case (laravel_react_survey2)

![image](https://github.com/user-attachments/assets/c095dc0c-fcf0-45ba-abfb-14d35e974c88)

  4.Update .env file
  Now, we must go to the .env file and change the parameters to match the ones in the image, please note that I put 3307 because it's the port of the Server I used in XAMMP

  ![image](https://github.com/user-attachments/assets/aeec5f57-f820-496c-a0a3-8bf3c29c97e9)

  5.Run migrations
```
php artisan migrate
```

  
