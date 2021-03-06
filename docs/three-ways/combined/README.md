# Комбинированная разработка

Комбинированный вариант разработки, подразумевает использование составляющих WebTutor совместно со сторонними составляющими. То есть в данном случае вы используете только часть инструментов WebTutor.

Рассмотрим применение комбинированной разработки на примерах:

#### 1) Замена серверной составляющей
Допустим вы столкнулись с ограничениями серверного JavaScript WebTutor и реализовать задуманное вами на нем невозможно. 

Для обхода ограничений, вы пишите вашу серверную часть не в WebTutor, а на другом сервере. К примеру на том же сервере на котором установлен WebTutor вы устанавливаете Node.js и запускате http-сервер и на нем уже реализуете всю серверную часть. При необходимости открываете порты и взаимодействуете из браузера напрямую с Node.js или осуществляете взаимодействие сервера WebTutor с Node.js итп.

Не обязательно использовать Node.js, на свое усмотрение вы можете использовать любой сервер и близкий вам язык (PHP, Go, Python...) и его модули.

Если у вас нет возможности развернуть полноценный сервер(к примеру IT подразделения не дают вам доступы и не разрешают ничего устанавливать), используйте облачные сервисы для выполнения вашего кода удаленно (к примеру [Google Cloud Functions](https://cloud.google.com/functions/)).

#### 2) Замена клиентской составляющей
Допустим вас устраивает серверная часть, но не устраивают интерфейсы, которые предоставляет библиотека Ext JS в WebTutor. 

Просто подключаете свою библиотеку и используете ее. Главное не забывать про инкапсуляцию стилей и скриптов. Для инкапсуляции используйте веб-компоненты или заключайте ваши разработки в iframe, чтобы внешнее окружение(стили, скрипты) не влияло на ваши разработки.

Рассмотрим положительные и отрицательные стороны подобного вида разработки.

#### 3) Замена базы данных
Допустим у вас стоит задача, реализовать интерфейс, который отображает какие-то данные и автоматически обновляет их в браузере(обновляет только при изменениях в базе данных), без обновления страницы. То есть надо реализовать [Real-time Database](https://en.wikipedia.org/wiki/Real-time_database) в WebTutor.

Чтобы не тратить время на то, что и так уже многими написано, вы ищите в интернете готовый сервис предоставляющий данный функционал и используете его. Храните и обрабатываете данные на стороне данного сервиса и чтобы перестраховаться осуществляете периодический бэкап данных.

### Плюсы

* отсутствие ограничений в разработке
* возможность использования современных технологий при разработке
* экономия времени за счет использования готовых модулей
* легче найти специалиста для подобной разработки (в случаях когда не используется серверный JavaScript WebTutor)

### Минусы

* потребуется взаимодействие с IT подразделениями(разрешение установки стороннего ПО на сервере WebTutor, открытие портов итп)
* поддержка WebSoft врятли(бесплатно) поможет при возникновении проблем с подобными разработками
* тяжело найти специалиста для подобной разработки, в случаях когда используются все составляющие WebTutor + внешние составляющие
* в определенных ситуациях есть зависимость от разработчиков WebSoft, в случаях внесения изменений в составляющие, которые вы использовали при разработке