# Требования к проекту
---

# Содержание
1 [Введение](#intro)  
1.1 [Назначение](#appointment)  
1.2 [Бизнес-требования](#business_requirements)  
1.2.1 [Исходные данные](#initial_data)  
1.2.2 [Возможности бизнеса](#business_opportunities)  
1.2.3 [Границы проекта](#project_boundary)  
1.3 [Аналоги](#analogues)  
2 [Требования пользователя](#user_requirements)  
2.1 [Программные интерфейсы](#software_interfaces)  
2.2 [Интерфейс пользователя](#user_interface)  
2.3 [Характеристики пользователей](#user_specifications)  
2.3.1 [Классы пользователей](#user_classes)  
2.3.2 [Аудитория приложения](#application_audience)  
2.3.2.1 [Целевая аудитория](#target_audience)  
2.3.2.1 [Побочная аудитория](#collateral_audience)  
2.4 [Предположения и зависимости](#assumptions_and_dependencies)  
3 [Системные требования](#system_requirements)  
3.1 [Функциональные требования](#functional_requirements)  
3.1.1 [Основные функции](#main_functions)  
3.1.1.1 [Вход пользователя в приложение](#user_logon_to_the_application)  
3.1.1.2 [Настройка профиля активного пользователя](#setting_up_the_profile_of_the_active_user)  
3.1.1.3 [Загрузка новостей](#download_news)  
3.1.1.4 [Просмотр информации об отдельной новости](#view_information_about_an_individual_newsletter)  
3.1.1.5 [Выход пользователя из учётной записи](#active_user_change)  
3.1.1.6 [Регистрация нового пользователя после входа в приложение](#add_new_user)  
3.1.2 [Ограничения и исключения](#restrictions_and_exclusions)  
3.2 [Нефункциональные требования](#non-functional_requirements)  
3.2.1 [Атрибуты качества](#quality_attributes)  
3.2.1.1 [Требования к удобству использования](#requirements_for_ease_of_use)  
3.2.1.2 [Требования к безопасности](#security_requirements)  
3.2.2 [Внешние интерфейсы](#external_interfaces)  
3.2.3 [Ограничения](#restrictions)  

<a name="intro"/>

# 1 Введение

<a name="appointment"/>

## 1.1 Назначение
Документ разработан для однозначной трактовки требований между разработчиком и заказчиком. Необходимо разработать мобильное приложение с простым функционалом и актуальной инфомацией о ценах на валюты. Необходимо, чтобы приложение именло главную страницу с основными данными по ценам на покупку/продажу валют, выбор банка, выбор валюты, в которой выводятся цены на гланой странице( перыоначатьная валюта - Белорусский рубль). Вторая страница - разворот с картой выбранного пользователем города, на карте меткой (круг, точка(по выбору заказчика)) обозначены отделения выбранного банка или же оделения всех доступных приложению банков(или только один, или все). На данной странице необходимо реализовать поиск необходимого города и выбор необходимого банка. Дла работы приложения требуется стабильное Интернет соединение, а так же подключенная геолокация.   
В этом документе описаны функциональные и нефункциональные требования к мобильному приложению «Сurrency exchange» для Android, IOS. 
Этот документ предназначен для команды, которая будет реализовывать и проверять корректность работы приложения. 

<a name="business_requirements"/>

## 1.2 Бизнес-требования

<a name="initial_data"/>

### 1.2.1 Исходные данные
В настоящее время у большинства людей есть необходимость покупки и продажи иностранной валюты, в связи с чем появляется необходимость в постоянном слежении за курсом валют. В официальных мобильных приложениях банков всегда есть вкладка либо окно с актуальными ценами на валюту установленными соответствующим банком. Но для сравнения курса по нескольким банкам необходимо либо открыть несколько различных приложений мобильного банкинга, либо искать необходимый сайт посредством сети Интернет. Невозможность просмотра и сравнения цен на валюту в одном приложении, а так же необходимость после обнаружения необходимого банка искать его адрес в отдельном приложении приводит к большим временным потерям для пользователей. 

<a name="business_opportunities"/>

### 1.2.2 Возможности бизнеса
На сегодняшний день 9,2% из 8000 опрошенных клиентов банков пользуются услугами мобильного банка, 7,4% используют интернет-банкинг. При этом 70,5% из этого числа никогда не совершали интернет-платежей, следовательно эти 70,5% людей возможно предпочтут использовать приложение, которое позволит быстро получать актуальную информацию о курсе валют, сравнивать цены из разных банков, а так же смотреть по картам адрес ближайшего отделения интересующего банка. Подобное приложение позволит им тратить меньше времени на поиск необходимой информации. Интерфейс, спроектированный с учётом всех требований, и постоянное обновление информации позволят увеличить количество людей, использующих данное приложение.

<a name="project_boundary"/>

### 1.2.3 Границы проекта
Приложение не требует регистрации.
Приложение «Watch & buy» позволит пользователям просматривать информацию о интересующей валют(цена для покупки/продажи), смотреть информацию по нескольким(не более 5) валютам одновременно. При необходимости просмотра курса относительно новой валюты(не белорусского рубля) необходимо реализовать выбор другой валюты. Так же есть возможность сохранения 1 основного банка для первоначального просмотра информации по  курсу при старте приложения. Необходимо так же реализовать возможность добавления виджета на рабочий экран смартфона. Виджет должен содержать информацию о курсе выбранных пользователем валют( не более 3)с привязкой к одному банку(банк и валюта(ы) выбирается пользователем при создании виджета). Реализовать возможность создания виджета как из самого приложения, так и через список виджетов смартфона. 
Возможность открытия карты выбранного города(город выбирается непосредственно на вкладке с картами, предыдущий выбор сохраняется и меняется пользователем в случае необходимости)для просмотра адресов отделений банков(можно смотреть как все доступные в приложении банки, так и один отдельный банк(либо все, либо только один!)).


<a name="analogues"/>

## 1.3 Аналоги
MyFin.by - Курсы валют и банки(вес 11 мб, встроенный конвертер, выбор валюты и котировки ресурсов, карты отделений, курс валют в реальном времени с выводом на карте) 
Курс валют - валюта и другое(вес 5.3 мб, встроенный конвертер, выбор валюты и котировки ресурсов)

В отличие от MyFin.by описываемое приложение не отображает информацию  курсе валюты в реальном времени на карте, так же нет встроенного конвертера валют, но описываемое приложение предположительно будет иметь меньший вес и не нагружено лишним функционалом.

В отличие от "Курс валют - валюта и другое" описываемое приложение не имеет встроенного конвертера валют, но у описываемого приложения есть возможность просмотра банков на карте(определение адресов) и возможность просмотра графика работы выбранного отделения.

<a name="user_requirements"/>

# 2 Требования пользователя

<a name="software_interfaces"/>

## 2.1 Программные интерфейсы
Продукт должен являться мобильным приложением и иметь user-friendly оформление. Front-end часть должна быть создана средствами HTML/CSS и React JS. Серверная часть должна быть написана на Python-фреймворке Django.

<a name="user_interface"/>

## 2.2 Интерфейс пользователя
Стартовое окно приложения.

![Стартовое окно приложения](https://github.com/NAsQuk/TRITPO_LAB2/blob/main/mockups/StartScreen.png)  
Главное окно приложения.  
![Главное окно приложения](https://github.com/NAsQuk/TRITPO_LAB2/blob/main/mockups/MainWindow1.png)  
Окно карт в приложении  
![Окно карт в приложении ](https://github.com/NAsQuk/TRITPO_LAB2/blob/main/mockups/Maps.png)  
Главное окно приложения после выбора новости в таблице (пользователь зарегестрирован).  
Wiget приложения  
![Wiget приложения ](https://github.com/NAsQuk/TRITPO_LAB2/blob/main/mockups/Wiget.png)
<a name="user_specifications"/>

## 2.3 Характеристики пользователей

<a name="user_classes"/>

### 2.3.1 Классы пользователей

Приложение не требует регистрации, все пользователи в равных условиях

<a name="application_audience"/>

### 2.3.2 Аудитория приложения

<a name="target_audience"/>

#### 2.3.2.1 Целевая аудитория
Люди старше 18 лет

<a name="collateral_audience"/>

#### 2.3.2.2 Побочная аудитория
Люди младше 18 лет.

<a name="assumptions_and_dependencies"/>

## 2.4 Предположения и зависимости
1. Приложение не работает при отсутствии подключения к Интернету;
2. Просмотр отделений банков на карте невозможен при отключенной геолокации.

<a name="system_requirements"/>

# 3 Системные требования

<a name="functional_requirements"/>

## 3.1 Функциональные требования

<a name="main_functions"/>

### 3.1.1 Основные функции

<a name="user_logon_to_the_application"/>


#### 3.1.1.1 Загрузка цен на валюту
**Описание.** После запуска приложения на экране

| Функция | Требования | 
|:---|:---|
| Загрузка информации о цене валют(ы)запуска приложения | Приложение должно загрузить информацию о цене(купли/продажи) валюты, после запуска приложения пользователем |
| Загрузка информации о цене валют(ы) после выставления пользователем определенных критериев| Приложение должно вывести на экран отсортированные данные(по возрастанию/убыванию) по ценам на одну или более валют(не более 3) с выводом названия соответствующих банков |

<a name="restrictions_and_exclusions"/>

### 3.1.2 Ограничения и исключения
1. Приложение работает только при наличии подключения к Интернету;
2. Просмотр отделений банков на карте возможен только при включенной геолокации.

<a name="non-functional_requirements"/>

## 3.2 Нефункциональные требования

<a name="quality_attributes"/>

### 3.2.1 Атрибуты качества

<a name="requirements_for_ease_of_use"/>

#### 3.2.1.1 Требования к удобству использования
1. Доступ к основным функциям приложения не более чем за две операции;
2. Все функциональные элементы пользовательского интерфейса имеют названия, описывающие действие, которое произойдет при выборе элемента;
3. Обновление информации о новостях происходит 4 раза в сутки( 00.00,06.00,12.00,18.00) в фоновом режиме.

<a name="security_requirements"/>

#### 3.2.1.2 Требования к безопасности
Приложение не хранит личные данные пользователя, следовательно не нуждается в защите персональных данных.

<a name="external_interfaces"/>

### 3.2.2 Внешние интерфейсы
  * размер шрифта не менее 12пт;
  * функциональные элементы контрастны фону окна.

<a name="restrictions"/>

### 3.2.3 Ограничения
1. Дизайн должен соответствовать пункту интерфейс пользователя.
