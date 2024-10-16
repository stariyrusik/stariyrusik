# <a name="Start"> Умный Город </a>

Состав команды:
- Максимов Руслан - 3 курс ИВТ-22-22
- Григорьев Ярослав - 3 курс ИВТ-22-22
- Леонтьев Иван- 3 курс ИВТ-22-22
- Шеховцов Тимофей- 3 курс ИВТ-22-22
##
- [Умный Город](#Start)
   - [Постановка задачи](#Task)
      - [Модель угроз](#Threats)
      - [Модель нарушителя](#Intruder)
   - [Архитектура (до кибериммунизации)](#Architecture1)
      - [Негативные сценарии](#NegativeScenarios)
      - [Позитивные сценарии](#PositiveScenarios)
   - [Архитектура (после кибериммунизации)](#Architecture2)
      - [Решение](#Decision)
##
## <a name="Task"> Постановка задачи</a>
Необходимо создать систему умного города, которая использует технологии для улучшения качества жизни горожан. Обеспечить безопасность данных, эффективность сервисов и улучшение инфраструктуры, предотвратить мошенничество и кибератаки, а также обеспечить надежное взаимодействие между горожанами и муниципальными службами.
## <a name="Threats">Модель угроз</a>
| УГРОЗЫ | ПОСЛЕДСТВИЯ|
| --- | --- |
| Кибератаки на базы данных | Похитители могут получить доступ к личным данным горожан, таким как имена, адреса, номера телефонов и паспортные данные. |
| DDoS-атаки | Злоумышленники могут пытаться перегрузить систему умного города, отправляя множество запросов, чтобы сделать её недоступной для пользователей. |
| Несанкционированный физический доступ | Мошенники могут пытаться получить физический доступ к серверам или другому оборудованию, чтобы установить вредоносное ПО или повредить систему. |
| Несанкционированный доступ | Неавторизованные пользователи могут пытаться получить доступ к системе, используя уязвимости в системе аутентификации. |
| Фальсификация данных | Злоумышленники могут пытаться ввести фальшивые данные в систему, чтобы исказать информацию о состоянии города.|
## <a name="Intruder">Модель нарушителя</a>
| ТИПЫ ЗЛОУМЫШЛЕННИКОВ | ХАРАКТЕРИСТИКИ | МЕТОДЫ | МЕРЫ ЗАЩИТЫ |
| --- | --- | --- | --- | 
|Хакеры| Понимание технических аспектов| Взлом защиты с помощью хакинга| Использование надёжных паролей и двухфакторной аутентификации|
| Сотрудники| Использование статуса в корыстных умыслах | Слив информации благодаря своим должностным привилегиям| Внедрение модели Zero Trust |
| Мошенники| Использование социальной инженерии| Фишинг| Подключение почтовых фильтров |
## <a name="Purposes">Цели безопасности</a>
1. Защита конфиденциальных данных пользователей
2. Защита бизнес-процессов
3. Защита доступности данных

## <a name="Architecture1">Архитектура (До кибериммунизации)</a>

![ыы](/diagram-export-16.10.2024-20_07_02.png)

## <a name="NegativeScenarios">Описание сценариев, при которых ЦБ нарушается</a>
### Сценарий №1
Сценарий: "Компрометация API Gateway"

Описание: Злоумышленник эксплуатирует уязвимость в API Gateway, позволяющую обойти механизмы аутентификации и авторизации. Это дает возможность получить доступ к внутренним сервисам системы умного города, включая доступ к базе данных и возможность манипулировать данными сервисов безопасности, инфраструктуры, взаимодействия и предотвращения мошенничества.
Последствия: Несанкционированный доступ к чувствительным данным горожан, нарушение работы критически важных инфраструктурных и безопасностных сервисов. 

![VP4_JlD04CNxFSKeN_qLiJiA5Cw1AAp4HIH8Liv2dTWIVsIXX0g9KnWh4SR6oHNUt8YtybOfq3GpdlTxiq-Uh5oIkVkxMsEkfcwPoGZlw73K0ZzQwZFx0tfMWtOaoKhiM9RPBCraR2p9-NHkauKZjaEjES4rfL-ez16DRWSa2aXqXhnHV4IBWwu5UtIw5PneyQIvbWCQ1pG](https://github.com/user-attachments/assets/5b78c7cc-7854-4a9f-b524-9c4a1f8f78a9)

### Сценарий №2
Сценарий: "SQL-инъекция"

Описание: Злоумышленник использует уязвимости в запросах к базе данных через один из сервисов, внедряя вредоносный SQL-код. Это позволяет ему читать, модифицировать или удалять данные в базе данных, включая личные данные пользователей и критически важную информацию о работе инфраструктурных сервисов.
Последствия: Утечка или потеря данных, нарушение целостности и доступности важной информации.

![ROynJaCn44JxFSKgr2diaY8Avq0KrhUBBq5YEOQQ10aXKNn4mm6uG1I8Y0WnLvYz4ID1GH6vySxEsvsTBceezVhgKkIig_EY8xnWZsPt-B97U-1_YmFV3fyZ3GlDJkSbfg9ECic-wtEOLM9FsDYAu2sj7rZRFNOs_2B-3_4Y4hhQtuIQg4fsuqdsfufdRD3mhlWctcnfAvPlQ1G](https://github.com/user-attachments/assets/049957fd-080e-4b74-99a3-d7b9a9576507)

### Сценарий №3
Сценарий: "DDoS-атака на API Gateway"

Описание: Злоумышленники организуют массированную DDoS-атаку на API Gateway, что приводит к перегрузке системы и отказу в обслуживании легитимных запросов от пользователей и поставщиков.
Последствия: Сервисы умного города становятся недоступными для пользователей, что нарушает работу городских сервисов и ухудшает качество жизни граждан.

![RT0zJiD040NWVaun2dKAsnr552x01H35ojx24YIhpK8TWyIFA09L6fhSm4HOCJ4iLtXp8oQ92uJGD5lCzzxkZcV1-71rUK5qaeUfvm6Mw13b5f_o90zwRl2bqs8xO3DZb_3K5zPpGavbcPVEJ8AoPwpbHk5SLpUevGwjB0uaxKdwXxpeSiGMZSmPx-XamLZX5Qi3otgM4PaybDS](https://github.com/user-attachments/assets/1bcf48d9-9906-41eb-8e2c-f79684fb3d21)

### Сценарий №4
Сценарий: "Компрометация облачного хранилища"

Описание: Злоумышленники используют уязвимости в конфигурации облачного хранилища для получения доступа к резервным копиям базы данных, содержащим личные данные пользователей и служебную информацию.
Последствия: Потеря конфиденциальности важных данных, возможное их использование в мошеннических целях.


![LO-nJe0m54NtznKlE3l0w63mEun3GpkGA3IbEXjDr8H1DoV_WI0eek8ltFT7lWONSuVUDFVqf6KNJOYN5-T49rLi0sTunYSskSMNzFAWVSQtPi6QiUdOvzm6wmBdv9MigzgR9YhsX55k5BpMwJi6kSCYZpjI_245aQbYVMMYqqiYdn-U7WHdpuvzSSHuKTM6LtrXI4AvtzNIuuC](https://github.com/user-attachments/assets/a5105988-8c70-4c68-aaee-0760eadc3c39)

### Сценарий №5
Сценарий: "Внедрение вредоносного кода через сервисы взаимодействия"

Описание: Злоумышленник эксплуатирует уязвимость в одном из сервисов взаимодействия для внедрения вредоносного ПО, которое может перехватывать данные пользователей или осуществлять атаки на другие компоненты системы.
Последствия: Компрометация данных пользователей, нарушение работы сервисов, распространение атаки на другие системы.
Эти сценарии нарушения информационной безопасности требуют комплексного подхода к обеспечению защиты всех компонентов системы умного города, включая регулярное обновление ПО, мониторинг безопасности и обучение персонала.


## <a name="PositiveScenarios">Описание позитивных сценариев работы</a>

### Сценарий №1
1. Авторизация пользователя
2. Выбор товара
3. Оформление заказа
4. Выбор типа доставки
5. Оплата заказа
6. Передача информации о заказе продавцу
7. Упаковка и отправка товара
8. Получение товара

### Сценарий №2
1. Авторизация пользователя
2. Открытие пользователем вредоносного сайта
3. Попытка запуска скрипта вредоносным сайтом
4. Невыполнение запроса маркетплейсом
5. Последующее ипользование маркеплейса

### Сценарий №3
1. Попытка множественного запроса кода подтверждения через СМС
2. Система увеличивает время между отправкой СМС
3. Злоумышленник не может нанести существенный ущерб

## <a name="Architecture2">Архитектура (после кибериммунизации)</a>

![nLNRRjD047tVhrZrtHBt2mzM-HIJM63HDf7Z59Mdk8ae2AG2GW8XHDG_S4FSk6bY_yBi7t5ckzauTXkP9nxYQDVdd9qvCplUxKLU6FNtzuHuteeweToXCULqfJxH3FyJIjGnfRpUaLvFzdj-A3jX6y-xeWjcq0gwta44sY_0fsh8K4ddu32_03-c9UKgXawcDNf-gny6qT4jEfz](https://github.com/user-attachments/assets/6debdfbc-eaef-420f-9bbd-6e27d88c3dd4)


## <a name="Decision">Решение</a>

### Описание действий для предотвращения нарушения ЦБ1
Использование общих слов при восстановлении пароля "Если такая почта существует, будет отправлен код восстановления". 
Усиление парольной политики, не разрешать людям ставить пароли в виде последовательности букв и цифр.
Ввести ограничение попыток ввода кода восстановления до 3-х раз, а также увеличить длину кода до 6 символов.
Проверять номер заказа и пользователя, сделавшего заказ, при показе информации о заказе.

![pLH1Rn9T5Ds_N_72-gF9fwwwQEh_S3C2YIGK6XWqSGK3iMreh9eOZOas_eDX1ALJ6Fx2lV_8SzxZDKD3IPTc5Zo6S-uzzzp3E-x5KJVkdxICULwBErrRaIzoAuMEPAaJFSTvBYiy2yahDkhPjwsExNJhZQvzOav1RTQQfr4x1k-3P9g0EG3sZwJwJXPwvJXHFtxr0EaZu8NaCjU](https://github.com/user-attachments/assets/5a804c77-4bf6-447b-83b3-b1db014b2dc4)

### Описание действий для предотвращения нарушения ЦБ2
Для защиты нужно внедрить CSRF-токен и установить атрибуты Same-Site, Secure, HTTPOnly для Cookies.

![dP6_JiCm4CRtUmghUmTWOq3bKKpY8L9fgiG5YIbD6P3AnCB6dpT88goMDd5VuVn6VBQCg1WOKAJuShhlTz_dJ4ej2xsudXBHPQBpGepubItltIDlS7RSk9gD_nu9MOf5gGgH5odU9pI7D4kokPnfoDwvuKzN2-ZsRDsAUxTs3wWD3tYslECcCEwcUKIS_a8yOROTOtJmIrtbxjc](https://github.com/user-attachments/assets/a6d47428-0748-40d3-8aa5-4049951f93ed)

### Описание действий для предотвращения нарушения ЦБ3
Использование троттлинга для ограничение одновременной отправки сообщений, увеличение времени между отправками во все последующие действия.

![RP71IiD048Rl-nH3xpceDm-XFafe0nRQf2HR3vuQHQi8LazUHEWRhBMX9Qdn5Vvv8sVI5IIK9R3iplVFDzb-RgFCpYPZOou6DiseXpVKQFWMUtxY1zcN-9QrGzMZAAVhSKffDempEZ5JGKU3qJHAh70lMFEDa7EftSBnFNQyR9bePYyzTDg1NgMyGOMIvuGDQbuILdZ7gWNpIUw](https://github.com/user-attachments/assets/c498864a-d194-4eb6-baf7-1f254ddbba79)





