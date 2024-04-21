## Исследование технологического процесса очистки золота

# Цель исследования
1. Построить модель машинного обучения, которая должна предсказать коэффициент восстановления золота из золотосодержащей руды и поможет оптимизировать производство, чтобы не запускать предприятие с убыточными характеристиками.


# Ход исследования
Нам предоставленны данные с параметрами добычи и очистки. Все данные находятся в трёх файлах: '/datasets/gold_industry_train.csv' — обучающая выборка; '/datasets/gold_industry_test.csv' — тестовая выборка; '/datasets/gold_industry_full.csv' — исходные данные. О качестве данных нам ничего не известно, поэтому перед тем, как приступать к целям исследования, понадобится обзор данных. Мы проверим данные на ошибки. Затем, на этапе предобработки мы будем искать возможность исправить все ошибки в данных, которые не приведут к искажению конечного результата. Далее приступим к целям исследования.<br>


Таким образом, исследование пройдёт в 7 этапов:<br>

* Обзор данных <br>
* Предобработка данных <br>
* Проведение исследоватльского анализа данных<br>
* Построение и обучение модели<br>
* Выявление наилучшей модели<br>
* Написание промежуточных выводов <br>
* Написание общего вывода


# Вывод
1. Мы ознакомились с тремя датафреймами:

    * gold_industry_train.csv — обучающая выборка; дубликатов не обнаружено, всего в датафрейме 86 столбцов и 14 579 записи.Имеются пропущенные значения в столбцах, однако пропущенные значения в каждом столбце составляют не более 10% от всего датафрейма.Тип данных у всех данных - float.

    * gold_industry_test.csv — тестовая выборка; дубликатов не обнаружено, всего в датафрейме 53 столбца и 4 860 записи. Имеются пропущенные значения в столбцах, однако пропущенные значения в каждом столбце составляют не более 10% от всего датафрейма. В данном датасете намного меньше признаков, чем в двух других. Тип данных у всех данных - float.

    * gold_industry_full.csv — исходные данные. дубликатов не обнаружено, всего в датафрейме 87 столбцов и 19 439 записи. Имеются пропущенные значения в столбцах, однако пропущенные значения в каждом столбце составляют не более 10% от всего датафрейма. Тип данных у всех данных - float.

    * Целевыми признаками являются final.output.recovery и rougher.output.recovery.
    
2. Проверили эффективность обогащения и найшли MAE:
    * MAE (среднее абсолютное отклонение) между эффективностью обогащения и значением признака rougher.output.recovery составляет: 9.83758577644259e-15, что является хорошим результатом, так как значение находится близко к нулю, эффективность обогащения рассчитана правильно.
    
3. Провели анализ признаков, недоступных в тестовой выборке.
4. Мы провели предобработку данных, устранили пропуски в обучающей и тренировочной выборках, а так же добавили целевые признаки в тестовую выборку.

5. Мы проанализировали как меняется концентрация металлов (Au, Ag, Pb) на различных этапах отчистки:
   * концентрация золота до флотации и после вторичной отчистки значительно увеличилась с 8.27 до 44.08
   * концентрация серебра, наоборот, уменьшилась, с 8.79 до 5.17
   * концетрация свинца увеличилась, с 3.60 до 9.98
6. Мы сравнили распределения размеров гранул исходного сырья на обучающей и тестовой выборках:
   * размер гранул исходного сырья на обучающей и тестовой выборках на этапе флотации примерно одинаковое и равняется 47;
   * размер гранул исходного сырья на обучающей и тестовой выборках на этапе первичной отчистки примерно одинаковое и равняется 7.5;
   * распределения размеров гранул не сильно отличаются друг от друга, поэтому можно смело предположить, что оценка модели будет правильной.
7. Мы исследовали суммарную концентрацию металлов на разных стадиях: в сырье, в черновом концентрате, в концентрате после первой очистки и в финальном концентрате, а так же выявили и устранили выбросы:
   * суммарная концентрация металлов до флотации (в сырье) в среднем равняется 57.41;
   * суммарная концентрация металлов после флотации (черновой концентрат) в среднем равняется 68.19;
   * суммарная концентрация металлов после первичной отчистки в среднем равняется 60.95;
   * суммарный финальный концентрат металлов в среднем равняется 68.73;
   * выбросы до 1 удалены.
   
8. Функция для вычисления итоговой sMAPE написана;
9. Мы обучили разные модели (случайный лес, решающее дерево, линейная регрессия) и оценили их качество кросс-валидацией:
   * Наилучшую относительную ошибку прогноза показала модель случайного леса с результатом 8.003, наилучшими параметрами для smape_rougher являются: глубина дерева 4, количество деревьев 21, наилучшими параметрами для smape_final являются:  глубина дерева 2, количество деревьев 21. Для проверки на тестовой выборке будет выбрана модель случайного леса.
10. Мы выбрали лучшую модель, ей оказался случайный лес и проверили на тестовой выборке:
   * Итоговое sMAPE (относительная ошибка прогноза) на тестовой выборке составляет 7.343 - наша модель работает хорошо.
11. Мы проверили модель на адекватность:
   * Итоговые ценки sMAPE константной модели на тестовых данных равны 8.392 и 8.247, что говорит нам о том, что наша модель адекватна.   

**Рекомендации:** <br>
Мы подготовили модель, которая будет адекватно предсказывать коэффициент восстановления золота из золотосодержащей руды. Модель поможет оптимизировать производство, чтобы не запускать предприятие с убыточными характеристиками. Благодаря предсказаниям модели, компания минимизирует убытки и приумножет прибыль.


# Стек технологий
Python, Pandas, Scikit-learn, Matplotlib, NumPy

# Статус проекта
Завершен