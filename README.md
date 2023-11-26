# Neural-networks-in-image-processing-hw1

## Работа Горохова Сергея 402

Для реализации поставленной задачи использовалась сеть alexnet с преобученными весами (#LBL6). В ней был изменен модуль классификатора на 2 линейных слоя, для упрощения структуры сети.

Получена точность на датасете test:
metrics for test:
	 accuracy 0.9542:
	 balanced accuracy 0.9542:

Из дополнительных критериев реализовано:
 * Автоматическое сохранение лучших весов сети во время обучения (на случай переобучения в конце процесса) (#LBL1)
 * Автоматическая валидация на тестовом датасете (test_tiny) после кжадой эпохи обучения (#LBL2)
 * Логирование точности, и значений функции потерь во время обучения (#LBL5)
 * График значений функции потерь на test и train датасетах (#LBL3)
 * Есть возможность дообучить есть, загрузив ее и снова вызвав метод train(), передав туда нужный датасет.
 * Добавлены аугментации для расширения обучающего датасета (#LBL4)
 * Автоматическое уменьшение learning_rate в течение обучения (#LBL7)

## Замечание
Был изменен класс Dataset на ImgDataset в связи с тем, что google drive выдавал ошибку при попытке скачать файлы с датасетами из Collab'а, поэтому пришлось скачать их себе на компьютер, выгрузить в облако и переопредилить их скачивание внутри ноутбука на собственный Google Диск.
Также было добавлено наследование от класса Dataset из torch и 2 внутренних метода для него, чтобы удобно реализовать работу с DataLoader.
