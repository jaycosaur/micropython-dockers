FROM python:3.8.0b3-buster

LABEL Jacob Richter <jaycorichter@gmail.com>

RUN apt update
RUN apt install -y build-essential build-essential libreadline-dev libffi-dev git pkg-config gcc-arm-none-eabi libnewlib-arm-none-eabi

RUN git clone --recurse-submodules https://github.com/micropython/micropython.git

RUN cd /micropython/mpy-cross/ && make

RUN cd /micropython/ports/unix/ && make axtls && make

CMD ["./micropython/ports/unix/micropython"]