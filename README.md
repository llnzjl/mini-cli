Mini CLI Tool — C Program + Linux Execution + Docker Deployment

This project is a simple mini CLI tool written in C, compiled and executed inside a Linux environment, and packaged into a Docker image.
The goal is to practice the workflow of open-source development: coding → Linux build → Docker packaging → Git/GitHub workflow.

1. Mini Program (C)

File: src/mini.c

#include <stdio.h>

int main(void) {
    printf(" Mini CLI Tool is running! \n");
    printf("This program was built in Linux and packaged with Docker.\n");
    return 0;
}

2. Linux Build & Run
Install gcc
sudo apt update
sudo apt install -y gcc

Compile
gcc mini.c -o mini

Run
./mini

Linux Screenshot

(Add your screenshot here)

docs/images/linux_run.png

 3. Docker Build & Run
Dockerfile
FROM ubuntu:24.04

WORKDIR /app

COPY mini.c mini.c

RUN apt update && \
    apt install -y gcc && \
    gcc mini.c -o mini

CMD ["./mini"]

Build Docker image
docker build -t mini-cli .

Run container
docker run mini-cli

Docker Screenshots

(Add them here)

docs/images/docker_build.png
docs/images/docker_run.png

4. Git & GitHub Workflow

Created GitHub repository

Added src/, Dockerfile, README.md, LICENSE, docs/images/

Made 5+ commits

Created 1 feature branch, then merged via Pull Request

5. Project Structure
mini-cli/
 ├─ src/
 │   └─ mini.c
 ├─ Dockerfile
 ├─ README.md
 ├─ LICENSE
 └─ docs/
     └─ images/
         ├─ linux_run.png
         ├─ docker_build.png
         └─ docker_run.png

6. License

This project includes a LICENSE file (MIT License recommended).