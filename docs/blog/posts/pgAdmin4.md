---
tags:
    - Docker
title:  Run pgAdmin4 on Docker in Arch Linux
date: 2022-05-05
authors: [betty]
categories:
  - tech
---

[pgAdmin4](https://www.pgadmin.org/download/) là GUI cho postgreSQL - dbms mình sẽ học cho học phần Database ở đại học. Nó là web application được build dựa trên `python` và `Javascript/jQuery`. Việc cài đặt trên Linux rất đơn giản, với Arch linux:
<!-- more -->

```bash
$ yay -S pgadmin4
```

Nhưng app build dựa trên python, nên packages python đi kèm nó rất nhiều:

```
Packages (35): python-alembic-1.7.4-3  python-blinker-1.4-11  python-                          brotli-1.0.9-7  python-dateutil-2.8.2-4  python-editor-                 1.0.4-8  python-email-validator-1.1.3-3
              python-extras-1.0.0-10  python-fixtures-3.0.0-12  python-         flask-babelex-0.9.4-5  python-flask-compress-1.11-1               python-flask-gravatar-0.5.0-7  python-flask-login-0.6.0-1
              python-flask-mail-0.9.1-8  python-flask-migrate-3.0.0-3  python-flask-paranoid-0.2-8  python-flask-principal-0.4.0-8  python-flask-security-too-4.1.3-1
              python-flask-sqlalchemy-2.5.1-3  python-flask-wtf-1.0.0-1         python-gssapi-1.7.3-1  python-ldap3-2.9.1-3  python-paramiko-2.9.2-1  python-passlib-1.7.4-5  python-pbr-5.8.1-1
              python-psycopg2-2.9.3-1  python-pyasn1-0.4.8-7  python-pynacl-1.4.0-5  python-simplejson-3.17.6-3  python-speaklater-1.3-11  python-sqlalchemy1.3-1.3.24-5
              python-sqlparse-0.4.2-3  python-sshtunnel-0.4.0-3  python-testtools-2.5.0-3  python-wtforms-3.0.1-1  pgadmin4-4.30-3

Total Installed Size:  153,29 MiB
```

Thực tế thì khi tải xong, mình cũng gặp lỗi không thể sử dụng được :v, có thể đống package trên conflict version với python đâu đó trong máy của mình. Nhưng nói chung là rất nhiều lỗi vặt tùm lum, fix cái này lại lòi ra cái khác. 

Xem lại trên fanpage của họ thì thấy có trên [Docker](https://hub.docker.com/r/dpage/pgadmin4/), quá tiện luôn, vừa để thực hành docker gần đây học :v.

### Setup

+ Đầu tiên, pull image đó về: `docker pull dpage/pgadmin4`.

+ Trước khi run, cần lưu ý 2 cái **environment variable** của pgAdmin là `PGADMIN_DEFAULT_EMAIL` và `PGADMIN_DEFAULT_PASSWORD` để đăng nhập vào web app lúc deploy. Nên mình phải dùng flag `-e` để set trước cho nó. Tiếp theo, vì là web app, nên cần set `--network="host"` để host trong docker container chung host  với host machine (là máy của mình). 
  
  ```bash
  $ docker run --name pgadmin --network="host" -e     "PGADMIN_DEFAULT_EMAIL=admin@admin.admin" -e "PGADMIN_DEFAULT_PASSWORD=admin" -d dpage/pgadmin4
  ```

+ Giờ thì mở browser lên và truy cập url 127.0.0.1 thui :v. Đăng nhập với mail và pass mình set ở trên. 

*Tèn ten*
![!](https://github.com/betty2310/everyday/blob/master/_pic/2022.04.09-23.12.45.screenshot.png?raw=true)

Thật ra cũng chả phải là gì to tát cả, nhưng việc ứng dụng được `docker` - 1 tools mới để hoàn thành công việc, làm mình thấy rất vui :)).

Mình viết thêm đoạn script nhỏ để phần setup đầy đủ hơn, từ việc run để việc mở browser. Link [gist đây](https://gist.github.com/betty2310/bac29054f38f4a4614f250bbc8eeca39).

### References

+ https://docs.docker.com/engine/reference/run/
+ https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html
+ https://www.metricfire.com/blog/what-is-docker-network-host/