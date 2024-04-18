## Определение выгодного тарифа для телеком компании

# Цель исследования
Необходимо проанализировать поведение клиентов и сделать вывод — какой тариф лучше, а так же проверить гипотезы:
* Средняя выручка пользователей тарифов «Ультра» и «Смарт» различается;
* Средняя выручка с пользователей из Москвы отличается от выручки c пользователей других регионов.

# Ход исследования
Данные о недвижимости мы получим из файла '/datasets/real_estate_data.csv'. О качестве данных ничего не известно, поэтому перед тем, как приступать к целям исследования, понадобится обзор данных.<br>
Мы проверим данные на ошибки и оценим их влияние на исследование. Затем, на этапе предобработки мы будем искать возможность исправить все ошибки в данных, которые не приведут к искажению конечного результата. Далее, создадим необходимые столбцы, и приступим к проведению исследовательского анализа.<br>

Исследование пройдёт в шесть этапов:<br> 
* Обзор данных
* Предобработка
* Анализ данных
* Проверка гипотез
* Написание промежуточных выводов
* Написание общего вывода

# Вывод
1.	Мы ознакомились с датафреймом и изучили его:
* Большой популярностью пользуются звонки продолжительностью до 5 минут, длительные звонки менее популярны
* Большинство клиентов тратят до 250 мегабайт интернета
2.	Мы провели полноценную предобработку данных;
3.	В результате работы с датафремом, мы добавили новые столбцы;
4.	Провели полноценный исследовательский анализ данных:
* Средняя выручка по тарифу smart составляет 1289, а по тарифу ultra = 2070
* Тариф ultra по количеству звонков лидирует все 12 месяцев по сравнению с тарифом smart, в среднем совершая 60-70 звонков, тогда как клиенты тарифа smart 50 звонков
* Большинство клиентов пользуются тарифом smart 
* У клиентов тарифа ultra, кроме февраля, продолжительность звонков дольше, чем у клиентов smart, в среднем 400-500 у тарифа ultra и 400 у тарифа smart 
* Клиенты тарифа ultra все месяцы, кроме февраля, отправляли больше сообщений, в среднем 40-50, чем клиенты тарифного плана smart - в среднем 30 сообщений
* Клиенты тарифного плана ultra тратят больше мобильного трафика, чем пользователи тарифа smart
* Меньше всего пользователи использовали интернет в январе, феврале и апреле
* Чаще всего абоненты тарифа Smart тратят 15–17 Гб, а абоненты тарифного плана Ultra — 19–21 ГБ
5.	Проверили гипотезы: 
* При проверке первой гипотезы мы подтвердили, что средняя выручка пользователей тарифов «Ультра» и «Смарт» различается
* При проверке второй гипотезы мы подтвердили, что средняя выручка с пользователей из Москвы не отличается от выручки c пользователей других регионов

**Рекомендации:** <br>
Проведя исследовательский анализ данных, можно с уверенностью сказать, что самый популярный у клиентов и прибыльный для компании тариф – «Ультра». Компании «Мегалайн», федеральному оператору сотовой связи, необходимо направить фокус на тариф «Ультра», так как данный тариф не только приносит больше денег, но и пользуется популярностью у клиентов, что немаловажно для компании. 

# Стек технологий
Python, Pandas, Matplotlib, NumPy, SciPy

# Статус проекта
Завершен