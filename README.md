# ML & DA
Уважаемый гость, в этой репозитории вы можете ознакомиться с моими работами по анализу данных и машинному обучению.

p.s. для просмотра ноутбуков, переходите по сссылке :wink:
# Machine Learning
## [Предсказание оттока клиентов в продуктовом ритейле](https://nbviewer.jupyter.org/github/EuMentality/ML-DA/blob/main/notebooks/forecasting_customer_churn.ipynb)
### По данным российской сети гипермаркетов надо проанализировать поведение клиентов, определить оптимальную методологию определения отточных клиентов. По выбранной методологии разработать модель вероятности оттока. 
* Стратегия определения отточных клиентов
* Предподготовка данных 
* Генерация признаков для построения моделей (Сгенерированные признаки -> тестовая модель -> проверка качества -> новые факторы -> тестовая модель -> проверка качества и так реккурентно.
* Построение итоговой вероятностной модели оттока клиентов
* Анализ результатов. Важность признаков, интерпретируемость модели. 

## [Catch Me If You Can](https://nbviewer.jupyter.org/github/EuMentality/ML-DA/blob/main/notebooks/catch_me.ipynb)
### [Kaggle competition](https://www.kaggle.com/c/catch-me-if-you-can-intruder-detection-through-webpage-session-tracking2/overview)

Задача идентификации взломщика по его поведению в сети Интернет. Это сложная и интересная задача на стыке анализа данных и поведенческой психологии. 

Здесь мы пытаемся идентифицировать пользователя в Интернете, отслеживая его/ее последовательность посещаемых веб-страниц. Алгоритм, который будет построен, будет принимать сеанс веб-страницы (последовательность веб-страниц, посещаемых, следовательно, одним и тем же человеком) и предсказывать, принадлежит ли он взломщику или кому-то еще

Данные собраны с прокси-серверов Университета Блеза Паскаля. "A Tool for Classification of Sequential Data", авторы Giacomo Kahn, Yannick Loiseau и Olivier Raynaud.
* Предобработка данных. Используя данные по посещенным сайтам и словарем, создана разреженная матрица, так называемая bag_of_sites для каждой сессии 
* Анализируя время начала сессии, сгенерированы достаточно хорошие признаки, которые позволяют лучше идентифицировать взломщика
* Во время работы было замечено, что взломщики начинают сессию в большинстве случае с посещения сайта "youtube" (#site = 80)
* Скор итоговой модели AUC ROC = 0.947 (kaggle sub)




# Data Analysis
## [Анализ результатов АБ-теста](https://nbviewer.jupyter.org/github/EuMentality/ML-DA/blob/main/notebooks/yandex_ab_test_analyse.ipynb)
### В данной работе анализируются результаты АБ - теста по изменению поисковой страницы компании Яндекс. Следует подтвердить или опровергнуть наличие изменений в пользовательском поведении между контрольной (control)  и тестовой (exp)  группами, определить характер этих изменений и практическую значимость вводимого изменения и понять, какая из пользовательских групп более всего проигрывает / выигрывает   от тестируемого изменения.
* Анализ разницы между двумя группами (control и exp) относительно количества пользовательских кликов.
  * Используя бутстреп подход, проанализированы 95% доверительные интервалы для средних значений и медиан количества кликов в каждой из двух групп.
  * С помощью критерия Манна-Уитни проверена гипотеза о равенстве средних
* Анализ влияния эксперимента на пользовательские группы

  Для каждой пользовательской группы (по каждому из уникальных значений столбца browser) применен критерий Манна-Уитни между control и exp группами + поправка Холма-Бонферрони на множественную проверку.


## [Анализ данных в задаче кредитного скоринга](https://nbviewer.jupyter.org/github/EuMentality/ML-DA/blob/main/notebooks/credit_scoring.ipynb)
### По данным о кредитных историях клиентов одного из банков, стояла задача проанализировать и сравнить показатели в двух группах, тех кто вернул кредит и тех кто не вернул кредит. Полезность данной процедуры заключается в том, что определив факторы, которые различаются статистически в двух группах, в дальнейшем будет проще идентифицировать клиента, который не вернет кредит. Например нам стали известны данные показатели после анализа, можно их включить в модель, которая предсказывает вероятность возврата кредита, тем самым повысив качество модели.
* Кредитный лимит
  * Проверка гипотезы о равенстве медианных значений кредитного лимита с помощью интервальной оценки
  * Проверка гипотезы о равенстве распределений с помощью перестановочного критерия для независимых выборок
* Гендерная принадлежность. 
  Проверка гипотезы о том,  что гендерный состав  группы людей вернувших и не вернувших кредит отличается
* Образование. 
  Проверка гипотезы: образование не влияет на возврат кредита
* Семейное положение.
  Связь семейного статуса с индикатором дефолта
* Возраст
  * Проверка гипотезы о равенстве медианных значений в двух группах
  * Проверка гипотезы о равенстве распределений в двух группах
  
## [Обнаружение статистически значимых отличий в уровнях экспрессии генов больных раком](https://nbviewer.jupyter.org/github/EuMentality/ML-DA/blob/main/notebooks/Gene_analysis.ipynb)
### Ученые из Stanford School of Medicine провели секвенирование биологического материала 72 испытуемых (Секвенирование — это определение степени активности генов в анализируемом образце с помощью подсчёта количества соответствующей каждому гену РНК) чтобы понять, какие из этих генов наиболее активны в клетках больных людей. В эксперименте принимали участие 24 человека, у которых не было рака груди (normal), 25 человек, у которых это заболевание было диагностировано на ранней стадии (early neoplasia), и 23 человека с сильно выраженными симптомами (cancer). В этой работе была попытка обнаружить те гены, активность которых у людей в разных стадиях заболевания отличаеюся статистически и практически значимо.
* Примененение t-критерия Стьюдента для проверки гипотезы о равенстве средних в двух независимых выборках.
* Использовалась поправка на множественную проверку гипотез и практическую значимость отличий
  * Поправка методом Холма
  * Поправка методом Бенджамини-Хохберга
* Было определено количество значимых отличий в генах у групп "Сильно выражены симптомы Рака", "Рак диагностирован на ранней стадии" и "Не болел раком груди","Рак диагностирован на ранней стадии".
