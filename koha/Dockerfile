FROM debian
MAINTAINER Renan Rocha "renan.rocha@grad.ufsc.br"

RUN apt-get update && apt-get install -y \
  wget \
  gnupg \
  mariadb-client \
  perlbrew

RUN wget -q -O- https://debian.koha-community.org/koha/gpg.asc | apt-key add -

RUN echo 'deb http://debian.koha-community.org/koha stable main' | tee /etc/apt/sources.list.d/koha.list

RUN apt-get update && apt-get install -y \
  koha-common

RUN perlbrew install-cpanm

RUN /root/perl5/perlbrew/bin/cpanm install JSON::Validator

RUN /root/perl5/perlbrew/bin/cpanm install Mojolicious::Plugin::OpenAPI

RUN a2enmod rewrite cgi mpm_itk

# Koha specific stuff

COPY koha-sites.conf /etc/koha/koha-sites.conf

COPY koha-common.cnf /etc/mysql/koha-common.cnf

RUN koha-translate --install pt-BR

COPY entrypoint.sh /

RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
