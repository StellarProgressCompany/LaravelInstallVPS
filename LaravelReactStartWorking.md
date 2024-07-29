# How to set up the environment to start working (Ubuntu 22.04)

It's simply needed to follow this steps.

## 1st Step: Enable Clipboard

```
sudo VBoxClient --clipboard
```

## 2nd Step: Open 1st terminal, navigate through your Project's dircetory and run Laravel Server:

```
cd Desktop/LaravelProject/laravel-react-example
php artisan serve
```

## 3rd Step: Open 2nd terminal, navigate through React directory and run React Server:

```
cd react
npm run dev
```

## 4th Step: Open 3rd terminal and run both Apache and MySQL Servers:

```
sudo /opt/lampp/manager-linux-x64.run
```

## 5th Step: Open 4th terminal and start working!

```
code ..
```
