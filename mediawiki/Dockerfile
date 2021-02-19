FROM mediawiki:1.35.1-fpm-alpine

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN cd extensions && \
  git clone https://github.com/petitalb/MW-OAuth2Client.git && \
  cd MW-OAuth2Client && \
  git submodule update --init && \
  cd vendors/oauth2-client && \
  composer install

RUN cd extensions && \
  git clone -b REL1_35 https://gerrit.wikimedia.org/r/mediawiki/extensions/Collection
