FROM gitpod/workspace-mysql

USER root

ENV COMPOSER_HOME=/home/gitpod/.config/composer

COPY --chown=gitpod:gitpod composer.json /home/gitpod/.config/composer/composer.json

RUN composer global require enlightn/security-checker ergebnis/composer-normalize php-parallel-lint/php-parallel-lint phpro/grumphp --no-interaction --ansi \
 && chown -R gitpod:gitpod /home/gitpod/.config/composer

USER gitpod

ENV PATH=./vendor/bin:${HOME}/.config/composer/vendor/bin:${PATH} APACHE_DOCROOT_IN_REPO=web
