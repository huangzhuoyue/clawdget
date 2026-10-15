FROM debian:bookworm-slim

# 使用国内镜像源加速 apt（bookworm 用 deb822 格式，旧格式兜底）
RUN sed -i 's|deb.debian.org|mirrors.aliyun.com|g' /etc/apt/sources.list.d/debian.sources 2>/dev/null \
 || sed -i 's|deb.debian.org|mirrors.aliyun.com|g' /etc/apt/sources.list 2>/dev/null \
 || true

RUN apt-get update \
 && apt-get install -y --no-install-recommends make gcc libc6-dev bzip2 file ca-certificates \
 && rm -rf /var/lib/apt/lists/*
