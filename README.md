# README

[Описание задачи](https://docs.google.com/document/d/174KhzX4EVqHIJV6GiWskP1KkhYUS_JeJa8WS6tgIwYY/edit#heading=h.sj9glk599oik)  


ПРОТОКОЛ ИСПЫТАНИЙ МОДЕЛЕЙ  
|Предобработка| Модель | Гиперпараметры | Временной интервал | ts_diff max | Метрика f1_weighed | 
|-------------|--------|---------------|---------------------|-------------|--------------------|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |LogisticRegression | max_iter = 1000, solver = 'saga', class_weight = class_weights, random_state = 42|10|0.036 |0.79|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |LogisticRegression | max_iter = 1000, solver = 'saga', class_weight = class_weights, random_state = 42|50|0.01 |0.76|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |CatBoostClassifier |depth=6,iterations=282,learning_rate = 0.412,l2_leaf_reg = 2,bootstrap_type = 'Bayesian',loss_function='MultiClass', class_weights=class_weights)|10|0.012 |0.77|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |CatBoostClassifier |depth=6,iterations=282,learning_rate = 0.412,l2_leaf_reg = 2,bootstrap_type = 'Bayesian',loss_function='MultiClass', class_weights=class_weights)|50|0.02 |0.79|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |CatBoostClassifier |depth=6,iterations=282,learning_rate = 0.412,l2_leaf_reg = 2,bootstrap_type = 'Bayesian',loss_function='MultiClass', class_weights=class_weights)|1000|0.189 |0.73|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |MultinomialNB |Default|10|0.903 |0.39|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |MultinomialNB |Default|50|0.031 |0.40|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |MultinomialNB |Default|100|0.038 |0.41|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |KNeighborsClassifier |n_neighbors=3, n_jobs = -1, algorithm = 'kd_tree', weights = 'distance'|10|0.229 |0.50|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |KNeighborsClassifier |n_neighbors=3, n_jobs = -1, algorithm = 'kd_tree', weights = 'distance'|50|0.316 |0.50|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |KNeighborsClassifier |n_neighbors=10, n_jobs = -1, algorithm = 'kd_tree', weights = 'distance'|50|0.225 |0.50|
