# How to install Laravel + React project
  
NOTE: I will be using Ubuntu 22.04. 

NOTE: Check node.js and npm latest versions are installed.

NOTE: A text editor is needed, I used Visual Studio Code.

NOTE: I followed this video: https://youtu.be/bHRe5XNP5l8?si=7j2cDSMTp6x-CcCz 

##### How to enable clipboard in ubuntu?

```
sudo VBoxClient --clipboard
```

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
  
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3307  # Change this if your MySQL port is different
DB_DATABASE=laravel_react_survey2
DB_USERNAME=root  # Change this if your MySQL username is different
DB_PASSWORD=      # Enter your MySQL password here
```

  ![image](https://github.com/user-attachments/assets/5739010a-5c01-45c0-96d6-73936387d983)

  5.Migrate the Data Bases
  
  5.1-Install the PHP MySQL Extension:
```
sudo apt-get install php-mysql
```

  5.2-Restart Apache to ensure the changes take effect:
```
sudo /opt/lampp/lampp restart
```

  5.3-Run migrations
```
php artisan migrate
```


### 1.5-Create a React project with Vite

  1.Run Vite:
```
npm create vite@latest
```

  2.Choose this distribution:
  
![image](https://github.com/user-attachments/assets/f60beabd-a303-4d47-be7a-696900fd8c71)

  3.Run this commands:
```
cd react
npm install
npm run dev
```

  4.Go to this file, an add this code to access using port 3000:

  ![image](https://github.com/user-attachments/assets/26e1d41e-ffcd-4858-b568-16e690b32e60)

```
--port=3000
```

  5.Run the Server again:
```
npm run dev
```



## Step 2: Add Tailwind css

### 2.1-Install Tailwind css (and its necessary programs/dependences)
  Open a new terminal and run the following commands:
```
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init
```

### 2.2-Configure your template paths
  Go to the tailwind.config.js file, delete everything and then copy this:
```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### 2.3-Configure spaces (OPTIONAL)
  Go to the .editor file and add this lines:
```
[*.{js, jsx, cjs}]
indent_size = 2
```

### 2.4-Add the Tailwind directives to your CSS
  Go to index.css and add this directives at the top:

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### 2.5-Install Tailwind CSS widget in Visual Studio Code

## Step 3: Add HeroIcons (OPTIONAL but recommended)
  ### 3.1-Install HeroIcons
```
npm install @heroicons/react
```

  ### 3.2-Import whatever is needed to get the icon desired:

In this url we can get the names of the icons https://unpkg.com/browse/@heroicons/vue/24/outline/

Here we can get how they look like visually https://heroicons.com
