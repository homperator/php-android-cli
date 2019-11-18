# INSTALL JDK AND SDK TOOLS FOLLOW:
https://stackoverflow.com/a/53508177/4974580

# INSTALL PHP GREATER THAN 5 (FOR EXAMPLE):
```bash
sudo apt install php7.2
```

# INSTALL COMPOSER:
```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'a5c698ffe4b8e849a443b120cd5ba38043260d5c4023dbf93e1558871f1f07f58274fc6f4c93bcfd858c6bd0775cd8d1') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

sudo php composer-setup.php --install-dir=bin --filename=composer

php -r "unlink('composer-setup.php');"
```

# BUILD:

```
git clone https://github.com/homperator/php-android-cli.git
cd php-android-cli
composer install
```

Change in file /etc/php/7.2/cli/php.ini:
```
;phar.readonly = On
```
to
```
phar.readonly = Off
```

# INSTALL:
```
php tasks/generate_phar.php
chmod +x phpandroid.phar
sudo mv phpandroid.phar /usr/local/bin/phpandroid
```

# EXAMPLE PROJECT

## install sdk that in  or tools and accept license:

**answer y for every question**
```
$ANDROID_HOME/tools/bin/sdkmanager --licenses
```

# CREATE EXAMPLE PROJECT

```
php index.php create test com.hom.test
chmod +x gradlew
```

## Don't know why, but install SDK and tools manualy (I use default versions that listed [here](https://github.com/homperator/php-android-cli#default)):

```
yes | sudo $ANDROID_HOME/tools/bin/sdkmanager "platforms;android-29"
yes | sudo $ANDROID_HOME/tools/bin/sdkmanager "build-tools;29.0.1"
```

# BUILD AND INSTALL APP

```
./gradlew build
./gradlew installDebug
```

# VSCODE DEBUG EXTENSION
https://marketplace.visualstudio.com/items?itemName=adelphes.android-dev-ext