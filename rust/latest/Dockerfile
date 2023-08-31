FROM        --platform=$TARGETOS/$TARGETARCH rust:slim

LABEL       author="Ethan Coward" maintainer="ethan.coward@icloud.com"

RUN         apt update \
                && apt -y install git dnsutils curl iproute2 ffmpeg libssl-dev \
                && useradd -m -d /home/container container

USER        container
ENV         USER=container HOME=/home/container CARGO_HOME=/home/container/.cargo
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         ["/bin/bash", "/entrypoint.sh"]
