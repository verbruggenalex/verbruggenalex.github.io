FROM gitpod/workspace-mysql

USER root

ENV COMPOSER_HOME=/home/gitpod/.config/composer

RUN composer global require enlightn/security-checker ergebnis/composer-normalize php-parallel-lint/php-parallel-lint phpro/grumphp --ansi --no-interaction \
 && chown -R gitpod:gitpod /home/gitpod/.config/composer

USER gitpod

ENV PATH=./vendor/bin:${HOME}/.config/composer/vendor/bin:${PATH} APACHE_DOCROOT_IN_REPO=web
