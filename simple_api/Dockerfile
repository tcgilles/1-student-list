FROM python:3.8-buster

LABEL author="Gilles Takam Cheno"
LABEL description="This image builds the simple-api API"

WORKDIR /

COPY ./student_age.py .
COPY ./requirements.txt .

RUN apt update -y \
    && apt install python-dev python3-dev libsasl2-dev libldap2-dev libssl-dev -y \
    && rm -rf /var/lib/apt/lists/* \
    && apt clean \
    && pip install --no-cache-dir -r requirements.txt \
    && mkdir -p data

VOLUME /data

EXPOSE 5000/tcp

ENTRYPOINT [ "python3" ]
CMD [ "./student_age.py" ] 

