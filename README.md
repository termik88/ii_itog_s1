# Final work (Diagnosis of the incidence of Pneumonia II st. according to the results of fluorography)
## Диагностика заболеваемости Пневмонией II ст. по результатам флюрографии 


## Authors (group 15 saturday 28.01.23)
[@termik88](https://github.com/termik88): Илья Колосов

## [Link to StreamLid Cloud](https://termik88-ii-itog-s1-streamlit-app-r1ykkj.streamlit.app/)

## Описание модели

Идея для данной модели была взята с одной из рассматриваемых задачь с Хакатона. ДатаСетом для модели(Нейросетки) служит дата сет рентгеновских снимков и мед. учереждения Гуанжоу: [Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)

Структура сети была обучена, сохранена и изъята с [Kaggle](https://www.kaggle.com/)

Структура сетки:

    keras.layers.Conv2D(32, (3,3), activation="relu", input_shape=(32,32,1)),
    keras.layers.MaxPool2D(pool_size=(2,2)),
    keras.layers.Conv2D(64, (3,3), activation="relu"),
    keras.layers.MaxPool2D(pool_size=(2,2)),
    keras.layers.Flatten(),
    keras.layers.Dense(1024, activation="relu"),
    keras.layers.Dense(200,activation="relu"),
    keras.layers.Dense(3,activation="softmax")

Итогом работы модели является три показателя, пример:

- Отрицательный анализ: 99.21 %

- Бактериальная пневмония: 0.79 %

- Вирус пневмонии: 0.0 %

Данные показатели являются выходными значениями нейронов сетки.

Тесты работаю, только Если стримлид на локальной Машине, если в облаке просто НИИИИИИ в какую.

## Небольщая справка. Чем отличается бактериальная пневмония от вирусной?

При бактериальной пневмонии поражаются именно альвеолы — они воспаляются и отекают, в них скапливается жидкость (экссудат), которая в последующем нагнаивается, мы начинаем кашлять, применяем муколитические средства для разжижения и более легкого отхождения мокроты. Экссудат задерживает прохождение кислорода в кровеносное русло, возникает кислородная недостаточность, снижается сатурация (насыщение крови кислородом). Цель лечения в этом случае — избавление от мокроты путем воздействия на возбудителя, чаще всего пневмококк. Поэтому бактериальная пневмония лечится антибиотиками.


При вирусной пневмонии картина совсем иная. В альвеолах жидкость не скапливается и не нагнаивается. Поэтому кашля с отделяемой мокротой при ковиде нет и быть не может. Вирус поражает стенки сосудов, где происходит газообмен, появляется отек стенок сосудов, сосуды сужаются. Это приводит к замедлению циркуляции крови. Эритроциты «слипаются», препятствуя газообмену, возникает острая нехватка кислорода. Лечить антибиотиками вирусную инфекцию до присоединения к ней бактериальной бесполезно! 