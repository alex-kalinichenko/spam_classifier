# python-flask-docker spam classifier
Итоговый проект для курса "Машинное обучение в бизнесе"

Стек:

- ML: sklearn, pandas, numpy
- API: flask
- Данные: ссобраны и классифицированы самостоятельно с одной из групп в телеграмме

**Задача**: предсказать по тексту сообщения является ли оно спамом или нет (поле spam). Бинарная классификация

Преобразования признаков: tfidf

Модель: logreg

### Клонируем репозиторий и создаем образ
```bash
$ git clone https://github.com/...
$ cd spam_classifier
$ docker build -t spam_classifier .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```bash
$ cd ..
$ docker run -d -p 8180:8180 -p 8181:8181 -v spam_classifier_pipline.dill:/app/app/models spam_classifier
```

### Переходим в веб-интерфейс

Переходим в браузер по ссылке: http://localhost:8181/