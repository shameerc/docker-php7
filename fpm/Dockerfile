FROM ubuntu:latest

RUN apt-get update && apt-get install -y software-properties-common language-pack-en-base \
    && LC_ALL=en_US.UTF-8 add-apt-repository -y ppa:ondrej/php \
    && apt-get update \
    && apt-get install -y php7.2 php7.2-fpm php7.2-mysql mcrypt php7.2-gd curl \
       php7.2-curl php-redis php7.2-mbstring sendmail supervisor \
    && mkdir /run/php \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

RUN sed -i -e 's/listen = \/run\/php\/php7.2-fpm.sock/listen = 0.0.0.0:9000/g' /etc/php/7.2/fpm/pool.d/www.conf \
    && sed -i -e 's/;daemonize = yes/daemonize = no/g' /etc/php/7.2/fpm/php-fpm.conf

WORKDIR /var/app

EXPOSE 9000

CMD ["/usr/bin/supervisord"]