# Список задач

## Задача 100 (групповая)
* __Название__: Мультимодельное представление динамических систем
* __Задача__: Рассматривается система, описываемая аттракторами в нескольких фазовых пространствах. Строятся частные модели, аппроксимирующие измерения состояния системы в каждом пространстве. Строится согласующая мультимодель. Уточняются параметры частных моделей. 
* __Данные__: Видео движения человека, сигналы акселерометра, гироскопа, электроэнцефалограмма
* __Литература__: Наши работы по акселерометрам и BCI, диссертации Мотренко, Исаченко, Грабового
* __Базовой алгоритм__: Частные модели - нейросети, мультимодель – канонический корреляционный анализ и дистиллируется мультимодель.
* __Решение__: Обобщить канонический корреляционный анализ и дистилляцию на случай произвольного числа моделей.
* __Новизна__: Построено выравнивающее пространство для набора гетерогенных моделей
* __Авторы__: А.В. Грабовой, В.В. Стрижов


## Задача 90
* __Название__: Восстановление движения руки по видео
* __Задача__:  По видеоряду восстанавливается скелетное представление позы человека. Траектория движения конечностей человека задает исходное фазовое пространство. Сигнал акселерометра с конечностей задает целевое фазовое пространство. Построить модель, связывающую аттракторы траекторий исходного и целевого пространств. 
* __Данные__: Начальная выборка собирается авторами проекта. Части выборки находятся в примерах к библиотекам.
* __Литература__: 
* __Базовой алгоритм__: 
* __Решение__: Теоретическая часть, выполняемая расширенной командой. Выполнить теоретическое исследование: показать, что метод канонического корреляционного анализа (и в частности, методы PLS, NNPLS, seq2seq, Neur ODE) являются частными случаями метода сходящихся перекрестных отображений Сугихары.
* __Новизна__: Введена обращаемая модель, отображающая координаты, восстановленные по видеоряду, в ускорения акселерометра мобильного телефона.
* __Авторы__: А.Д. Курдюкова, Р.И. Исаченко, В.В. Стрижов

## Задача 91
* __Название__: Кластеризация траекторий движения человека
* __Задача__: This paper analyses the periodic signals in the time series to recognize human activity
by using a mobile accelerometer. Each point in the timeline corresponds to a segment of
historical time series. This segments form a phase trajectory in phase space of human activity.
The principal components of segments of the phase trajectory are treated as feature descriptions
at the point in the timeline. The paper introduces a new distance function between the points
in new feature space. To reval changes of types of the human activity the paper proposes an
algorithm. This algorithm clusters points of the timeline by using a pairwise distances matrix.
The algorithm was tested on synthetic and real data. This real data were obtained from a
mobile accelerometer
* __Данные__: USC-HAD, новые выборки по акселерометрам
* __Литература__: Grabovoy A.V., Strijov V.V. Quasi-periodic time series clustering for human activity recognition // Lobachevskii Journal of Mathematics, 2020, 41 : 333-339.
* __Базовой алгоритм__: Гусеница
* __Решение__: Статью Грабового из Lobachevsky Journal of Mathematics довести до ума
* __Новизна__: Использовать Neuro ODE для построения фазовой траектории и ее классификации
* __Авторы__: А.В. Грабовой (спросить!!), В.В. Стрижов

## Задача 97
* __Название__: Антидистилляция или обучение учителя: перенос знаний от простой модели к сложной
* __Задача__: Рассматривается задача адаптации модели к новой выборке с большим количеством информации. Для адаптации предлагается построить новую модель большей сложности с дальнейшим переносом в нее информации от простой модели. При переносе информации требуется учитывать не только качество прогноза на исходной выборке, но так же и адаптируемость новой модели к новой выборке и робастнсоть полученного решения.
* __Данные__: Выборка рукописных цифр MNIST, Выборка изображений CIFAR-10
* __Литература__: Исходная постановка задачи дистилляции: Hinton G. et al. Distilling the knowledge in a neural network //arXiv preprint arXiv:1503.02531
* __Базовой алгоритм__: Предлагается увеличить сложность модели, включив в модель константные значения, близкие к нулю. Такой подход является базовым, т.к. может вести к снижению робастности модели и худшей адаптивности к новой выборке.
* __Решение__: Предлагается рассмотреть несколько подходов к увеличению сложности модели, включающие в себя как вероятностные  (добавление шума в новые параметры с учетом эксплуатационных требований), так и алгебраические (расширение параметрического пространства модели с учетом требований к робастности и константы Липшица исходной модели)
* __Новизна__: получение метода, позволяющего адаптировать существующую модель к усложнению обучающей выборки без потери информации
* __Авторы__ Бахтеев, Грабовой, Стрижов

## Задача 98
* __Название__: Выбор модели глубокого обучения с контролем соответствия экспертной модели
* __Задача__: рассматривается задача классификации. Задана экспертная модель низкой сложности. Требуется построить модель глубокого обучения, дающую высокое качество прогноза и схожую по поведению экспертной модели.
* __Данные__: Социологические выборки, выборка изображений CIFAR
* __Литература__: Yakovlev Konstantin, Grebenkova Olga, Bakhteev Oleg, Strijov Vadim. Neural architecture search with structure complexity control // Communications in Computer and Information Science (Proceedings of the 10th International Conference on Analysis of Images, Social Networks and Texts), 2021
* __Базовый алгоритм__: построение экспертной модели.
* __Решение__: Предлагаемый метод заключается в гиперсетей с контролем согласованности найденной модели с экспертной моделью. Под гиперсетью понимается модель глубокого обучения, порождающая параметры целевой модели.
* __Новизна__: предложенный метод позволяет учитывать экспертную оценку в процессе выбора модели и поиска архитектуры.
* __Авторы__: Гребенькова, Бахтеев, Стрижов

## Задача 99
* __Название__: Выбор интерпретируемых сверточных моделей глубокого обучения
* __Задача__: Рассматривается задача выбора интерпретируемой модели классификации глубокого обучения. Под интерпретируемостью понимается способность модели: а) возвращать наиболее значимые признаки объекта для классификации, б) определять кластеры объектов, являющихся схожими с точки зрения классификатора
* __Данные__: Выборка рукописных цифр MNIST, Выборка изображений CIFAR-10
* __Литература__:
  1) [Exact and Consistent Interpretation for Piecewise Linear Neural Networks: A Closed Form Solution](https://arxiv.org/pdf/1802.06259.pdf)
  2) ["Why Should I Trust You?": Explaining the Predictions of Any Classifier](https://arxiv.org/abs/1602.04938)
* __Базовой алгоритм__: Алгоритм LIME (1) интерпретирует модель методом локальной аппроксимаци
* __Решение__: Предлагается решение на основе метода, изложенного в (2). В данной работе было предложено обобщение модели многослойного перцпетрона с кусочно-линейной функцией активации. Такая функция активации позволяет рассматривать классификатор для каждого объекта выборки как локально-линейный, при этом без использования аппроксимации. Предлагается обобщить предложенный подход на основные нелинейные функции, используемые в сверточных нейронных сетях: функции свертки, пулинга и нормализации.
* __Новизна__: заключается в получении нового класса нейронных моделей, поддающихся хорошей интерпретации.
* __Авторы__: Яковлев, Бахтеев, Стрижов

## Задача 101
* __Title__: Stochastic Newton with Arbitrary Sampling
* __Problem__: We analyze second order methods solving Empirical Risk Minimization problem of the form min f(x) in R^d. Here x is a parameter vector of some Machine Learning model, f_i(x) is a loss function on i-th training point (a_i,b_i). Our desire to solve it using Newton-type method that requires access to only one data point per iteration. We investigate different sampling strategies of index i_k on iteration k. See description in [PDF.](http://www.machinelearning.ru/wiki/images/5/5c/Stochastic_Newton_with_Arbitrary_Sampling.pdf)
* __Dataset__: It is proposed to use open SVM library as a data for experimental part of the work.
* __References__:
  1. Stochastic Newton and Cubic Newton Methods with Simple Local Linear-Quadratic Rates
  2. Parallel coordinate descent methods for big data optimization
* __Base algorithm__: As a base method it is proposed to use Algorithm 1 from the paper Stochastic Newton and Cubic Newton Methods with Simple Local Linear-Quadratic Rates.
* __Solution__: Is is proposed to adjust existing sampling strategies from Parallel coordinate descent methods for big data optimization in this work.
* __Novelty__: In the literature of Second Order methods there are a few works on incremental methods. The idea is to analyze the existing method by applying different sampling strategies. It is known that the proper sampling strategies may improve the performance of a method.
* __Authors__:  Islamov Rustem, Vadim Strijov

## Задача 107
* __Title__: Compression for Federated Random Reshuffling
* __Problem__: We analyze first order methods solving Empirical Risk Minimization problem of the form min f(x) in R^d. Here x is a parameter vector of some Machine Learning model, f_i(x) is a loss function on i-th training point (a_i,b_i). We focus on distributed setting of this problem. We are going to apply compression techniques to reduce number of communicated bits to overcome communication bottleneck. Also we want to combine it with server-side updates. We desire to generalize and get improvement in theory and practice.
* __Dataset__: It is proposed to use open SVM library as a data for experimental part of the work.
* __References__:
  1. [Federated Random Reshuffling with Compression and Variance Reduction](https://fl-icml.github.io/2021/papers/FL-ICML21_paper_34.pdf)
  2. [Proximal and Federated Random Reshuffling](https://arxiv.org/pdf/2102.06704.pdf)
  3. [Server-Side Stepsizes and Sampling Without Replacement Provably Help in Federated Optimization](https://arxiv.org/pdf/2201.11066.pdf)
* __Base algorithm__: As a base method we use Algorithm 3 from [Proximal and Federated Random Reshuffling](https://arxiv.org/pdf/2102.06704.pdf).
* __Solution__: Is is proposed to combine the method with two stepsizes with compression operators.
* __Novelty__: This would be the first method combining 4 popular federated learning techniques: local steps, compression, reshuffling of data and two stepsizes. 
* __Authors__:  Grigory Malinovsky

## Задача 107
* __Название__: Дистилляция знаний с использованием представления выборки в общем латентном пространстве моделей
* __Задача__: Рассматривается задача дистилляции - передачи информации от одной или более моделей учителя к ученику. Рассматривается специальный случай, когда учителя обладают неполной информацией о выборке, и каждая модель имеет полезную информацию только о некотором подмножестве.
* __Данные__: Выборка изображений CIFAR-10; выборка рукописных цифр MNIST
* __Литература__: 
  1. Hinton G. et al. Distilling the knowledge in a neural network //arXiv preprint arXiv:1503.02531. – 2015. – Т. 2. – №. 7.
  2. Oki H. et al. Triplet Loss for Knowledge Distillation //2020 International Joint Conference on Neural Networks (IJCNN). – IEEE, 2020. – С. 1-7.
* __Базовой алгоритм__: Дистилляция Хинтона [1].
* __Решение__: Предлагается рассмотреть скрытые представления учителей и ученика получаемые при помощи алгоритмов снижения размерности. Для выравнивания пространств моделей предлагается применять модель автокодировщика с триплетными ограничениями (см., например, [2]). 
* __Новизна__: Предложенный метод позволит производить дистилляцию разнородных моделей, с использованием информации от нескольких учителей.
* __Авторы__: Горпинич, Бахтеев, Стрижов

## Задача 92
* __Задача__: Тематическое моделирование 
* __Данные__:
* __Литература__: 
* __Базовой алгоритм__: 
* __Решение__: 
* __Новизна__:
* __Авторы__: А.С. Попов

## Задача 93
* __Название__: Оценки риска возникновения лесных пожаров методами машинного обучения. 
* __Задача__: Прогноз риска возникновения лесных пожаров (wildfire risk prediction) по значениям климатических переменных (температура воды/воздуха, атмосферное давление) с 1991 года. Прогнозирование осуществляется (а) в краткосрочном диапазоне (2-5 лет; стационарный временной ряд) и (б) в долгосрочном диапазоне (до 50 лет; нестационарный временной ряд). Особенность прогнозирования в долгосрочном диапазоне состоит в (вероятном) существенном изменении поведения климатических переменных (сценарии CMIP5). 
Ключевые особенности задачи (1) необходимость достаточно точного прогноза экстремальных значений риска (максимальных значений временного ряда), в то время как алгоритм может совершать существенное число ошибок в области малых значений ряда. (2) пространственная структура данных ряда. 
* __Данные__: 
  1. Google Earth Data – данные по климатическим переменным и ланшафту, доступные по API (есть jupyter notebook, через который можно скачать данные локально)
https://developers.google.com/earth-engine/datasets/catalog/IDAHO_EPSCOR_TERRACLIMATE 
  2. Климатические сценарии CMIP5 (есть jupyter notebook, через который можно скачать данные локально)  https://www.worldclim.org/data/cmip6/cmip6_clim2.5m.html
  3. Wildfire Risk Database https://daac.ornl.gov/cgi-bin/theme_dataset_lister.pl?theme_id=8
  4. Severe Weather Dataset https://www.visualcrossing.com/weather/weather-data-services 
* __Литература__: 
  1. Daizong Ding, Mi Zhang, Xudong Pan, Min Yang, Xiangnan He. Modeling Extreme Events in Time Series Prediction. KDD-2019. http://staff.ustc.edu.cn/~hexn/papers/kdd19-timeseries.pdf 
  2. Roman Kail, Alexey Zaytsev, Evgeny Burnaev. Recurrent Convolutional Neural Networks help to predict location of Earthquakes. https://arxiv.org/abs/2004.09140 
  3. Nikolay Laptev, Jason Yosinski, Li Erran Li, Slawek Smyl. Time-series Extreme Event Forecasting with Neural Networks at Uber. http://roseyu.com/time-series-workshop/submissions/TSW2017_paper_3.pdf 
* __Базовой алгоритм__: (1) метод из статьи 1, (2).  ST-LSTM
* __Решение__: предлагается решать задачу в два шага. На первом шаге алгоритмом 1 (с добавление пространственной компоненты) восстанавливается (усредненное в некотором диапазоне) поведение временного ряда. Далее, анализируется невязка значений ряда и модели. На основе этого восстанавливается распределение шума и строится вероятностная модель достижения определенного уровня риска на заданной территории в необходимом диапазоне времени. 
* __Новизна__: (geo)-spatial time series prediction – открытая область с большим потенциалом для теоретических и практических работ. В частности, оценка риска пожаров необходима (1) прогноза вероятности аварий (электроэнергетика, газо-транспортный комплекс); (2) приоритизации противопожарных мер по регионам; (3) оценки финансовых рисков компаний работающих в области. 
* __Авторы__: Юрий Максимов, Алексей Зайцев
* __Консультанты__: Юрий Максимов, Алексей Зайцев, Александр Лукашевич. 

## Задача 94
* __Название__: Прогноз выпадения града с помощью графовых нейронных сетей
* __Задача__: Прогноз риска выпадения града (hail risk prediction) по значениям климатических переменных (температура воды/воздуха, атмосферное давление) с 1991 года. Прогнозирование осуществляется (а) в краткосрочном диапазоне (2-5 лет; стационарный временной ряд) и (б) в долгосрочном диапазоне (до 50 лет; нестационарный временной ряд). Особенность прогнозирования в долгосрочном диапазоне состоит в (вероятном) существенном изменении поведения климатических переменных (сценарии CMIP5). 
Ключевые особенности задачи (1) редкие события, случае выпадения града в России за последние 30 лет было менее 700 на всей территории страны (2) пространственная структура данных ряда. 
* __Данные__: 
  1. Google Earth Data – данные по климатическим переменным и ланшафту, доступные по API (есть jupyter notebook, через который можно скачать данные локально)
https://developers.google.com/earth-engine/datasets/catalog/IDAHO_EPSCOR_TERRACLIMATE 
  2. Климатические сценарии CMIP5 (есть jupyter notebook, через который можно скачать данные локально)  https://www.worldclim.org/data/cmip6/cmip6_clim2.5m.html
  3. База экстремальных событий  NOAA Storm Events Database https://www.ncdc.noaa.gov/stormevents/ftp.jsp
  4. База экстремальных событий European Severe Weather Database https://eswd.eu/cgi-bin/eswd.cgi
  5. Severe Weather Datasett https://www.visualcrossing.com/weather/weather-data-services
* __Литература__: 
  1. Ayush, Kumar, et al. "Geography-aware self-supervised learning." Proceedings of the IEEE/CVF International Conference on Computer Vision. 2021. https://openaccess.thecvf.com/content/ICCV2021/papers/Ayush_Geography-Aware_Self-Supervised_Learning_ICCV_2021_paper.pdf 
  2. Cachay, Salva Rühling, et al. "Graph Neural Networks for Improved El Ni\~ no Forecasting." arXiv preprint arXiv:2012.01598 (2020). NeurIPS Clima Workshop. https://arxiv.org/pdf/2012.01598.pdf 
  3. Cai, Lei, et al. "Structural temporal graph neural networks for anomaly detection in dynamic graphs." Proceedings of the 30th ACM International Conference on Information & Knowledge Management. 2021. https://dl.acm.org/doi/pdf/10.1145/3459637.3481955 
* __Базовой алгоритм__: классификация с экстремально редкими событиями, самый базовый вариант log-regression + SMOTE. За основу в работе предлагается взять комбинацию алгоритмов из статей 2 и 3.
* __Решение__: предполагается, что комбинация алгоритмов из статей 2 и 3 может улучшить классификацию в подобных задачах с исключительно редкими событиями. Кроме того, предполагается использовать физическую информацию для регуляризации классификатора (комбинации температурных/влажностных факторов, при которой град наиболее вероятен)
* __Новизна: (geo)-spatial time series prediction – открытая область с большим потенциалом для теоретических и практических работ. В частности, оценка риска пожаров необходима (1) прогноза вероятности повреждений (сельское хозяйство, животноводство); (2) оценка страховых и финансовых рисков.
* __Авторы__: Юрий Максимов (point of contact), Алексей Зайцев
* __Консультанты__: Юрий Максимов (point of contact), Алексей Зайцев, Александр Булкин.

## Задача 95
* __Название__: Identification the transmission rate and time-dependent noise for the stochastic SIER disease model with vital rates (Time-dependent parameter identification for a stochastic epidemic model)
* __Задача__: Ставится задача поиска оптимальных зависимых от времени параметров для известной стохастической модели распространения заболевания SIER.  Оптимальные параметры-это параметры стохастического уравнения, при которых выборка  скорости распространения вируса в ограниченной популяции, при использовании сравнения с оптимальной выборкой. Предлагается использовать адаптивный обобщенный метод моментов с локальным запаздыванием (LLGMM) основаный на обобщенном методе моментов (GMM). 
* __Данные__: Данные по росту заболеваний коронавирусом от Института Хопкинса доступны на различных ресурсах. Также данные можно скачать самостоятельно по ссылке 
* __Литература__: 
  1. Anna Mummert, Olusegun M. Otunuga  Parameter identification for a stochastic SEIRS epidemic model: case study influenza PDF
  2. David M. Drukker Understanding the generalized method of moments (GMM): A simple example LINK
* __Ключевые слова__: Compartment disease model, Stochastic disease model, Local lagged adapted generalized method of moments,  Time-dependent transmission rate
* __Базовый алгоритм__: в интернете несколько разных вариантов, например статья  B.Tseytlin Actually forecasting COVID-19 LINK нынешняя программа не дает хорошей сходимости, потому что использует всегда фиксированное количество точек для предсказания
* __Новизна__: новый LLGMM метод моментов, повышающий точность предсказания&  Базовая идея метода моментов заключается в использовании в моментных условиях (моментные функции или просто моменты) вместо математических ожиданий выборочные средние, которые согласно закону больших чисел при достаточно слабых условиях должны асимптотически сходится к математическим ожиданиям. Поскольку количество условий на моменты в общем случае больше количества оцениваемых параметров, то однозначного решения эта система условий не имеет. Обобщенный метод моментов предлагает ситуацию, когда условий на моменты можно получить больше, чем оцениваемых параметров. Метод строит условия момента (моментные функции), также называемые условиями ортогональности, в более общем виде как некоторую функцию параметров и данных модели. Параметры оцениваются путем минимизации определенной положительно квадратичной формы от выборочных средних для моментов (моментных функций). Квадратичная форма находится в итерационном процессе с требуемой точностью. Если модель содержит более одного параметра (это наш случай), подлежащего идентификации, то для построения условий момента  используются второй и выше моменты. LLGMM определяет зависящие от времени параметры, используя ограниченное количество «точек» временного ряда данных для формирования условий момента, а не весь ряд. Таким образом, метод запаздывает. Кроме того, количество используемых элементов временного ряда варьируется для каждой оценки в зависимости от времени. Таким образом, метод является локальным и адаптивным.
* __Автор__: эксперт Маркашева Вера (лаборатория вычислительной биоинформацики Центра системной биологии)

## Задача 96
* __Название__: Влияние локдауна на динамику эпидемии
* __Задача__: Введение локдауна считается эффективной мерой по борьбе с эпидемией. Однако вопреки интуиции оказалось, что при определенных условиях локдаун может привести к росту эпидемии.  Данный эффект отсутствует для классических моделей «в среднем», но был выявлен при моделировании распространения эпидемии с учетом графа контактов. Задача заключается в поиске формульных и количественных соотношений между параметрами, при которых локдаун может привести к росту эпидемии.
* __Данные__: Реальные данных о распространении эпидемии на графах контактов, особенно с учетом необходимости анализа сценариев недоступны. Задача предполагает работу с модельными и синтетическими данными: имеются готовые данные, а также предполагается возможность генерации новых в процессе решения задачи.
* __Литература__: 
* __Авторы__: Антон Бишук, А.В. Зухба

## Задача 102
* __Название__: Графовые нейронные сети в задаче регрессии пар графов
* __Задача__: Рассматривается задача регрессии на паре графов. В паре каждой вершине одного графа соответствует вершина
второго графа. Требуется установить оптимальную архитектуру графовой нейронной сети, учитывающий данный порядок,
заданный на вершинах.
* __Данные__: Предлагается использовать датасеты свойств химических реакций 
[(github)](https://github.com/hesther/reactiondatabase). Для данного датасета пара графов задается естественным образом.
Это графы молекул исходных веществ и продуктов химической реакции. 
* __Литература__:
  * [DRACON: disconnected graph neural network for atom mapping in chemical reactions.](https://chemrxiv.org/engage/chemrxiv/article-details/60c74e0f9abda2cf1af8d58a)
  * [Machine learning of reaction properties via learned representations of the condensed graph of reaction.](https://chemrxiv.org/engage/api-gateway/chemrxiv/assets/orp/resource/item/6112ac487117507542e68bef/original/machine-learning-of-reaction-properties-via-learned-representations-of-the-condensed-graph-of-reaction.pdf)
  * [A comprehensive survey on graph neural networks.](https://ieeexplore.ieee.org/abstract/document/9046288)
* __Базовый алгоритм__: Отношение графов задается на уровне эмбеддингов графов. То есть строится отдельный 
вектор-эмбеддинг для каждого графа, а затем данные вектора конкатенируются. В данном случае явно не используется информация
о соответствии вершин в графах. 
* __Новизна__: На примере архитектуры графовой нейронной сети с фиксированными гиперпараметрами с теоретической и практической точки зрения 
изучить способы добавления в графовую нейронную сеть информацию об отношении графов. 
* __Авторы__: Никитин Филипп, Вадим Стрижов, Александр Исаев. 

## Problem 103
* __Requirement__ Flient English to collaborate
* __Introduction__ [See full description here.](http://www.machinelearning.ru/wiki/images/f/fa/M1p_ppis.pdf). Proteins are involved in several biological reactions by means of interactions with other proteins or with other molecules such as nucleic acids, carbohydrates, and ligands. Among these interaction
types, protein–protein interactions (PPIs) are considered to be one of the key factors as they are involved in most of the cellular processes [1]. The binding of two proteins can be viewed as a reversible and rapid process in an equilibrium that is governed by the law of mass action. Binding affinity is the strength of the interaction between two (or more than two) molecules that bind reversibly (interact). It is translated into physico-chemical terms in the dissociation constant Kd, the latter being the concentration of free protein at which half of all binding sites of the second protein type are occupied [2]. 
* __Objectives__  Three main objectives of this work can be formulated as follows:
  1. Refine PDBbind [12] data and a standard binding affinity dataset [3], and compile a novel
benchmark of PPIs with known binding affinity values
  2. Employ graph-learning toolset to predict binding affinities of PPIs from the new dataset
  3. Benchmark the resulting method against existing state-of-the-art approaches
* __Data & Metrics__ In this work, we will operate on experimentally-observed three-dimensional structures of protein-protein complexes annotated with the binding affinity values. Two main sources of data are the following:
  * PDBbind dataset [12] that includes around 2k PPIs
  * Standard dataset introduced in [3] that includes 144 PPIs As main regression metrics, we suggest to consider Mean Squared Error (MSE), Mean Absolute Error (MAE) and Pearson correlation.
* __Novelty__ To the best of our knowledge, geometric deep learning methods have never been applied to the protein-protein binding affinity prediction problem so far.
* __Requirements__ 
  * Fluent English
  * Python and PyTorch (medium level and higher), Git, Bash
  * Background in computational biology is a plus
* __Authors__: Arne Schneuing, Ilia Igashov


## Задача 109 
* __Название__ Непрерывное время при построении нейроинтерфейса BCI 
* __Задача__: В задачах декодирования сигнала данные представляются как многомерные временные ряды. При решении задач используется дискретное представление
времени. Однако недавние работы по нейронным обыкновенным дифференциальным уравнениям иллюстрируют возможность работать со скрытым состоянием рекуррентных нейронных сетей, как с решениями дифференциальных уравнений. Это позволяет рассматривать временные ряды как непрерывные по времени.
* __Данные__: Для классификации:
  * датасет P300, по которому писали статью
  * похожий на него по формату записей датасет DEAPdataset. 
  * Определение эмоций.
  * Тоже классификация эмоций SEED
  * Не ЭЭГ, но данные акселерометров с классификацией активности/положения
  * Для регрессии можно взять то же neurotycho, если хочется несколько усложнить жизнь относительно задач классификации.
* __Литература__: 
  * Neural Ordinary Differential Equations
  * Neural controlled differential equations for irregular time series
  * Latent ODEs for Irregularly-Sampled Time Series (?)
  * GRU-ODE-Bayes: Continuous modeling of sporadically-observed time series (?)
  * Neural Rough Differential Equations for Long Time Series (?)
  * ODE2VAE: Deep generative second order ODEs with Bayesian neural networks (?)
  * Go with the Flow: Adaptive Control for Neural ODEs
  * Legendre Memory Units: Continuous-Time Representation in Recurrent Neural Networks
  * Мой магистерский
* __Базовой алгоритм__: Алгоритм Алины Самохиной
* __Решение__: Использование вариаций  NeurODE для аппроксимации исходного сигнала. (Байес, частные производные, и т.д.). Сравнительный анализ существующих подходов к применению дифференциальных уравнений для классификации EEG
* __Новизна__: предлагается способ построения непрервыного представления сигнала. Работа с функциональным пространством сигнала, а не его дискретным представлением. Использование параметров полученной функции в качестве признакового пространства результирующей модели.
* __Авторы__: Алина Самохина, Вадим Стрижов

## Задача 104
* __Название__: (Ожидается уточнение) Кроссязычный поиск дубликатов
* __Задача__: Ставится задача кроссязычного поиска текстового плагиата. Поиск дубликатов оригинального текста осуществуляется среди текстов на 100 различных языках.
* __Данные__:
  * В качестве обучающей выборки используется выборка научных статей из научной электронной библиотеки eLIBRARY.ru, а так же статьи из онлайн-энциклопедии Wikipedia.
  * В качестве научных рубрикаторов рассматриваются Государственный рубрикатор научно-технической информации (ГРНТИ), Универсальный десятичный классификатор (УДК).
  * В качестве метрик качества поиска используются:
   * средняя частота – частота, усреднённая по контрольным языкам, с которой документ-запрос попадает в топ 10 % документов, среди которых осуществляется поиск
   * средний процент – процент документов, усреднённый по контрольным языкам, попавших в топ 10 % документов-переводов, которые имеют такую же научную рубрику, как документ-запрос
* __Литература__: Воронцов К. В. Вероятностное тематическое моделирование: обзор моделей и аддитивная регуляризация [http://www.machinelearning.ru/wiki/images/d/d5/Voron17survey-artm.pdf]
* __Базовые алгоритмы__:
  * Иерархические тематические модели
  * Тематические модели с однопроходной векторизацией документов
* __Решение__: Для решения задачи поиска была построена мультимодальная тематическая модель. В качестве модальностей использовались 100 языков, а также научные рубрики, к которым относились статьи из обучающих данных. Была проведена серия экспериментов по улучшению метрик качества поиска, в том числе: подбор оптимального способа токенизации, добавление регуляризаторов, подбор функций сравнения тематических векторов, функций ранжирования и др.
* __Новизна__: В основе большинства систем поиска документов в больших коллекциях лежит векторизация документов коллекции и поискового документа тем или иным способом. Новейшие на данный момент способы векторизации документов обычно ограничиваются одним языком. В таком случае возникает проблема создания единообразной системы получения векторных эмбедингов мультиязыковой коллекции документов. Предложенный подход позволяет обучить тематическую модель кодирующую информацию о распределениях слов в тексте безотносительно их языковой принадлежности. Также на решение действуют ограничения по размеру модели и времени обучения, обусловленные возможностью практического использования описываемой модели.
* __Автор__: Полина Потапова, Константин Воронцов

## Задача 52
* __Название__: (Ожидается уточнение) Предсказание качества моделей белков с помощью сферических сверток на трехмерных графах.
* __Задача__: Целью данной работы является создание и исследование новой операции свертки на трехмерных графах в рамках решения задачи оценивания качества трехмерных моделей белков (задача регрессии на узлах графа).
* __Данные__: Используются модели, сгенерированные участниками соревнований CASP (http://predictioncenter.org).
* __Литература__: 
  * [https://drive.google.com/file/d/1pXCED8XBcxbjwtg_1wZG0oAjvUCxFlua/view?usp=sharing] Подробно о задаче.
  * [https://arxiv.org/abs/1806.01261] Relational inductive biases, deep learning, and graph networks.
  * [https://arxiv.org/abs/1611.08097] Geometric deep learning: going beyond euclidean data.
* __Базовой алгоритм__: В качестве базового алгоритма будем использовать нейросеть, основанную на методе свертки на графах, который в общем виде описывается в [https://arxiv.org/abs/1806.01261].
* __Решение__: Наличие в белках пептидной цепи позволяет однозначно вводить локальные системы координат для всех узлов графа, что дает возможность создавать и применять сферические фильтры независимо от топологии графа.
* __Новизна__: В общем случае графы являются нерегулярными структурами, а во многих задачах обучения на графах объекты выборки не имеют единой топологии. Поэтому существующие операции сверток на графах очень сильно упрощены, либо не обобщаются на разные топологии. В данной работе предлагается рассмотреть новый способ построения операции свертки на трехмерных графах, для которых возможно однозначно выбрать локальные системы координат, привязанные к каждому узлу.
* __Автор__: Сергей Грудинин


## Задача 110 (техническая)
* __Название__: Обнаружение дефектов на кузове автомобиля 
* __Подзадачи__:  Классификация автомобилей по типам и марка, Классификация частей автомобиля (дверь, капот, крыша и тд), Сегментация дефектных участков на разных частях автомобиля, Классификация дефекта по типу (вмятина, царапина, повреждения стекла), Оценка степени повреждения, 
* __Для решения задачи можно использовать открытые датасеты__:
  * Coco Car Damage Detection Dataset – 70 фотографий поврежденных машин с рамками, семантической маской и типом повреждения (фара, передний бампер, капот, дверь, задний бампер)
  * Сar_damage – 920 фотографий поврежденных машин с размеченными масками
  * CarDent-Detection-Assessment – 100 фотографий поврежденных машин с размеченными масками
  * CarAccidentDataset – 52 фотографий поврежденных машин с размеченными масками
  * Car damage detection – 950 фотографий поврежденных и 1150 фотографий целых машин
  * Car Damage – 1512 фотографий поврежденных машин. Размечены для классификации вида повреждения
  * Cars Dataset – 16185 фотографий целых машин, 196 моделей. Изображения с разными ракурсами, метками и рамками элементов машины для сопоставления ракурсов.
* __Автор__: Андрей Инякин

## Задача 111 (техническая – Для сбора данных и разметки необходимо до 2-х недель)
* __Название__: Распознавание именованных сущностей в информационных русскоязычных новостях
* __Подзадачи__:  Оценка точности имеющихся моделей NER 
* __Разработка__ алгоритма насыщения (аугментации) обучающей выборки редкими именованными сущностями
* __Данные__: Для решения задачи будут подготовлены датасеты новостей из Интерфакс с разметкой именованных сущностей. 

# Шаблон описания научной статьи
## Задача 101
* __Название__: Название, под которым статья подается в журнал. 
* __Задача__: Описание или постановка задачи. Желательна постановка в виде задачи оптимизации (в формате argmin). Также возможна ссылка на классическую постановку задачи. 
* __Данные__: Краткое описание данных, используемых в вычислительном эксперименте, и ссылка на выборку. 
* __Литература__: Список научных работ, дополненный 1) формулировкой решаемой задачи, 2) ссылками на новые результаты, 3) основной информацией об исследуемой проблеме. 
* __Базовой алгоритм__: Ссылка на алгоритм, с которым проводится сравнение или на ближайшую по теме работу. 
* __Решение__: Предлагаемое решение задачи и способы проведения исследования. Способы представления и визуализации данных и проведения анализа ошибок, анализа качества алгоритма. 
* __Новизна__: Обоснование новизны и значимости идей (для редколлегии и рецензентов журнала). 
