FROM ubuntu:22.04

# Устанавливаем рабочую директорию
WORKDIR /home/

# Копируем локальные файлы в рабочую директорию контейнера
COPY ./cat/Makefile .
COPY ./cat/s21_cat.c . 

# Обновляем список пакетов и устанавливаем необходимые пакеты, затем очищаем загрузочные файлы
RUN apt-get update && \
    apt-get install -y build-essential make && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN make all

# Указываем команду по умолчанию, которая будет выполняться при запуске контейнера
CMD ["./s21_cat", "s21_cat.c"]

# /cat - утилита cat , созданная мною на яп C.

# Желательно запустить контйнер сразу в ИНТЕРАКТИВНОМ режиме: docker run -it --name contcat cat /bin/bash
# Прописать команду make и проверить работу программы s21_cat : ./s21_cat s21_cat.c