# README

[Описание задачи](https://docs.google.com/document/d/174KhzX4EVqHIJV6GiWskP1KkhYUS_JeJa8WS6tgIwYY/edit#heading=h.sj9glk599oik)  


ПРОТОКОЛ ИСПЫТАНИЙ МОДЕЛЕЙ  
|Предобработка| Модель | Гиперпараметры | Временной интервал | ts_diff max | Метрика f1_weighed | 
|-------------|--------|---------------|---------------------|-------------|--------------------|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |LogisticRegression | max_iter = 1000, solver = 'saga', class_weight = class_weights, random_state = 42|10|0.011 |0.30|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |LogisticRegression | max_iter = 1000, solver = 'saga', class_weight = class_weights, random_state = 42|50|0.013 |0.31|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |CatBoostClassifier |depth=6,iterations=282,learning_rate = 0.412,l2_leaf_reg = 2,bootstrap_type = 'Bayesian',loss_function='MultiClass', class_weights=class_weights)|10|0.016 |0.02|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |CatBoostClassifier |depth=6,iterations=282,learning_rate = 0.412,l2_leaf_reg = 2,bootstrap_type = 'Bayesian',loss_function='MultiClass', class_weights=class_weights)|100|0.019 |0.01|
| Экспоненциально взвешенные скользящие средние,Сумма изменений признака за последние 5 временных шагов, Cдвиг признаков с лагом 3 и шагом 2 |CatBoostClassifier |depth=6,iterations=282,learning_rate = 0.412,l2_leaf_reg = 2,bootstrap_type = 'Bayesian',loss_function='MultiClass', class_weights=class_weights)|1000|0.526 |0.01|

