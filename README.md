![](http://www.lsi.uned.es/images/banners/lsi/Lenguajes-y-sistemas.jpg)

# VERSIÓN INESTABLE

# TADs para la práctica de EPED

Este repositorio contiene el código de los TADs proporcionados para la
realización de la pŕactica de la asignatura de EPED del departamento
LSI de la UNED.

# Configuración de Git

## Ubuntu
Si quieres usar Git conjuntamente con el llavero de Gnome, puedese seguir
estos pasos y no tendrás que introducir la contraseña cada vez:
```
% sudo apt-get install libsecret-1-dev
% cd /usr/share/doc/git/contrib/credential/libsecret
% sudo make
% git config --global credential.helper /usr/share/doc/git/contrib/credential/libsecret/git-credential-libsecret
```

Fuente: https://gist.github.com/keirlawson/0e3ac20728f9a0535eec
