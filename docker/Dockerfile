FROM php:8.3-fpm

# Installe les dépendances nécessaires
RUN apt-get update && apt-get install -y \
    libpq-dev \
    git \
    unzip \
    wget \
    && docker-php-ext-install pdo pdo_pgsql

# Configure Git
RUN git config --global user.email "nadal.david@outlook.com" \
    && git config --global user.name "David"

# Installe Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Installe Symfony CLI
RUN wget https://get.symfony.com/cli/installer -O - | bash \
    && mv /root/.symfony*/bin/symfony /usr/local/bin/symfony