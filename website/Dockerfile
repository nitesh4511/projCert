# Use official PHP with Apache
FROM php:8.2-apache

# Enable useful Apache modules (optional but common)
RUN a2enmod rewrite

# Install any PHP extensions you need (example: PDO + MySQL)
# Remove pdo_mysql if you don't use a DB
RUN docker-php-ext-install pdo pdo_mysql

# Set working directory to Apache web root
WORKDIR /var/www/html

# Copy everything into the container (except what you .dockerignore)
COPY . /var/www/html/

# (Optional) If you rely on .htaccess and need overrides:
# RUN sed -i 's/AllowOverride None/AllowOverride All/g' /etc/apache2/apache2.conf

# Expose Apache port
EXPOSE 80

# Apache is the default CMD in this image
# CMD ["apache2-foreground"]