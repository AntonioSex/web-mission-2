# Mission 2

## Part 0

[Link to video](https://drive.google.com/file/d/1j2isFBBDt7FLybs0WW-CHypeVD8PPAq4/view?usp=sharing)

## Part1

- Вопрос 1. Зачем нужен ssh? Ответ на пару предложений.	 
> SSH (Secure Shell) используется для защищенного удаленного доступа к компьютерам и серверам через зашифрованный протокол. Он позволяет пользователям безопасно управлять удаленными узлами и передавать данные, не подверженные перехвату или изменению злоумышленниками. SSH широко применяется для администрирования серверов, удаленного выполнения команд и безопасной передачи файлов.
- Вопрос 2. Предположим, у вас есть прямой доступ к серверу(терминалу) под управлением ubuntu. У вас есть коллега Вася, который хочет получить доступ к этому серверу. Он генерирует пару ssh ключей с помощью команды ssh-keygen и дает вам свой публичный ключ. В какой файл на сервере нужно записать ключ, чтобы Вася смог подключиться к терминалу сервера?
	 
> Для того чтобы Вася мог подключиться к серверу с использованием своего публичного ключа, необходимо добавить его в файл ~/.ssh/authorized_keys на сервере под управлением Ubuntu. Каждый публичный ключ должен быть добавлен в новую строку этого файла. Вот как можно добавить ключ на сервер:
Сначала скопируйте публичный ключ Васи на сервер, например, через scp или любым другим способом.
Затем отредактируйте файл ~/.ssh/authorized_keys на сервере и добавьте содержимое публичного ключа Васи в этот файл.
Сохраните файл и убедитесь, что у Васи есть соответствующие права доступа к файлу ключей и каталогу ~/.ssh на сервере.
Пример команды для добавления ключа из локального файла на сервер:
bash
cat вася_публичный_ключ.pub >> ~/.ssh/authorized_keys


- Вопрос 3. Тут вопрос про АПИ. Разберитесь, что такое long polling и webhooks, опишите сами в нескольких предложениях, как они работают.	 
> Long polling используется для постоянного опроса сервера ботом с целью получения обновлений, что может привести к частым запросам и увеличению нагрузки на сервер. В отличие от long polling, webhooks позволяют серверу Telegram самому отправлять обновления боту, что уменьшает нагрузку и обеспечивает более эффективную передачу данных, а также предоставляет возможность для реального времени подключения и получения событий без необходимости активного опроса со стороны бота.
 

- Вопрос 4. Найдите информацию, что такое issues на гитхабе и для чего нужны. Также вставьте ссылки на пару примеров issues в популярных open source проектах.	 
> GitHub Issues представляют собой инструмент для отслеживания и управления работой, необходимой для улучшения ваших проектов. Каждое issue может представлять собой задачу, отчет об ошибке или запрос функции, и может быть назначено участникам команды, помечено метками и связано с вехами (2 ). Используйте issues для планирования, обсуждения и отслеживания работы, а также для эффективного общения с другими (1 ).

Например, одним из примеров issues может быть следующее:

"Fix navigation bug on mobile devices" - задание на исправление ошибки в навигации на мобильных устройствах.
"Implement dark mode feature" - задача по добавлению функции темного режима.
Некоторые популярные open source проекты и примеры issues:

Bootstrap: Issues Bootstrap доступны по ссылке https://github.com/twbs/bootstrap/issues .
Node.js: Пример issues для Node.js можно найти здесь https://github.com/nodejs/node/issues .
Эти примеры демонстрируют, как issues используются в open source проектах для управления задачами, отчетами об ошибках и запросами на функциональность. 

- Вопрос 5. Ваш проект используется пустую папку images, но гит не поддерживает отслеживание пустых директорий. Что делать?	 
> Если вы хотите поддерживать пустую директорию в вашем репозитории Git, вы можете добавить в эту директорию файл-заглушку (.gitkeep или .gitignore) и затем зафиксировать его в вашем репозитории.

Вот как это сделать:

В командной строке или терминале создайте файл-заглушку в пустой папке images с помощью команды touch (для Unix/Linux) или type nul (для Windows):

На Unix/Linux:

text

touch images/.gitkeep
На Windows:

text

type nul > images\.gitkeep
Затем добавьте этот файл и зафиксируйте его в вашем репозитории:

text

git add images/.gitkeep
git commit -m "Added .gitkeep to images directory"
Теперь Git будет отслеживать эту пустую папку, и вы сможете сохранить ее состояние в репозитории.  