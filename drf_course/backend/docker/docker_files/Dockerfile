FROM python:3.10

ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1

RUN set -e; \
    apt-get update ;\
    apt-get -y install netcat-traditional ;\
    apt-get -y install gettext ;
RUN mkdir /backend
COPY . /backend/
WORKDIR /backend

RUN set -e; \
    /usr/local/bin/python -m pip install --upgrade pip ;\
    python -m pip install -r /backend/requirements.txt ;\
    chmod +x /backend/docker/entrypoints/entrypoint.sh ;

EXPOSE 8000
ENTRYPOINT ["/backend/docker/entrypoints/entrypoint.sh"]


