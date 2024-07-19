# How to install Laravel + React project
  
NOTE: I will be using Ubuntu 22.04. 

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
  
### 1.2-Create a Laravel Project
  1.Navigate to the directory you want to create your project and create a directory which will contain it (I will name it LaravelProject).
```
  cd Desktop/
  mkdir LaravelProject
  cd LaravelProject/
```

  2.Install Laravel installer
