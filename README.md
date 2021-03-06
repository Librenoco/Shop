# Описание:
Данный репозиторий является проектной работой учащихся школы Eltex по направлению "Embedded C"

Учащиеся, принимавшие участие в работе над проектом:
  
  - [KushchenkoMaksim](https://github.com/KushchenkoMaksim);

  - Warnet/[Librenoco](https://github.com/Librenoco); (Разрабатывал функционал для работы с json файлами в данном проекте)

  - Volkov Yury/[VolkovYury](https://github.com/VolkovYury);

# Техническое задание: 
  
## Разработка модели работы сети торговых терминалов
  
Разработать клиент и сервер для моделирования взаимодействия торгового терминала с сервером, разработать протокол для их взаимодействия.
  
Сервер при старте считывает из json карточки доступных товаров (описание, цена, доступное количество). Клиенты подключаются к серверу и синхронизируют эти данные. В клиенте предусмотреть минимальный консольный интерфейс для просмотра карточек и условной покупки (далее транзакции). При получении транзакции в консольном интерфейсе клиент отправляет ее на сервер, сервер изменяет количество доступных единиц этого товара и рассылает эту транзакцию всем клиентам, чтобы все терминалы поддерживали карточки в актуальном состоянии. Усложнение - клиенты могут иметь разный набор товаров в пределах доступного серверу.
  
## Общие требования:
  
- сборка cmake;
  
- взаимодействие между клиентами и сервером через inet сокеты;
  
- хранение актуального состояния карточек товаров в файле в json.

## Требования к клиенту:
  
- консольный интерфейс для возможности покупки, просмотра состояния "склада";
  
- усложнение - для просмотра каждой карточки товара отдельно.

## Требования к серверу:
  
- соединение с каждым из терминалов обслуживается отдельным потоком;
    
- консольный интерфейс для просмотра информации о состоянии "склада", количестве торговых точек;
  
- усложнение - для просмотра каждой карточки товара и изменении их состояния;
  
- усложнение - поддержать работу клиента в оффлайн режиме с записью транзакций в json, которые будут отправлены на сервер при следующем обычном подключении.
