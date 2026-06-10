# Reverse-proxy для Supabase (Amvera)

Прокидывает запросы с api.fotori.ru → omxrwwheockfucjazsrt.supabase.co
Российский IP Amvera обходит блокировки провайдеров.

## Установка

1. Создать репозиторий на GitHub, залить эти 3 файла:
   - Dockerfile
   - nginx.conf
   - amvera.yml

2. В Amvera: Создать проект → тип Docker → подключить репозиторий → деплой.

3. В настройках проекта Amvera включить "Доменное имя" (бесплатный поддомен вида your-app.amvera.io) — это нужно для следующего шага.

4. У регистратора домена fotori.ru добавить CNAME:
   - Тип: CNAME
   - Имя: api
   - Значение: your-app.amvera.io (тот адрес, что выдал Amvera)
   - TTL: 300

5. В Amvera в "Доменные имена" добавить api.fotori.ru — он сам выпустит SSL.

6. Проверка: https://api.fotori.ru/healthz → должно вернуть "ok".

## После настройки
Сообщите мне "api.fotori.ru работает" — я переключу клиент Supabase на новый URL.
