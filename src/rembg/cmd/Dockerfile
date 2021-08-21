FROM nvidia/cuda:11.4.1-base-ubuntu20.04

RUN apt-get update && apt-get install -y --no-install-recommends python3 python3-pip python3-dev llvm llvm-dev
RUN pip3 install rembg

COPY server.py server.py
ENTRYPOINT ["python3 server.py"]
CMD []
