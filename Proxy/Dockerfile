FROM nginxinc/nginx-unprivileged
USER nginx

WORKDIR /app
COPY . /app
RUN ls -la
# выставляем права
RUN sudo chmod a+rw /etc/nginx/sites-available/
# копируем шаблон в файл
RUN sudo cat skinet > /etc/nginx/sites-available/skinet
# создаем симлинк
RUN sudo ln -sf /etc/nginx/sites-available/skinet /etc/nginx/sites-enabled/skinet
# проверяем конфиг
RUN sudo nginx -t
# перезапускаем нгингс
RUN sudo service nginx start