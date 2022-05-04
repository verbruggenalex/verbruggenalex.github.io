FROM gitpod/workspace-mysql

USER root

ENV COMPOSER_HOME=/home/gitpod/.config/composer

COPY --chown=gitpod:gitpod assets/gitpod/composer.json /home/gitpod/.config/composer/composer.json
COPY --chown=gitpod:gitpod assets/gitpod/.wakatime.cfg /home/gitpod/.wakatime.cfg

RUN composer global require enlightn/security-checker ergebnis/composer-normalize php-parallel-lint/php-parallel-lint phpro/grumphp --ansi \
 && chown -R gitpod:gitpod /home/gitpod/.config/composer \
 && sed -i "s/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/$WAKATIME_API_KEY/g"  /home/gitpod/.wakatime.cfg

USER gitpod

ENV PATH=./vendor/bin:${HOME}/.config/composer/vendor/bin:${PATH} APACHE_DOCROOT_IN_REPO=web
