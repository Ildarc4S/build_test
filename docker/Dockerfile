FROM ubuntu:22.04

RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    python3-pip \
    git

RUN pip3 install conan==2.0.16

WORKDIR /project

COPY . .

RUN conan profile detect --force
RUN conan install . --build=missing

RUN cmake -B build -S . \
  -DCMAKE_TOOLCHAIN_FILE=build/Release/generators/conan_toolchain.cmake \
  -DCMAKE_BUILD_TYPE=Release
RUN cmake --build build

CMD ["./build/main"]

