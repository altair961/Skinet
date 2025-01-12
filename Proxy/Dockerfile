FROM nginxinc/nginx-unprivileged
USER nginx

WORKDIR /app
COPY . /app
RUN ls -la
# выставляем права
RUN chmod a+rw /etc/nginx/sites-available/
# копируем шаблон в файл
RUN cat skinet > /etc/nginx/sites-available/skinet
# создаем симлинк
RUN ln -sf /etc/nginx/sites-available/skinet /etc/nginx/sites-enabled/skinet
# проверяем конфиг
RUN nginx -t
# перезапускаем нгингс
RUN service nginx start