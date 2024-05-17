# MachineLearning_CNN_CV
 ML_CNN - это скрипт для машинного обучения и создания сверточной нейронной сети (CNN), состоящей из 16 слоев, для классификации изображений из набора данных CIFAR-10 с аугментацией, визуализацией результатов, динамическое управление скоростью обучения и предотвращение переобучения.
 Точность созданной модели 85% за 40 эпох обучения. На выходе она имеет более 1600000 параметров и 550000 из них обучаемые.
 
![Screenshot_status](https://github.com/NightInsight/MachineLearning_CNN_CV/assets/113856600/8031eef1-d0a8-4018-a5e5-414347ecd007)

 Для работы скрипта надо установить следующие библиотеки:
  
  pip install tensorflow matplotlib
 
 Пошаговый порядок работы ML_CNN:
  1) Импорт библиотек и настройка TensorFlow:
     - Импортируется модуль os для работы с операционной системой;
     - Устанавливаются переменные окружения для конфигурации TensorFlow, отключающие оптимизации oneDNN и уменьшающие количество логов;
     - Импортируются необходимые библиотеки для работы с изображениями, нейронными сетями, включая TensorFlow и его высокоуровневый API Keras.
  2) Загрузка и нормализация данных CIFAR-10:
     - Данные CIFAR-10 загружаются и разделяются на обучающую и тестовую выборки;
     - Изображения нормализуются путем деления каждого пикселя на 255 для приведения значений в диапазон от 0 до 1.
  3) Отображение набора данных:
     - Выводятся первые 25 изображений из обучающей выборки с названиями классов, к которым они принадлежат;
  4) Аугментация данных:
     - Описана функция для случайного отражения изображений по горизонтали;
     - Создаются датасеты для обучения и тестирования с применением аугментации и пакетной обработки (batch processing).
  5) Загрузка или создание новой модели CNN:
     - Если модель с заданным именем существует, она загружается. В противном случае создается новая модель со сверточными слоями, слоями пулинга, слоями dropout для предотвращения переобучения и полносвязными слоями.
  6) Компиляция модели:
     - Модель компилируется с использованием оптимизатора Adam, функции потерь для классификации и метрики точности.
  7) Аугментация данных с помощью генератора данных:
     - Настройка генератора данных для автоматической аугментации в процессе обучения (вращение, сдвиги, увеличение/уменьшение и т.д.).
  8) Обучение модели:
     - Модель обучается на аугментированных данных с использованием коллбеков для динамического изменения скорости обучения и ранней остановки обучения при отсутствии улучшения результатов на валидационной выборке.
  9) Оценка модели и ее сохранение:
     - Построение графиков точности на обучающем и валидационном наборах;
     - Оценка точности модели на тестовом наборе данных;
     - Сохранение обученной модели для дальнейшего использования.

 После обучения и сохранения модели вы можете использовать ее для предсказания классов новых изображений, загружая модель и передавая ей изображения для классификации.
 Вот несколько примеров, как можно использовать эту модель:
  1) Разработка мобильного приложения для классификации объектов в реальном времени:
     - Используйте фреймворки, такие как TensorFlow Lite, для конвертации и внедрения модели в мобильное приложение;
     - Далее создайте UI, который позволяет пользователям делать снимки или загружать изображения для классификации;
     - Реализуйте функцию, которая подготавливает пользовательские изображения (масштабирование до 32x32 пикселей, нормализация) перед подачей их в модель;
     - После чего отобразите наименование класса с наивысшей вероятностью, предсказанное моделью, пользователю.
  2) Автоматизация каталогизации изображений на веб-сервере:
     - Интегрируйте модель с веб-сервером, используя фреймворки, такие как Flask или Django для Python;
     - Создайте API-эндпоинт, который позволяет пользователям загружать изображения для классификации;
     - Разработайте логику для обработки загруженных изображений и их классификации с помощью модели;
     - Автоматически каталогизируйте изображения на сервере на основе полученных классификаций, облегчая поиск и организацию данных.
  3) Распознавание объектов на производственной линии АСУ ТП:
     - Разработайте систему для подключения модели к камерам, установленным на производственной линии.
     - Настройте систему для обработки изображений с камер в реальном времени для идентификации и классификации объектов;
     - Используйте результаты классификации для автоматической проверки качества продукции, выявления брака или неправильной комплектации;
     - На основе классификации реализуйте логику для автоматической сортировки продукции, например, отклонение некачественных изделий.
  4) Улучшение для систем видеонаблюдения:
     - Внедрите модель в систему видеонаблюдения для анализа видеопотока в реальном времени или обработки архивных записей;
     - Реализуйте функционал для выделения и обрезки объектов из видеопотока, чтобы подавать их на вход модели для классификации;
     - Настройте систему таким образом, чтобы при обнаружении определенных объектов (например, автомобилей или людей) выполнялись специфические действия, такие как отправка уведомлений или активация записи;
     - Сохраняйте результаты классификации для последующего анализа, что может быть полезно как улучшение безопасности или бизнес-аналитики.
