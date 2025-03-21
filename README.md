LDAP (Lightweight Directory Access Protocol) — это сетевой протокол прикладного уровня, используемый для взаимодействия с сервисами каталогов. Каталоги представляют собой специализированные базы данных, организованные иерархически, которые содержат информацию о пользователях, устройствах, службах и других объектах сети. Протокол LDAP позволяет клиентам искать и извлекать данные из каталога, а также изменять эти данные при наличии соответствующих прав.

### Основные операции протокола LDAP

Протокол LDAP поддерживает следующие операции:

1. **Поиск** (`search`):
   - Позволяет находить объекты в каталоге по заданному критерию (например, имя пользователя).
   
2. **Добавление** (`add`):
   - Добавляет новый объект в каталог.

3. **Удаление** (`delete`):
   - Удаляет существующий объект из каталога.

4. **Изменение** (`modify`):
   - Обновляет атрибуты существующих объектов.

5. **Переименование** (`modrdn`):
   - Изменяет имя объекта в каталоге.

6. **Сравнение** (`compare`):
   - Сравнивает значение атрибута объекта с указанным значением.

7. **Привязывание** (`bind`):
   - Аутентификация клиента перед выполнением операций.

8. **Отвязывание** (`unbind`):
   - Завершение сеанса связи с сервером каталогов.

9. **Расширенный запрос** (`extended operation`):
   - Выполнение специфичных операций, определяемых расширениями сервера каталогов.

### Утилиты для подключения к каталогу по протоколу LDAP

Для работы с каталогами через LDAP можно использовать несколько утилит:

1. **ldapsearch**:
   - Командная строка утилита для выполнения поисковых запросов к LDAP-каталогу.

2. **ldappasword**:
   - Используется для изменения паролей в LDAP-каталоге.

3. **ldapmodify**:
   - Инструмент для добавления, удаления и модификации записей в каталоге.

4. **ldapdelete**:
   - Команда для удаления объектов из каталога.

5. **Apache Directory Studio**:
   - Графический клиент для администрирования LDAP-каталогов.

6. **LdapAdmin**:
   - Еще один графический инструмент для работы с LDAP-каталогами.

### Оснастка Редактирование ADSI

Оснастка **Редактирование ADSI** является инструментом для просмотра и редактирования содержимого службы каталогов Active Directory. Она позволяет просматривать и управлять объектами AD, такими как пользователи, группы, организационные единицы (OU), принтеры и другие ресурсы. Этот инструмент предоставляет низкоуровневый доступ к данным каталога, позволяя администраторам выполнять различные административные задачи.

### Утилита ldp.exe

Утилита **ldp.exe** — это графическая программа, входящая в состав пакета Windows Server, предназначенная для диагностики и тестирования служб каталогов, использующих протокол LDAP. С её помощью можно:

- Просматривать структуру каталога.
- Выполнять поиск объектов.
- Добавлять, удалять и изменять объекты.
- Тестировать аутентификацию.
- Проверять права доступа.

### Установка утилиты ldp.exe

Утилиту **ldp.exe** можно добавить в систему, установив пакет поддержки удаленного администрирования **RSAT (Remote Server Administration Tools)**. Для установки RSAT в Windows 10/11:

1. Откройте **Панель управления** → **Программы и компоненты** → **Включение или отключение компонентов Windows**.
2. Найдите компонент **Средства удалённого администрирования сервера** и установите нужные инструменты, включая **AD DS и LDAP**.

### Альтернативные средства для работы с LDAP

Существуют сторонние программы для работы с LDAP-каталогами:

- **JXplorer**: Кросс-платформенный клиент с открытым исходным кодом.
- **Softerra LDAP Browser**: Бесплатный браузер LDAP-каталогов.
- **phpLDAPadmin**: Веб-интерфейс для управления LDAP-каталогами.

### Хранение информации в службе каталогов

Информация в службе каталогов хранится в виде объектов, каждый из которых имеет уникальный идентификатор (DN — Distinguished Name). Объекты организованы в древовидную структуру, основанную на иерархии доменов и организационных единиц (OU). Атрибуты объектов определяют их свойства, такие как имя пользователя, пароль, группа принадлежности и др.

### Атрибуты объектов в LDAP

Атрибуты объектов в LDAP представляют собой пары ключ-значение, описывающие характеристики объекта. Например, для пользователя это могут быть такие атрибуты, как `cn` (Common Name), `sn` (Surname), `mail` (Email Address) и многие другие. Каждый атрибут имеет тип данных (например, строковый, числовой, булевый) и может содержать одно или несколько значений.

### Составление фильтра для поиска в LDAP

Фильтры для поиска в LDAP позволяют ограничить результаты запроса определёнными условиями. Фильтр представляет собой строку, содержащую условия сравнения атрибутов объектов. Примеры операторов:

- `(objectClass=person)` — находит все объекты класса person.
- `(cn=John Doe)` — ищет объекты с Common Name равным John Doe.
- `(&(objectClass=user)(!(cn=System)))` — находит всех пользователей, кроме тех, у кого Common Name равен System.

### Операторы в фильтрах LDAP

Основные операторы в фильтрах LDAP:

- `&`: Логическое И.
- `|`: Логическое ИЛИ.
- `!`: Отрицание.
- `=`: Равно.
- `>=`, `<=`: Больше или равно, меньше или равно.
- `~=`: Приблизительное соответствие.

### Запись специальных символов в LDAP-запросах

Специальные символы в LDAP-запросах требуют экранирования. Например:

- Пробел: `\20`.
- Звездочка: `\*`.
- Скобки: `$`, `$`.
- Обратная косая черта: `\\`.

### Просмотр всех атрибутов объекта в ldp.exe

Чтобы просмотреть все атрибуты объекта в программе **ldp.exe**, нужно:

1. Подключиться к серверу LDAP.
2. Перейти в меню **Connection** → **Bind** и выполнить привязку.
3. В дереве каталогов выбрать нужный объект.
4. В контекстном меню объекта выбрать **Search...**.
5. В окне поиска установить флажок **Show only attributes that have values** и нажать **Run**.

### Поиск пользователя по второму почтовому адресу

Для поиска пользователя по второму почтовому адресу в домене можно использовать следующий фильтр:

`(proxyAddresses=smtp:john.doe@example.com)`

Этот фильтр найдёт все объекты, у которых есть указанный почтовый адрес.

### LDIF и его использование

LDIF (LDAP Data Interchange Format) — это текстовый формат, предназначенный для обмена данными между LDAP-каталогами. Он используется для импорта и экспорта данных, а также для внесения изменений в каталоги. Формат LDIF позволяет добавлять, обновлять и удалять объекты путём описания их атрибутов в текстовом файле.

### Утилита ldifde

Утилита **ldifde** позволяет выполнять экспорт и импорт данных в формате LDIF из командной строки. Примеры использования:

Экспорт всех объектов:
```
ldifde -f export.ldif -d "dc=example,dc=com" -p subtree -r "(objectClass=*)"
```

Импорт данных из файла:
```
ldifde -i -f import.ldif
```

### Делегирование прав в Active Directory

Делегирование прав в Active Directory позволяет передавать полномочия на выполнение определённых административных действий другим пользователям или группам. Это полезно для распределения обязанностей среди сотрудников, чтобы снизить нагрузку на администраторов и повысить безопасность. Права могут быть делегированы на уровне OU, отдельных объектов или всего домена.

### Функции, которые можно делегировать

Примеры функций, которые можно делегировать:

- Создание, изменение и удаление пользователей.
- Управление группами.
- Разрешение или блокировка учётных записей.
- Назначение прав доступа к файловым серверам и принтерам.

### Мастер делегирования управления

Мастер делегирования управления (**Delegation of Control Wizard**) в Active Directory упрощает процесс делегирования прав. Он пошагово проводит администратора через выбор объекта, типа задания и назначения прав определённым пользователям или группам.

### Восстановление удаленных объектов

В Active Directory удалённые объекты перемещаются в специальный контейнер **Deleted Objects**. Чтобы восстановить удалённый объект:

1. Включите корзину Active Directory.
2. Используйте консоль **Active Directory Administrative Center** или PowerShell-команду `Get-ADObject` для поиска удалённых объектов.
3. Воспользуйтесь командой `Restore-ADObject` для восстановления объекта.

### Корзина Active Directory

Корзина Active Directory позволяет восстанавливать случайно удалённые объекты до их окончательного удаления из системы. Чтобы включить корзину:

1. Откройте **Active Directory Administrative Center**.
2. Выберите домен и перейдите в **Features** → **Recycle Bin**.
3. Нажмите **Enable**.

### Окончательное удаление объектов

После истечения срока хранения в корзине (по умолчанию 180 дней) объекты окончательно удаляются из Active Directory. Их нельзя будет восстановить стандартными средствами.

### Изменяемые атрибуты при удалении объекта

При удалении объекта его атрибуты заменяются на служебные значения, такие как `isDeleted` и `lastKnownParent`. Эти атрибуты помогают идентифицировать удалённые объекты и их местоположение в структуре каталога.

### Учетные записи и безопасность

Учетная запись — это набор данных, который определяет личность пользователя или устройства в системе. Она включает в себя имя пользователя, пароль и другие параметры, необходимые для идентификации и авторизации. Безопасность обеспечивается путем проверки подлинности пользователя при входе в систему и контроля доступа к ресурсам на основе прав, назначенных учетной записи.

### Идентификация пользователей ОС

Операционная система идентифицирует пользователей с помощью уникального идентификатора безопасности (SID), который присваивается каждой учетной записи при создании. SID гарантирует, что даже после переименования или удаления учетной записи система сможет различать пользователей.

### SID (Security Identifier)

SID — это уникальная последовательность чисел, представляющая учетную запись пользователя, группы или другого объекта безопасности. Он формируется системой автоматически и состоит из двух частей: идентификатора безопасности и относительного идентификатора (RID). SID остается неизменным на протяжении всей жизни учетной записи.

### Повторное создание учетной записи

Даже если учетная запись создается с тем же именем, система создает новый SID, что делает новую учетную запись уникальной с точки зрения безопасности. Это предотвращает случайное предоставление доступа старым объектам.

### Дополнительные параметры учетной записи

К дополнительным параметрам учетной записи относятся:

- Срок действия пароля.
- Политика блокировки учетной записи.
- Членство в группах.
- Ограничения на вход в систему (время, место и т.д.).

### Части SID

SID состоит из:

1. Идентификатора безопасности (S-1-5-21-XXXXXX-YYYYYY-ZZZZZZ).
2. Относительного идентификатора (RID), который уникально идентифицирует объект внутри домена.

### Стандартные SID

Примеры стандартных SID:

- `S-1-5-18`: Локальная система.
- `S-1-5-32-544`: Администраторы.
- `S-1-5-32-545`: Пользователи.

### Определение SID по имени и наоборот

Для определения SID по имени пользователя или наоборот можно использовать утилиты:

- `whoami /user`: Показывает текущее имя пользователя и его SID.
- `wmic useraccount where name='ИмяПользователя' get sid`: Получение SID по имени.
- `psgetsid ИмяПользователя`: Получение SID по имени с использованием PsTools.

### Локальные и доменные учетные записи

Локальные учетные записи создаются и управляются на конкретном компьютере и применяются только на нём. Доменные учетные записи управляются централизованно через Active Directory и могут использоваться для входа в сеть и доступа к общим ресурсам.

### Создание и изменение локальных учетных записей

Локальные учетные записи создаются и изменяются через Панель управления → Учётные записи пользователей или командную строку с использованием команды `net user`.

### Создание и изменение доменных учетных записей

Доменные учетные записи создаются и изменяются через консоли Active Directory Users and Computers или PowerShell-команды `New-ADUser`, `Set-ADUser`.

### Учетные записи Microsoft

Учетные записи Microsoft используются для входа в онлайн-сервисы компании, такие как Office 365, OneDrive и Xbox Live. Они связаны с электронной почтой и паролем и могут синхронизироваться с локальными или доменными учетными записями.

### Доступ доменных учетных записей к локальным ресурсам

Доменные учетные записи могут получать доступ к ресурсам локального компьютера, если компьютер включен в домен и учетная запись имеет соответствующие права доступа.

### Одноименные учетные записи на разных компьютерах

Одноименные учетные записи на разных компьютерах считаются разными пользователями, поскольку каждая из них имеет уникальный SID, что важно для обеспечения безопасности и разграничения доступа.

### Информация о неудачных попытках входа

Количество неудачных попыток входа можно узнать через журнал событий безопасности или с помощью команд PowerShell, таких как `Get-EventLog Security | Where-Object {$_.EventID -eq 4625}` (для неудачного входа).

### Группы, добавляемые в локальные группы при включении компьютера в домен

При включении компьютера в домен в локальные группы добавляются доменные группы, такие как `Domain Admins`, `Domain Users` и другие, что обеспечивает совместимость и управление правами доступа.

### Использование фильтров для запросов к службе каталогов

Фильтры для запросов к службе каталогов позволяют извлечь нужную информацию, такую как неудачные попытки входа, используя операторы поиска и критерии отбора.

### Типы групп пользователей в Windows Server

Поддерживаемые типы групп:

- **Локальные группы**: Применяются только на одном компьютере.
- **Группы безопасности**: Используются для управления доступом к ресурсам.
- **Группы рассылки**: Предназначены для отправки сообщений группе пользователей.

### Отличия типов групп по области действия

- **Локальные группы**: Действуют только на локальном компьютере.
- **Глобальные группы**: Могут включать пользователей и группы одного домена.
- **Универсальные группы**: Могут включать пользователей и группы из нескольких доменов одной леса.

### Возможности включения объектов в разные типы групп

- **Локальные группы домена**: Могут включать глобальные и универсальные группы.
- **Глобальные группы**: Могут включать пользователей и другие глобальные группы одного домена.
- **Универсальные группы**: Могут включать пользователей, глобальные и другие универсальные группы из любого домена леса.

### Встроенные локальные группы

Встроенные локальные группы имеют предопределенные права и разрешения, которые нельзя изменить. Примеры: `Администраторы`, `Операторы архива`, `Опытные пользователи`.

### Какие объекты могут быть включены в универсальные группы

Универсальные группы могут включать пользователей, глобальные и другие универсальные группы из любых доменов леса Active Directory.


### Группы, которые могут быть членами универсальных групп

Универсальные группы могут включать в себя:

- **Пользователей**,
- **Глобальные группы**,
- **Другие универсальные группы**.

Это позволяет гибко структурировать права доступа и управлять ими на уровне всей организации.

---

### Влияние изменения членства пользователя в группах на доступ к ресурсам

Когда пользователь добавляется или удаляется из группы, его доступ к ресурсам изменяется соответствующим образом. Если пользователь был членом группы, имеющей доступ к определенному ресурсу, и его исключили из этой группы, он теряет этот доступ. Аналогично, включение пользователя в группу с новыми привилегиями предоставляет ему возможность доступа к новым ресурсам.

Пример: если пользователь становится членом группы "Администраторы", он получает права на администрирование системы, но если его исключают из этой группы, он лишается этих полномочий.

---

### Ограничения при вложении групп друг в друга

Некоторые ограничения на вложение групп зависят от их типа:

- **Глобальные группы** могут включать только пользователей и другие глобальные группы из того же домена.
- **Универсальные группы** могут включать пользователей, глобальные и другие универсальные группы из любых доменов леса.
  
Важно учитывать, что вложенность групп может усложнить управление правами доступа, особенно если одна группа вкладывается в другую, имеющую противоположные права.

---

### Преобразования типов групп в режиме native mode

Начиная с Windows 2000, режим **native mode** позволяет конвертировать типы групп следующим образом:

- **Глобальную группу** можно преобразовать в **универсальную**.
- **Универсальную группу** можно преобразовать обратно в **глобальную**, если она не содержит вложенных универсальных групп.

Преобразование возможно благодаря поддержке смешанных режимов работы доменов, что облегчает миграцию старых конфигураций в новые структуры.

---

### Проблемы при преобразовании типа группы

При преобразовании типа группы, особенно если в ней уже есть вложенные группы, могут возникнуть сложности:

- **Несоответствие правил вложенности**: Универсальные группы могут содержать другие универсальные группы, тогда как глобальные — нет.
- **Потеря прав доступа**: Если вложенные группы теряют права доступа после преобразования, это может привести к проблемам с безопасностью.

Перед преобразованием важно проверить текущие права и вложенные группы, чтобы избежать неожиданных последствий.

---

### Группы рассылки (Distribution Group)

Группы рассылки предназначены исключительно для рассылки сообщений по электронной почте. Они не предоставляют никаких прав доступа к ресурсам и не влияют на безопасность. Основное назначение — организация рассылок и управление контактами.

---

### Группы, включаемые в локальные группы безопасности

В локальные группы безопасности могут быть включены:

- **Локальные пользователи**,
- **Локальные группы**,
- **Глобальные группы**,
- **Универсальные группы**.

Такое разнообразие позволяет точно контролировать доступ к ресурсам конкретного компьютера.

---

### Группы, включаемые в универсальные группы

Универсальные группы могут включать:

- **Пользователей**,
- **Глобальные группы**,
- **Другие универсальные группы**.

Это делает универсальные группы мощным инструментом для управления доступом на уровне организации.

---

### Группы, включаемые в глобальные группы безопасности

Глобальные группы могут включать:

- **Только пользователей** и **другие глобальные группы** из того же домена.

Они действуют только в пределах своего домена и не распространяются на всю организацию.

---

### Ролевое управление (Role-Based Access Control, RBAC)

Ролевое управление — это метод управления доступом, при котором права назначаются ролям, а не отдельным пользователям. Пользователь получает доступ к ресурсам на основании своей роли, что упрощает администрирование и повышает безопасность.

---

### Связь ролей с группами безопасности и локальными группами

Роли часто реализуются через группы безопасности и локальные группы. Пользователям назначаются роли, а сами роли ассоциируются с конкретными правами доступа к ресурсам. Таким образом, администратор управляет доступом через определение ролей, а не вручную каждому пользователю.

---

### Действия администратора при подключении нового пользователя

При подключении нового пользователя администратор:

1. Создает учетную запись.
2. Определяет роль или роли, которые будут присвоены новому пользователю.
3. Добавляет пользователя в соответствующую группу безопасности или назначает ему роли.

Это упрощает управление правами доступа и снижает вероятность ошибок.

---

### Итоговые разрешения при множественном членстве в группах

Если пользователь входит в несколько групп с разными правами, итоговое разрешение определяется согласно следующему принципу:

- **Запрет** имеет приоритет над **разрешением**.
- Если для одной группы есть разрешение на операцию, а для другой — запрет, операция будет запрещена.

Такой подход помогает предотвратить случайное расширение прав доступа.

---

### Последствия наличия противоречивых разрешений

Противоречивые разрешения могут приводить к путанице и ошибкам в управлении доступом. Поэтому важно тщательно проверять конфигурации групп и ролей, чтобы избежать проблем с безопасностью.

---

### Осторожность при назначении явных запретов

Явные запреты могут конфликтовать с разрешениями, что затрудняет управление доступом. Рекомендуется избегать избыточных запретов и тщательно документировать все исключения.

---

### Исключение из правила приоритета запрета

Существует исключение: если для объекта установлены **явные разрешения** на уровне владельца объекта, они имеют приоритет над любыми запретами.

---

### Использование ролей прикладными программами

Прикладные программы могут интегрироваться с ролями для динамического управления доступом. Например, веб-приложение может проверять принадлежность пользователя к определенной роли и предоставлять доступ к функциям на основе этой информации.

---

### Примеры ролей

Типичные примеры ролей включают:

- **Администратор**,
- **Менеджер**,
- **Оператор**,
- **Читатель**.

Эти роли определяют уровень доступа и полномочий каждого пользователя.

---

### Проверка наличия запретов и разрешений

Проверка осуществляется на каждом этапе обработки запроса доступа. Система сначала проверяет наличие запрещающих правил, затем разрешающих. Если найдены оба вида правил, действует принцип приоритета запрета.

---

### Проблемы при сложной структуре групп и явных запретах

Сложная структура групп и большое количество явных запретов могут сделать управление доступом запутанным и труднопредсказуемым. Важно минимизировать количество запретов и стараться использовать роли и группы для упрощения процесса.

---

### Упрощение управления правами доступа с использованием ролей

Использование ролей позволяет создавать четкую и предсказуемую структуру доступа. Администратор может легко менять права доступа, меняя роли, а не индивидуально настраивая каждую учетную запись.

---

### Разрешения общего доступа и их применение

Разрешения общего доступа контролируют доступ к сетевым ресурсам на уровне общего доступа (shares). Они задаются для папок и файлов, размещаемых на общих ресурсах.

---

### Разрешения безопасности и их связь с файловой системой

Разрешения безопасности применяются к объектам файловой системы (NTFS) и контролируют доступ на уровне отдельных файлов и папок. Они более детализованы и обеспечивают точный контроль доступа.

---

### Взаимодействие разрешений общего доступа и безопасности

Разрешения общего доступа и безопасности работают совместно:

- **Общий доступ** ограничивает доступ к ресурсу на уровне сети.
- **Безопасность** регулирует доступ к файлам и папкам на уровне файловой системы.

Доступ предоставляется только в случае совпадения обоих видов разрешений.

---

### Файловая система, контролируемая только разрешениями общего доступа

Файловая система FAT32 не поддерживает разрешения безопасности, поэтому доступ к ресурсам контролируется только через разрешения общего доступа.

---

### Ошибка предоставления общего доступа к папкам на рабочем столе

Часто пользователи предоставляют общий доступ к папкам на своем рабочем столе, забывая, что это открывает доступ ко всему содержимому рабочего стола. Это может привести к утечке конфиденциальной информации.

---

### Исправление ошибки с доступом к общей папке на рабочем столе

Для исправления ошибки достаточно создать отдельную папку вне рабочего стола и предоставить к ней общий доступ, оставив рабочий стол защищенным.

---

### Два подхода к настройке прав доступа к сетевым ресурсам

Два основных подхода:

1. **Минимизация прав**: Предоставляется минимальный набор прав, необходимых для выполнения конкретных задач.
2. **Максимализация прав**: Изначально предоставляются максимальные права, которые затем сужаются через дополнительные ограничения.

Первый подход предпочтительнее, так как минимизирует риски несанкционированного доступа.

---

### Настройка разрешений для различных объектов

Различные объекты могут требовать разной степени защиты. Например, общие файлы могут иметь менее строгий контроль, чем конфиденциальные документы. Гибкое сочетание разрешений общего доступа и безопасности позволяет обеспечить нужный уровень защиты.

---

### Преимущества сочетания разрешений общего доступа и безопасности

Комбинируя оба типа разрешений, можно достичь высокой точности в управлении доступом. Это позволяет обеспечивать защиту на разных уровнях, минимизируя риск утечки данных и несанкционированного доступа.

---

Таким образом, эффективное управление доступом требует комплексного подхода, сочетающего роли, группы, разрешения общего доступа и безопасности.
