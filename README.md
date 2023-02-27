# lepta
Лабораторная работа №1

Проектирование системы

Тема: волонтёрское движение «Лепта»	Ф.И.О.	Полешко Ратибор Андреевич
	Группа	ИВТ-363
	Преподаватель	Гаис Аль-Мерри
	Дата сдачи	

Команда: Полешко Ратибор, Орлов Никита, Козякин Андрей
Описание проекта и предметной области:
 
1 Идём на задание

Аннотация движения:
«Братья и сестры из "Лепты" —  это команда неравнодушных христиан, которые пытаются немного скрасить будни тех, кто нуждается в поддержке, привнеся в них радость, светлую радость о Боге и надежду на Него. Так случилось, что мы обнаружили в себе талант, которым владеем, и решили именно им послужить Богу и людям. Наше волонтерство и миссия опосредованы музыкой, поэтому взаимно отрадны и слушателям, и нам самим. Ежемесячно мы собираемся, чтобы прийти или в хоспис, или в интернат. Есть также мастерская "Конкордия", где добрые мастера помогают подготовиться к ярмарке. Периодически, участвуя в ярмарках, мы собираем средства на помощь хоспису и интернату, и другие дела благотворительности. С хосписом мы сотрудничаем около пяти лет. Хоспис — это чаще всего последнее пристанище для тяжело больных людей. Интернат — это пристанище для пожилых, которые нуждаются в медицинском уходе, и инвалидов, за которыми некому или тяжело ухаживать в миру. Среди инвалидов не мало молодых. Легко ли такое служение? На первый взгляд, ничего хитрого: что может быть легче того, что умеешь? Но, с другой стороны, видя глаза и печали тех, кому ты все это адресуешь, ты чувствуешь, что не в состоянии помочь бОльшим. И единственно верным может быть понимание того, что Господь и не требует от нас этого бОльшего, потому что остальное — это Его вотчина. И значимы здесь только наши сердца, открытые зову Господа, Который нас сюда и привел. Если вы обладаете той лептой, которой можете помочь, присоединяйтесь. Вас ждут там!»
Также в рамках деятельности христианского движения Лепты существует сфера религиозного образования и воспитания. Так, у нас, при содействии с Волгоградской епархией действует школа катехизации, евангельские кружки и прочие виды деятельности и работы с молодежью. Также в рамках осуществления деятельности молодежного отдела Волгоградской епархии и Лепты действует Библейское Волгоградское общество, в рамках которого работает библиотека.
В настоящий момент руководителями движения являются Мария Смирнова и её помощник и заместитель Ратибор Полешко, куратор молодежной евангельской группы и ответственный за информационную работу.
Для того, чтобы расширить свою деятельность и привлечь новых людей, мы решили автоматизироваться, разработать собственный веб-сайт(веб-приложение) для взаимодействия с получателями наших волонтерских услуг, различными учреждениями, автоматизации записи в волонтеры. Также это необходимо для упрощения деятельности администрации и организаторов.
 
2 Основные деятели Лепты
 
3 Лепта на выезде

Результаты проекта, которых мы уже достигли
Нас знают и ждут во многих социальных учреждениях города:
1) Волгоградский областной клинический хоспис
2) Волгоградский ПНИ (на ул.Криворожской 2а)
3) Ергенинский интернат для престарелых и инвалидов 
4) Панасионат "Благодать"
5) ГКСУ СО "Городищенский СРЦ" 
6)ГКОУ КК ШКОЛА-ИНТЕРНАТ СТАНИЦЫ МЕДВЕДОВСКОЙ 
7) ПВР в гостинице "Царицынской"
В 2022 году стали постоянными гостям ПВР в гостинице "Царицынской".

Где мы уже зарегистрированы:
Ссылка на страницу движения «Лепта» на сайте Добро.ру: https://dobro.ru/project/10063544

База данных для руководства движения и описание сущностей с атрибутами:
 
1)Главная сущность в базе данных администраторов – волонтер (volunteer). В этой таблице также могут храниться данных непосредственно о личностях организаторов. Отличие обычных волонтеров от организаторов определяется по полю role.
 О волонтерах содержится информация:
id – идентификатор волонтёра для системы (int),
full_name – ФИО волонтёра (varchar),
age – возраст волонтера(int),
phone_number – номер телефона (varchar),
sex – пол волонтера(varchar),
religion – вероисповедание(varchar), 
id_role(fk) – идентификатор роли данного волонтёра (int, внешний ключ, чтобы ссылаться на роли в организации), 
id_evangelical_group(fk) – id евангельской группы, в которую ходит волонтер или 0, если никуда не ходит(int),
id_achivment(fk) – id событий, в которых участвовал волонтер. 

2) Сущность books(книги).
О книгах содержится следующая информация:
id – идентификатор книги(int),
title – название книги(varchar), 
annotation – аннотация(varchar),
date – дата издания. Год(varchar),
confirmation – гриф книги, что она подтверждена Издательским Советом РПЦ. 1, если да, 0 если нет(int).

3) Сущность library(библиотека).
Таблица библиотеки содержит:
id_reader(fk) – идентификатор читателя. Он соответствует id волонтера из таблицы volunteer.
id_book(fk) – идентификатор книги. Он соответствует id книги из таблицы books.
 
4 Библиотека
4) Сущность news(новости). Выражена в виде отдельной, ни с чем не связанной таблицы.
О новостях в таблице содержится следующая информация:
Id  - идентификатор новости(id),
Heading – заголовок новости(varchar),
Text – текст новости(varchar),
Date – дата новости(date).

5) Сущность achievement(достижения).
О достижениях в таблице содержится следующая информация:
Content – содержание новости(text),
Id_event – идентификатор события(id),
Id_volounteer – идентификатор волонтера(id).

6) evangelical_group(евангельская группа)
О евангельских группах в таблице содержится следующая информация:
Id  - идентификатор евангельской группы(id),
name – название евангельской группы(varchar).

7) Сущность roles(роли).
О ролях в таблице содержится следующая информация:
id – идентификатор роли(id),
title – наименование роли(varchar).

8) Сущность events(события).
О событиях в таблице содержится следующая информация:
id – идентификатор события(id),
title – название события(varchar),
datetime – дата и время события(datetime),
id_type – идентификатор типа события(id)

9) Сущность types_event(тип события)
id – идентификатор типа события(id),
name_type – название типа события(varchar).

Типы связей базы данных и ограничения:
1) Роли – волонтёры: 1 ко многим (у каждого волонтёра может быть только 1 роль).
2) Достижения – волонтеры: 1 ко многим(у каждого волонтера может быть определенная связь в достижениях. То есть, его биография)
3) Евангельская группа – волонтеры: 1 ко многим( каждый волонтер может состоять ТОЛЬКО в одной евангельской группе, определяемой по возрасту).
4) Книги – волонтеры. Многие ко многим. Реализовано через таблицу библиотеки. Многие волонтеры могут брать в библиотеке многое количество книг.
5) События – волонтеры. Многие ко многим. Реализовано через таблицу достижений. Многие волонтеры могут участвовать во многих событиях. И к этому будет приписано что-нибудь, чем они отличились на конкретном событии.
6. События – типы событий: один к одному. У события может быть несколько типов. Так, например, если это и раздача гуманитарной помощи и благотворительный концерт.

Аналитические запросы:
1) Показать всех людей, которых ходят на молодежную евангельскую группу.
2) Подсчитать количество книг в библиотеке, которые имеют гриф от Издательского Совета РПЦ.
3) Посчитать кол-во новостей в период с 1 июня 2022 года по 1 августа того же года.
4) Вывести общее кол-во волонтёров одной и той же роли и являющихся мужчинами.
5) Вывести достижения определенного волонтера по его имени.

Функциональные требования:
1) Добавить нового волонтёра.
2) Изменить дату и время начала проведения события.
3) Удалить событие (например, если оно было отменено).
4) Добавить достижения волонтёра.
5) Добавить новое событие.
6) Открыть новую книгу в библиотеку.
7) Добавить новость.

Нефункциональные требования:
1) Система должна быть простой в использовании и понятной.
2) Система должна соответствовать законам и правилам.
3) Время отклика не должно превышать 3 секунд.
