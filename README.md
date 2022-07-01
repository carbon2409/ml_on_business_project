# ml_on_business_project
Курсовой проект по курсу "Машинное обучение в бизнесе"


Стек:

ML: sklearn, pandas, numpy
API: flask
Данные: медосмотр

Задача:  определить вероятность наличия сердечно-сосудистых заболеваний (поле cardio). Бинарная классификация

Используемые признаки:

- age (int64)
- gender (int64)
- height (int64)
- weight (float64)
- ap_hi (int64)
- ap_lo (int64)
- cholesterol (int64)
- gluc (int64)
- smoke (int64)
- alco (int64)
- active (int64)

Преобразования признаков: StandardScaler, OHEEncoder

Модель: CatBoost

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/carbon2409/ml_on_business_project.git
$ cd ml_on_business_project
$ docker build -t gb_docker_flask .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -v <your_local_path_to_pretrained_models>:/app/app/models gb_docker_flask
```
