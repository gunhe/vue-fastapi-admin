FROM python:3.11-slim-bullseye

WORKDIR /opt/vue-fastapi-admin
ADD . .


# RUN sed -i "s@http://.*.debian.org@http://mirrors.ustc.edu.cn@g" /etc/apt/sources.list \
#     && apt-get update \
#     && apt-get install -y --no-install-recommends gcc python3-dev bash nginx vim curl procps net-tools

RUN pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

ENV LANG=zh_CN.UTF-8
EXPOSE 9999

ENTRYPOINT [ "sh", "entrypoint.sh" ]