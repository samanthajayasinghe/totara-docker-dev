FROM ubuntu:16.04

RUN  echo "deb http://archive.ubuntu.com/ubuntu xenial main universe\n" > /etc/apt/sources.list \
  && echo "deb http://archive.ubuntu.com/ubuntu xenial-updates main universe\n" >> /etc/apt/sources.list \
  && echo "deb http://security.ubuntu.com/ubuntu xenial-security main universe\n" >> /etc/apt/sources.list

# No interactive frontend during docker build
ENV DEBIAN_FRONTEND=noninteractive \
DEBCONF_NONINTERACTIVE_SEEN=true

#COPY chrome64_62.0.3202.75.deb /chrome64_62.0.3202.75.deb

#RUN apt-get -qy update \
#  && apt-get -qy --no-install-recommends install \
#    gconf-service \
#    libasound2 \
#    libatk1.0-0 \
#    libcairo2 \
#    libcups2 \
#    libdbus-1-3 \
#    libexpat1 \
#    libfontconfig1 \
#    libgconf-2-4 \
#    libgdk-pixbuf2.0-0 \
#    libgtk-3-0 \
#    libnspr4 \
#    libpango-1.0-0 \
#    libpangocairo-1.0-0 \
#    libx11-xcb1 \
#    libxcomposite1 \
#    libxcursor1 \
#    libxss1 \
#    libxtst6 \
#    ca-certificates \
#    fonts-liberation \
#    libappindicator1 \
#    libnss3 \
#    lsb-release \
#    xdg-utils \
#    wget \
#  && rm -rf /var/lib/apt/lists/* /var/cache/apt/*
#
#RUN dpkg -i /chrome64_62.0.3202.75.deb

RUN apt-get -qy update \
  && apt-get -qy --no-install-recommends install \
    ca-certificates \
    wget \
  && rm -rf /var/lib/apt/lists/* /var/cache/apt/*

ARG CHROME_VERSION="google-chrome-stable"
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
  && echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list \
  && apt-get update -qy \
  && apt-get -qy install \
    google-chrome-stable=62.0.3202.94-1 \
#    ${CHROME_VERSION:-google-chrome-stable} \
  && rm /etc/apt/sources.list.d/google-chrome.list \
&& rm -rf /var/lib/apt/lists/* /var/cache/apt/*

EXPOSE 9222

CMD google-chrome-stable --no-sandbox --disable-gpu --headless --remote-debugging-address=0.0.0.0 --remote-debugging-port=9222