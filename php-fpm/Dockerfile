FROM php:8.2-fpm

# Copy the existing php template with in the container and create the php.ini file using it
RUN cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini

# apt-get update updates the packages list and upgrades command upgrades them to the latest ones 
RUN apt-get update

# This is a script provided by the official PHP Docker images to simplify the process of installing PHP extensions. It is a part of the PHP source distribution.
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install bcmath
RUN docker-php-ext-install sockets

# -------------------INSTALLATION OF COMPOSER - START ----------------------
RUN apt-get install -y --no-install-recommends \
    wget \
    unzip 

RUN wget -O /usr/local/bin/composer https://getcomposer.org/composer.phar
RUN chmod +x /usr/local/bin/composer
# -------------------INSTALLATION OF COMPOSER - END ------------------------

# This line removes unnecessary packages and cleans up temporary files to reduce the size of the Docker image.
RUN apt-get autoremove -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*