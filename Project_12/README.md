## Прогнозирование количества заказов такси на следующий час

# Цель исследования
1. Построить модель, которая быстро и с наибольшим качеством прогрозирует количество заказов такси на следующий час.


# Ход исследования
Нам предоставленны данные данные из компании «Чётенькое такси» о заказах такси в аэропортах. Данные находятся в датафрейме, который мы получим из файла 'taxi.csv'. О качестве данных нам ничего не известно, поэтому перед тем, как приступать к целям исследования, понадобится обзор данных. Мы проверим данные на ошибки. Затем, на этапе предобработки мы будем искать возможность исправить все ошибки в данных, которые не приведут к искажению конечного результата. Далее приступим к целям исследования.<br>


Таким образом, исследование пройдёт в десять этапов:<br>

* Обзор данных 
* Предобработка данных 
* Ресемплирование данных по одному часу
* Анализ данных
* Подготовка выборок
* Обучение разных моделей с различными гиперпараметрами
* Выявление лучшей модели 
* Проверка наилучшей модели на тестовой выборке 
* Написание промежуточных выводов 
* Написание общего вывода


# Вывод
1. Мы загрузили и ознакомились с представленным датафреймом.
2. Выполнили ресемплирование данных по одному часу, всего в датафрейме, после ресемплирования остался 1 столбец и 4 416 записи со временным промежутком с 1 марта 2018 года по 31 августа 2018 года.
3. Мы проанализировали данные:
    * Пик активности заказов наблюдается в вечернее и ночное время, рано утром - самая низкая активность;
    * В среднем, количество заказов такси с марта по август 2018г. составляет не менее 50 заказов за час и не более 190 заказов за час;
    * Спрос на такси летом вырос по сравнению с весной, спрос на заказы такси растет с каждым последующим летним месяцем - август является лидером по заказам;
    * У всех рассматриваемых временных рядов стохастический процесс нестационарный, так как распределения меняются.
4. Мы обучили разные модели с различными гиперпараметрами:
    * Наилучшей моделью оказалась модель линейной регрессии - LinearRegression, с результатом RMSE на валидационной выборке 55.910844365717836.
5. Сделали тестовую выборку размером 10% от исходных данных.
6. Мы проверьте данные на тестовой выборке :
    * RMSE наилучшей модели линейной регрессии - LinearRegression на тестовой выборке составляет: 44.45736586680238.
7. Добились результата "значение метрики RMSE на тестовой выборке должно быть не больше 48".
      

**Рекомендации:** <br>
Мы построили модель, которая быстро и с наибольшим качеством прогрозирует количество заказов такси на следующий час. В связи с этим, компания «Чётенькое такси» может рационрально распределить свои силы и в нужное время привлечь больше водителей в период пиковой нагрузки, тем самым получив надежных работников и верных клиентов, более того, данная модель поможет в клиентоориентированности - с увеличением водителей в места пиковой нагрузки, завоюет внимание потребителей, тем самым  привлечет еще больше постоянных клиентов.


# Стек технологий
Python, Pandas, Scikit-learn, statsmodels

# Статус проекта
Завершен