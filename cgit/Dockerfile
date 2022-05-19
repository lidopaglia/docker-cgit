FROM alpine
MAINTAINER Lido Paglia
RUN apk update
RUN apk add \
    cgit \
    git \
    highlight \
    uwsgi \
    uwsgi-cgi

RUN adduser -S -u 900 -h /home/cgit -s /bin/false cgit

COPY cgitrc /etc/cgitrc
COPY cgit-syntax-highlighting.sh \
     /usr/lib/cgit/filters/cgit-syntax-highlighting.sh
COPY cgit.ini /etc/uwsgi/apps-available/cgit.ini

USER cgit

CMD /usr/sbin/uwsgi --ini /etc/uwsgi/apps-available/cgit.ini
