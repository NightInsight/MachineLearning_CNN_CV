# MachineLearning_CNN_CV
Обучение сверточной нейронной сети (CNN) для классификации изображений из набора данных CIFAR-10 с аугментацией, визуализацией результатов, динамическое управление скоростью обучения и предотвращение переобучения.

Пошаговый порядок работы:
1.Импорт библиотек и настройка TensorFlow:
  Импортируется модуль os для работы с операционной системой.
  Устанавливаются переменные окружения для конфигурации TensorFlow, отключающие оптимизации oneDNN и уменьшающие количество логов.
  Импортируются необходимые библиотеки для работы с изображениями, нейронными сетями, включая TensorFlow и его высокоуровневый API Keras.

2.Загрузка и нормализация данных CIFAR-10:
  Данные CIFAR-10 загружаются и разделяются на обучающую и тестовую выборки.
  Изображения нормализуются путём деления каждого пикселя на 255 для приведения значений в диапазон от 0 до 1.

3.Отображение набора данных:
  Выводятся первые 25 изображений из обучающей выборки с названиями классов, к которым они принадлежат.

4.Аугментация данных:
  Описана функция для случайного отражения изображений по горизонтали.
  Создаются датасеты для обучения и тестирования с применением аугментации и пакетной обработки (batch processing).

5.Загрузка или создание новой модели CNN:
  Если модель с заданным именем существует, она загружается. В противном случае создаётся новая модель со свёрточными слоями, слоями пулинга, слоями dropout для предотвращения переобучения и полносвязными слоями.

6.Компиляция модели:
  Модель компилируется с использованием оптимизатора Adam, функции потерь для классификации и метрики точности.

7.Аугментация данных с помощью ImageDataGenerator:
  Настройка генератора данных для автоматической аугментации в процессе обучения (вращение, сдвиги, увеличение/уменьшение и т.д.).

8.Обучение модели:
  Модель обучается на аугментированных данных с использованием коллбеков для динамического изменения скорости обучения и ранней остановки обучения при отсутствии улучшения результатов на валидационной выборке.

9.Оценка модели и сохранение:
  Построение графиков точности на обучающем и валидационном наборах.
  Оценка точности модели на тестовом наборе данных.
  Сохранение обученной модели для дальнейшего использования.
