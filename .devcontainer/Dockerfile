FROM mcr.microsoft.com/devcontainers/php:0-8.1

# Install MariaDB client
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y mariadb-client \ 
    && apt-get install -y libicu-dev \ 
    && apt-get install -y icu-devtools \ 
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Install php-mysql driver
RUN docker-php-ext-install mysqli pdo pdo_mysql

# RUN apt-get update
# RUN apt-get install -y libicu-dev
# RUN apt-get install -y icu-devtools 
RUN docker-php-ext-configure intl \ 
&& docker-php-ext-install intl \ 
&& docker-php-ext-enable intl

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1