FROM gitpod/workspace-mysql

USER gitpod

RUN composer global require enlightn/security-checker ergebnis/composer-normalize php-parallel-lint/php-parallel-lint phpro/grumphp --no-interaction

ENV PATH=${GITPOD_REPO_ROOT}/vendor/bin:${HOME}/.composer/vendor/bin:${PATH} APACHE_DOCROOT_IN_REPO=web
