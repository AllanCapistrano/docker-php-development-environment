# Cocker PHP Development Environment

You can use any PHP version you want; to do this, simply change the base image in the `.docker/Dockerfile`. [Click here](https://hub.docker.com/_/php/tags) to check all the official images.

## Add PHP to environment

1. Create a file to represent PHP on your machine:
    ```powershell
    sudo touch /usr/local/bin/php
    ```
2. Grant execution permissions to the created file:
    ```powershell
    sudo chmod +x /usr/local/bin/php
    ```
3. Edit the file with the following code:
    ```powershell
    sudo nano /usr/local/bin/php
    ```

    ```powershell
    command="docker exec php php "$@"
    echo "Running on Docker PHP"
    $command
    ```
4. You can check if it worked with the following command:
    ```powershell
    php -v
    ```

## Add Composer to environment

1. Create a file to represent Composer on your machine:
    ```powershell
    sudo touch /usr/local/bin/composer
    ```
2. Grant execution permissions to the created file:
    ```powershell
    sudo chmod +x /usr/local/bin/composer
    ```
3. Edit the file with the following code:
    ```powershell
    sudo nano /usr/local/bin/composer
    ```

    ```powershell
    command="docker exec php composer "$@""
    echo "Running on Docker PHP"
    $command
    ```
4. You can check if it worked with the following command
    ```powershell
    composer -V
    ```

## Setting up the intellisense

1. Open your VS Code settings file;
2. Add te following settings:
    ```JSON
    "php.validate.executablePath": "/usr/local/bin/php",
    "intelephense.environment.phpVersion": "<PHP Version>"
    ```