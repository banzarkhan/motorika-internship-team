# README

[Описание задачи](https://docs.google.com/document/d/174KhzX4EVqHIJV6GiWskP1KkhYUS_JeJa8WS6tgIwYY/edit#heading=h.sj9glk599oik)  


ПРОТОКОЛ ИСПЫТАНИЙ СИСТЕМЫ ПРИНЯТИЯ РЕШЕНИЙ 
|Предобработка| Модель | Гиперпараметры | Временной интервал | ts_diff max | Метрика f1_weighed | 
|-------------|--------|---------------|---------------------|-------------|--------------------|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |LogisticRegression | max_iter = 1000, solver = 'saga', class_weight = class_weights, random_state = 42|10|0.036 |0.79|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |LogisticRegression | max_iter = 1000, solver = 'saga', class_weight = class_weights, random_state = 42|50|0.01 |0.76|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |CatBoostClassifier |depth=6,iterations=282,learning_rate = 0.412,l2_leaf_reg = 2,bootstrap_type = 'Bayesian',loss_function='MultiClass', class_weights=class_weights)|10|0.012 |0.77|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |CatBoostClassifier |depth=6,iterations=282,learning_rate = 0.412,l2_leaf_reg = 2,bootstrap_type = 'Bayesian',loss_function='MultiClass', class_weights=class_weights)|50|0.02 |0.79|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |CatBoostClassifier |depth=6,iterations=282,learning_rate = 0.412,l2_leaf_reg = 2,bootstrap_type = 'Bayesian',loss_function='MultiClass', class_weights=class_weights)|1000|0.189 |0.73|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2, MinMaxScalar |MultinomialNB |Default|10|0.044 |0.57|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |MultinomialNB |Default|100|0.012 |0.58|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |KNeighborsClassifier |n_neighbors=3, n_jobs = -1, algorithm = 'kd_tree', weights = 'distance'|10|0.372 |0.75|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |KNeighborsClassifier |n_neighbors=3, n_jobs = -1, algorithm = 'ball_tree', weights = 'uniform'|20|0.551 |0.75|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |SVC|kernel='rbf', gamma='scale', C=10000, break_ties=True, decision_function_shape='ovr', max_iter = -1|20|0.2|0.83|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |SVC|kernel='rbf', gamma='scale', C=1000, break_ties=True, decision_function_shape='ovr', max_iter = -1|10|0.027|0.84|  

ПРОТОКОЛ ИСПЫТАНИЯ СИСТЕМЫ ПРИНЯТИЯ РЕШЕНИЙ С ОТДЕЛЬНОЙ МОДЕЛЬЮ ПРЕДСКАЗАНИЯ ЖЕСТА THUMB  

|Предобработка| Модель | Гиперпараметры | Временной интервал | ts_diff max | Метрика f1_weighed | 
|-------------|--------|---------------|---------------------|-------------|--------------------|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |SVC+SVC|(kernel='rbf', gamma='scale', C=1000, break_ties=True, decision_function_shape='ovr', max_iter = -1)  Модель предсказания Thumb(kernel='rbf', gamma='auto', C=0.1, break_ties=False, class_weight = class_weights, decision_function_shape='ovo')|10|0.253|0.81
