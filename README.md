

Наша команда в течении 6 лет разрабатывает облачную медицинскую информационную систему
для соединенных штатов.

Сегодня я хотел рассказать о молодом, но многообещающем стандарте fhir.

Но вначале немного предистории.

Мы все с вами понимаем, что данные которые собирает и хранит система не принадлежат самой 
системе, а в рамках парадигмы patient-centric медицины, являются собственностью самого пациента.
Поэтому практически не избежно наши системы должны будут отдавать эти данные (другим системам или пациенту)
и принимать их. Важным аспектом передачи медицинской информации является то, что принимающая сторона
должна правильно их интерпретировать, те понять. Для этого наши системы должны говорить на одном общепонятном
языке.

Именно этими проблемами занимается международная организация HL7, которая разрабатывает стандарты для обмена
данными.


Исторически первым организацией HL7 был разработан стандарт обмена сообщениями - HL7 v2.
Это простой и практичный стандарт, который получил широкое распространение. Сейчас значительная 
часть систем, таких как лабораторные приборы и системы, фармакологические, административные и т.д, 
умеет говорить на языке HL7 v2.


Однако этот стандарт обладает рядом серьезных недостатков:

* в основе стандарта лежит жесткая и неявная модель сообщений и сегментов
* в стандарте предусмотрен лишь наивный способ расширения в виде сегментов общего назначения и каждая реализация использует их по разному
* с другой стороны стандарт не предусматривает штатного способа наложения более жестких ограничений на содержимое сообщений, что достаточно часто необходимо.

Из нашего опыта: мы много интегрировались с различными лабораторными, фармацевтическими и другими системами
и можем подтвердить, что эти проблемы реальны. 

Реализовав одну интеграцию, нам практически с нуля приходилось настраивать следующую. Постоянную и жгучую боль
вызывала агрегация данных из разных источников.

По этим причинам организация HL7 решила отправить стандарт версии 2 на поддержку и принятся за разработку стандарта нового поколеления, который как не удивительно был назван HL7 v3. Это было более 10 лет назад. Стандарт был призван учесть недостатки предыдущей версии. Для его разработки был даже стандартизован сам процесс разработки. Сам стандарт
из себя представляет целый пакет самостоятельных стандартов и рекомендаций, таких как референсная информационная модель, модели различных предметных областей, модели сообщений для этих предметных областей. 

Но к сожалению следует констатировать, что за эти 10 лет стандарт не достиг поставленной перед ним цели и не достиг планируемого распространения. Он оказался сложным и медленным в разработке. Можно сказать, что перемудрили.
Самой важной ошибкой было то, что стандарт практически не учитывал его реализуемость.

С этим столкнулись и мы, учавствовуюя в программе Abama Care и сертифицирую нашу систему. Одним из тербований сертификации была реализация импорта и экспорта саммари медицинской истории в формате CCD, который основан на стандартах HL7 v3 и родственном стандарте CDA (архитектура клинических документов).  В частности сложность реализации
этого пункта послужила одним из поводов срыва сроков развития программы, и следующий этап сертификации (по просьбе множества реализаторов систем) был отложен на один год.

Даже влиятельные члены коммисии разработки этого стандарта признают, что они оказались в некотором тупике.

По этому около двух лет назад HL7 принял под свое крыло молодой стандарт FHIR. Этот стандарт изначально был разработан австралийским экспертом Grahame Grieve.
Акроним FHIR раскрывается в фразу Fast Health Interoperable Resources - медицинские ресурсы для быстрго обмена информацией.

Новый стандарт призван взять лучшее из предыдущих версий - практичность от hl7 v2 и правильные концептуальные наработки из hl7 v 2.

Основной акцент в этом стандарте ставиться на простоту и легкость реализации и внедрения, что отражено в названии. 

Отличительной особенностью fhir является то, что этот стандарт распространяется под открытой лиценцией
Common Creative. Те вы свободно можете его использовать, распространять и адаптировать. Единственным требованием является сохранение ссылки на авторство. 

Сама спецификация находиться в публичном доступе по адрессу - http://www.hl7.org/implement/standards/fhir.

Мы также осуществили перевод стандарта на русский язык и поддерживаем его в актуальном состоянии, поскольку стандарт 
находится в активной разработке.

В основу стандарта положен набор принципов:

* фокус на реализацию
* поддержка основных стандартных сценариев из коробки
* в основу стандарта положены современные веб технологии
* открытость самого стандарта и прозрачность процесса его разработки
* сообщество заинтересованных профессионалов как неотъемлемая часть стандарта


Стандарт интенсивно развивается:

* Первая публикация была в 2011 году
* В 2012 году стандарт был принят в состав HL7
* В 2013 году выпущена первая версия для триального использования (DSTU), которую планируется финализировать к концу этого года
* В 2015 году планируется вторая версия
* а в 2016 первая нормативная


Коротко о структуре стандарта. 

Стандарт представлен одной спецификацией, которая доступна публично.
Технически стандарт описывает веб сервер реализующий REST интерфейс для доступа
к информационным ресурсам. Даже если вам не знакомо сокращение REST, то вы точно знакомы
с его использованием - поскольку на REST архитектуре реализована всемирная сеть или интернет.
И это тот же самый протокол по которому мы открываем в браузере сайты и web приложения.

В основе fhir лежит понятие ресурса. Ресурс представляет основную информационную единицу обмена
и содержит информацию о знакомых нам сущностях, таких как пациент, медикамент или аллергия.

В стандарте описано несколько десятков типов ресурсов, причем само описание тоже является ресурсом
с типом Profile (те данными). Ресурсы собраны в группы - административные, диагностические исследования и тп.

Каждый ресурс представляет собой иерархическую структуру состоящую из элементов. Каждый элемент содержит список
аттрибутов (полей).

В спецификации описаны операции доступа и манипуляции ресурсами. Например для поиска ресурсов типа Patient нужно обратиться по адресу  `https://server.com:/Patient/_search?name=Ivan`

Важной составляющей стандарта является спецификация работы со словарями и терминологиями. 
fhir (как и в hl7 v3) использует концепцию ValueSet, для создания перечесляемых наборов значений, которые можно
присвоить определенному полю определенного ресурса. При этом сами ValueSet в свою очередь тоже являются
ресурсами и работа с ними осуществляется по также как и с остальными данными.

By Design предпологается, что часто используемые ресурсы и аттрибуты включены в стандарт (правило 80%). 
Для хранения и обмена дополнительной информацией в стандарт заложен механизм расширения ресурсов, либо наложением дополнительных ограничений либо добавлением новых элементов и аттбибутов. 

Информация о расширениях распространяется как часть ресурсов Profile. Существует репозиторий расширений.

Как уже говорилось открытое сообщество заинтересованных профессионалов является неотъемлемой частью разработки стандарта. Обсуждения ведутся в комментариях, которые доступны прямо на страницах стандарта. Существует список рассылки и скайп чат, в которых несколько сотен инженеров, экспертов и членов комиссии ведут оживленные обсуждения.

Для верификации того, что стандарт движется в правильном направлении члены комиссии и сообщества ежемесячно устраивате так называемые конектотоны - где встречаются эксперты и разработчкики, выступают лидеры стандарта, и прямо на встречах реализуются и демонстрируются типовые сценарии.


Важной составляющей эко-системы fhir является создание открытых и свободных инструментов и решений на базе стандарта. Которые могут существенно ускорить и удешевить внедрение и использование.

Так доступны референсные реализации для популярных языков и платформ: java, C#, ObjectiveC, JavaScript
В открытом доступе развернуты тестовые сервера, для разработки и верефикации идей. Реализации основных серверов
свободно доступны.

Наша командо давно и активно учавствует в разработке стандарта и открытых средств для него.

Мы внесли свой вклад и разработали хранилище медицинских данных на основе стандарта fhir.
Это реляционно-документная база построенная поверх открытой базы PostgreSQL. 
Мы активно сотрудничаем с отечественной командой разработки Postgresql для того, чтобы сделать
ее надежной и быстрой. 
Это открытый и бесплатный проект, мы используем его в наших коммерческих
решениях и заинтересованны в его развитии. 
By Design значительная часть спецификации реализована внутри хранилища и может быть использована для разработки
медицинских систем на разных технологиях.

На основе медицинской базы fhirbase мы реализовали web сервер, соответсвующий станадрту fhir. Это тоже открытый
и бесплатный проект. В частности он используется как один из тестовых серверов при разработке стандарта.

Также в сотрудничестве со Smart Platform мы разрабатываем референсную библиотеку для javacript, которая  позволит
легко создавать web интерфейсы для луюбых соответсвующих стандарту серверов.

На наш взгля за fhir будущее медицинских стандартов. И это мнение многих авторитетных экспертов из организации HL7.

На этой конференции мы слышали много про региональные и центральные шины обмена информацией, про личные кабинеты пациента. Это как раз целевые обасти fhir. И мы надеемся, что этот многообещающий стандарт получит должное признание и распространение в России. И готовы этому способствовать. Если у вас есть вопросы про стандарт или наши open source решения то мы доступны в кулуарах.
