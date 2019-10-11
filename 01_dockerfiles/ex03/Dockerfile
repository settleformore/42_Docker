# Docker can be useful to test an application that’s still being developed without polluting your libraries. You will have to design a Dockerfile that gets the development
# version of Gitlab - Community Edition installs it with all the dependencies and the necessary configurations, and launches the application, all as it builds. The container will be
# deemed valid if you can access the web client, create users and interact via GIT with this
# container (HTTPS and SSH). Obviously, you are not allowed to use the official container
# from Gitlab, it would be a shame...

#docker build -t ex03 .
#docker run -it --rm -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03

FROM debian

RUN apt-get update && apt-get install -y curl openssh-server ca-certificates postfix

RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | /bin/bash

RUN apt-get install -y gitlab-ce

EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && /bin/bash