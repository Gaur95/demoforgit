# Docker
```
wget https://www.free-css.com/assets/files/free-css-templates/download/page296/carvilla.zip
 1983  ls
 1984  unzip carvilla.zip 
 1985  ls
 1986  cp -r carvilla-v1.0 apache/
 1987  ls
 1988  cd apache/
 1989  ls
 1990  curl -o https://www.free-css.com/assets/files/free-css-templates/download/page296/carvilla.zip
 1991  curl -O https://www.free-css.com/assets/files/free-css-templates/download/page296/carvilla.zip
 1992  ls
 1993  rm carvilla.zip 
 1994  ls
 1995  vim Dockerfile
 1996  cd docker/
 1997  cd apache/
 1998  ls
 1999  vim Dockerfile 
 2000  docker build -t myweb .
 2001  docker run -d -p 1122:80 myweb
 2002  docker ps
 2003  ifconfig 
 2004  ls
 2005  cat Dockerfile 
 2006  ls
 2007  wget https://www.free-css.com/assets/files/free-css-templates/download/page296/neogym.zip
 2008  ls
 2009  unzip neogym.zip 
 2010  ls
 2011  vim Dockerfile 
 2012  docker build -t web2 .
 2013  docker run -d -p 1133:80 web2
 2014  docker ps
 2015  ls
 2016  vim neogym-html/
 2017  vim neogym-html/index.html 
 2018  docker run -d -p 1133:80 web2
 2019  docker run -d -v /home/akash/docker/apache/neogym-html:/var/www/html -p 1144:80 web2 
 2020  docker ps
 2021  cd neogym-html/
 2022  ls
 2023  vim index.html 
 2024  ls
 2025  rm -r *
 2026  cd ..
 2027  ls
 2028  cp -r carvilla-v1.0/. neogym-html/.
 2029  cd neogym-html/
 2030  ls
 2031  rm -r *
 2032  ls
 2033  vim index.html
```
