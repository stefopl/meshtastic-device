FROM python:3.11-slim-bookworm AS app
LABEL "website"="https://github.com/mate-dev/mmrelaynode"
RUN groupadd -g 1000 mesh && useradd -ml -u 1000 -g 1000 -s /bin/bash mesh
RUN pip install --upgrade pip -qq
USER mesh
WORKDIR /home/mesh/app
COPY meshtastic-matrix-relay /home/mesh/app
RUN pip install -qq -r /home/mesh/app/requirements.txt --no-cache-dir
RUN echo "export PATH=/home/mesh/.local/bin:\$PATH" >> /home/mesh/.bashrc
COPY config.yaml .
#ENTRYPOINT ["sh", "-c", "sleep 30 && python main.py"]


