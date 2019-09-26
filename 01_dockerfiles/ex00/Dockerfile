# From an alpine image you’ll add to your container your favorite text editor, vim or
#emacs, that will launch along with your container.


#build with docker build -t ex00 .
#then run with docker run -it --rm ex00

FROM alpine

RUN apk update && apk upgrade 
RUN apk add vim 

ENTRYPOINT vim
