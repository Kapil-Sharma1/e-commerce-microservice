FROM python:3.11-slim

# python envs
ENV PYTHONFAULTHANDLER=1 \
    PYTHONUNBUFFERED=1 \  
    PYTHONHASHSEED=random \
    PIP_NO_CACHE_DIR=off \
    PIP_DISABLE_PIP_VERSION_CHECK=on \
    PIP_DEFAULT_TIMEOUT=100


# python dependencies
COPY ./backend/requirements.txt /
RUN pip3 install -r ./requirements.txt
RUN apt-get update && apt-get -y upgrade


# upload scripts
COPY ./backend/scripts/entrypoint.sh ./backend/scripts/start.sh ./backend/scripts/gunicorn.sh /

WORKDIR /app/backend/