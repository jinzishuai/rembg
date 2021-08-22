FROM nvidia/cuda:11.4.1-base-ubuntu20.04

RUN apt-get update && apt-get install -y --no-install-recommends python3 python3-pip python3-dev build-essential llvm llvm-dev

COPY requirements.txt /requirements.txt
RUN pip3 install -r /requirements.txt
RUN python3 -c 'import pymatting_aot.cc'

COPY server.py /server.py
COPY newrelic.ini /newrelic.ini
ENV NEW_RELIC_CONFIG_FILE=/newrelic.ini
ENTRYPOINT ["newrelic-admin", "run-program", "python3", "/server.py"]
CMD []
EXPOSE 5000
