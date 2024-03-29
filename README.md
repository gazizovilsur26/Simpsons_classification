# Классификация изображений

Сегодня вам предстоить помочь телекомпании FOX в обработке их контента. Как вы знаете, сериал "Симпсоны" идет на телеэкранах более 25 лет, и за это время скопилось очень много видеоматериала. Персоонажи менялись вместе с изменяющимися графическими технологиями, и Гомер Симпсон-2018 не очень похож на Гомера Симпсона-1989. В этом задании вам необходимо классифицировать персонажей, проживающих в Спрингфилде. Думаю, нет смысла представлять каждого из них в отдельности.

Обучающая и тестовая выборка состоят из отрывков из мультсериала Симпсоны. Каждая картинка представлена в формате jpg c необходимой меткой - названием персонажа изображенного на ней. Тест был поделен на приватную и публичную часть в соотношении 95/5

В тренировочном датасете примерно по 1000 картинок на каждый класс, но они отличаются размером.

Важный момент: метки классов представлены в виде названий папок, в которых лежат картинки. Это сделано для того, чтобы вы могли без проблем использовать библиотечные загрузчики данных, а не писали свои, тратя на это весь свой последний(единственный) день, который вы отвели на задание :)

### Описание файлов
- train.csv - the training set
- testset.csv - the test set
- sampleSubmission.csv - пример решения, если у вас нет времени на задание

### Поля в данных
- image_id - id картинки
- Expected - имя персонажа

### Цель:
Получить качественный классификатор изображений на 42 класса, ключевая метрика - F1.


**Вывод:**
- Предобработка данных:
    - Был сильный дисбаланс классов,поэтому сделали аугментацию данных, чтобы увеличить кол-во маленьких классов
- Была выбрана и обучена модель `EfficientNet_b2` для классифакация изображений персонажей Симпсонов на 42 класса:
    - Была взята предобученная на данных ImageNet модель. Заменили классификтор на пользовательский, который классифицирует на 42 класса
    - Получили accuracy на валидацинной выборке `0.99`
    - Целевой метрикой соревнования была метрика f1.  Получили на публичном тесте значение `f1 = 0.99256`


  
