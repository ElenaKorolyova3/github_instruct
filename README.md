# Инструкция по работе в GitHub
---

Веб-сервис GitHub востребован для хостинга IT-проектов и совместной разработки. Разработчики системы называют ее «социальной сетью» для программистов. Здесь они объединяют репозитории, комментируют примеры «чужого» кода и используют платформу в качестве облачного хранилища с возможностью быстрой передачи заказчику.

## Предварительная настройка <div id='start' />
Для начала [зарегистрируйтесь на GitHub:](https://github.com/) задайте логин, почту и придумайте пароль. После «Создать аккаунт» не забудьте проверить почту и подтвердить её (опрос от Github после подтверждения почты можно пропустить).

![Начало](https://i.postimg.cc/z35QVtJ7/1.png)

Для того чтобы сервис определил, кто вы и имеете ли право работать с тем или иным репозиторием, нужно представиться — пройти процесс аутентификации.

При подключении используется пара ключей — открытый (публичный, public) и закрытый (приватный, private). Пользователь создаёт пару ключей при помощи специальной команды и сохраняет закрытый ключ у себя, а открытый кладёт на сервер (в нашем случае на GitHub). А работает это всё благодаря асимметричному шифрованию.

Чтобы создать пару ключей, в терминале нужно ввести команду, задать путь для хранения ключей и указать пароль к ключу (необязательно).

Далее будем опираться на то, что путь для ключей дефолтный и пароль на ключи не установлен.

Пароль для ключей нужен как дополнительная мера безопасности, если вдруг ваш приватный ключ попадёт не в те руки.

~~~
$ ssh-keygen
Generating public/private rsa key pair.
# путь до ключей, в скобках путь по умолчанию
Enter file in which to save the key (/Users/ifireice/.ssh/id_rsa):  
# пароль для ключей, при задании пароля в консоли не отображается ничего, даже звёздочки
# если нажать Enter, ничего не вводя, пароль будет пустым
Enter passphrase (empty for no passphrase):
# повторите пароль
Enter same passphrase again:
# после появится сообщение такого вида
Your identification has been saved in /Users/ifireice/.ssh/id_rsa
Your public key has been saved in /Users/ifireice/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:Zu+HkZPC4ZP0veRmVjuKgylVvljHBNO8mHs+ieFFPvs ifireice@ifireice-osx
The key's randomart image is:
+---[RSA 3072]----+
|           o     |
|          o o    |
|           = .   |
|        o + +    |
|       +S* X     |
|       oB.@ X .  |
|       . O.# * . |
|      . +.*.% o  |
|       .  o*.+E. |
+----[SHA256]-----+
~~~

Бинго, ключи сгенерированы: в заданной директории появятся два файла, id_rsa и id_rsa.pub.

Теперь надо добавить публичный ключ в аккаунт на GitHub:

~~~
# выведите содержимое публичного ключа в консоль
$ cat ~/.ssh/id_rsa.pub 
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDDJfHIi73sKd6cqm3RwKuY1zl46aAaE6X9Gp
/6zJiY3BiJj95oJjPdpfpPhVFWLIbmT8zFAtOLbX9N4C3b0enHUzgMacP/Kl4AbrAkhLqaua9iD
VNxxiTVxADG1M5525oc/eAvx7y0pXIb9ouWdYJSKa8/TUYFhWlCzV2quY9SA0FaMs7eY41+KWYpG.....
tA0oGxv+7WmXQmQzleLIRG13KQ+VAbL2vabdPcRoGuZavh0smOr/GtVSnLdspZ5RgONMSPWlF2I1YHMR
Q7CIKPs= ifireice@ifireice-osx
$
~~~

Скопируйте ключ от символов ssh-rsa и до конца файла и вставьте его в ваш аккаунт на GitHub.

![ssh](https://i.postimg.cc/18gCLbHm/2.png)

![ssh](https://i.postimg.cc/XpYDgrBy/3.png)

![ssh](https://i.postimg.cc/jL333Ry3/4.png)


## Создание аккаунта в Github

Первый шаг к использованию сервиса GitHub заключается в регистрации нового пользователя. В процедуре нет ничего сложного – достаточно зайти на официальный сайт <https://github.com> и создать новую учетную запись. Система запросит рабочую электронную почту.

Пароль вводится на выбор пользователя, но с учетом правил. Так, рекомендуется комбинация размером в 15 символов или 8, но с использованием хотя бы одной цифры и строчной буквы. Имя пользователя, как и email, проверяется на занятость, и придется выбирать тот, с которым платформа позволит продолжать регистрацию.

Далее нужно указать, хочется ли получать новости об обновлениях продуктов и самой системы. Последним шагом становится подтверждение – пользователю предлагается собрать паззл, после чего станет активной кнопка ***«Зарегистрироваться»*** .

Вход на платформу будет открыт только после подтверждения электронной почты, поэтому зайти анонимно не получится. Это своеобразная защита сервера от многочисленных ботов и гарантия для пользователей, что они будут общаться с реальными людьми. Теперь можно приступать к управлению настройками внутри личного кабинета.

## **Взаимодействие с GitHub**
---

GitHub предоставляет встроенные средства общения для совместной работы, чтобы вы могли взаимодействовать с сообществом. В этом кратком руководстве показано, как выбрать подходящее средство для ваших потребностей.

Вы можете создавать проблемы, запросы на вытягивание, GitHub Discussions и обсуждения в команде, а также участвовать в них, в зависимости от требуемого типа обсуждения.

### GitHub Issues
* удобны для обсуждения конкретных сведений о проекте, например для отчетов об ошибках, сведений о запланированных улучшениях и отзывов;
* относятся к конкретному репозиторию и обычно имеют конкретного владельца;
* часто называются системой отслеживания ошибок GitHub.
### Запросы на вытягивание
* позволяют предлагать конкретные изменения;
* позволяют напрямую комментировать предложенные другими пользователями изменения;
* относятся к конкретному репозиторию.
### GitHub Discussions
* выполняют роль форума, который лучше всего подходит для обсуждения в свободной форме идей и планов, требующих общего участия;
* могут охватывать множество репозиториев;
* предоставляют возможность совместной работы без привязки к базе кода, например для мозгового штурма идей и наработки базы знаний сообщества;
* часто не имеют конкретного владельца;
* часто используются не для создания конкретной задачи.
### Обсуждения в команде
* могут создаваться на странице обсуждения в команде, и могут охватывать несколько проектов без привязки к определенной проблеме или запросу на вытягивание. Вместо того, чтобы открыть вопрос в репозитории для обсуждения идеи, вы можете привлечь к беседе всю команду, проведя обсуждение в команде.
* позволяют проводить с командой обсуждения для планирования, анализа, проектирования, изучения реакции пользователей и принятия решений общего характера по проекту;
____

## Создание репозитория

Важно отметить, что сервис англоязычный, и пользоваться им без знания языка получится только при использовании обновленных версий браузеров типа Google Chrome, где есть встроенные функции по переводу страниц. В любом случае работа начинается с создания собственного репозитория – в бесплатном режиме доступны публичные, частные откроются только при активации платного тарифа.

### Последовательность действий:

1. В правом верхнем углу любой страницы откройте раскрывающееся меню  и выберите Новый репозиторий.
В поле Имя репозитория введите hello-world.

2. В поле Описание напишите краткое описание.

3. Выберите параметр Добавить файл сведений.

4. Выберите, будет ли репозиторий общедоступным или частным.

5. Выбрать нужный тип лицензии и нажать на кнопку *«Create project».*
Тип лицензии (приватная или публичная) допускается заменить после, в процессе использования платформы. Единственная настройка, которую пользователи делают сразу, – это создание нескольких веток для размещения разных проектов. Например, для тестового кода и финальных релизов, чтобы не путать их при разработке и общении с другими кодерами.

6. Щелкните Создать репозиторий.

### Проект в Гитхабе

Подобный подход часто используют создатели продуктов, которыми пользуются «массы». Им передается ссылка на проверенные стабильные версии, в то время как команда продолжает работу над таким же комплектом файлов без опасения нарушить функциональность системы в целом. При использовании платформы следует ориентироваться на отметку *«Branch».*

Данная отметка обозначает текущую ветку. Создание новой инициируется просто – достаточно в списке начать набирать еще несуществующее название, и система выдаст сообщение «Create branch». Сразу после этого пользователь перекидывается в новую ветку (это стоит учитывать при работе, чтобы случайно не начать редактирование «не тех файлов»).

### Изменение файлов и коммиты
Корректировка файлов на GitHub выполняется при помощи коммитов. Это непосредственно само исправление и краткое описание изменений. Такой подход позволяет «внешним» пользователям ориентироваться в нововведениях кода и упрощает контроль командной работы, когда один и тот же файл может редактироваться разными исполнителями.

Система сохранения информации о корректировках удобна, когда они вносятся в различные участки кода, но связаны с определенной задачей. Фактически текстовый файл с описанием «связывает» разрозненные изменения и объясняет непосвященному программисту их суть, назначение. Чтобы запустить редактирование README, нужно в правой панели нажать на «кисточку».

После этого откроется текстовый редактор, где вносятся исправления. По завершении заполняется поле *«Commit»* внизу страницы (кратко, что изменилось) и нажимается кнопка *«Commit changes»*. Сохраненные корректировки будут внесены в текущую (активную) ветку проекта, поэтому перед их внесением следует убедиться в правильном выборе.

### Внесение и фиксация изменений

После создания ветви на предыдущем шаге в GitHub открылась страница кода для новой ветви readme-edits, которая является копией ветви main.

Вы можете вносить изменения в файлы в репозитории и сохранять их. В GitHub сохраненные изменения называются фиксациями. С каждой фиксацией связано сообщение о фиксации, в котором объясняется, почему было внесено данное изменение. В сообщениях о фиксациях ведется история изменений, чтобы другие участники могли понять, что вы сделали и почему.

* В созданной ветви readme-edits щелкните файл README.md.

* Щелкните , чтобы изменить файл.

* В редакторе напишите немного о себе. Попробуйте использовать различные элементы Markdown.

* В поле Фиксация изменений напишите сообщение о фиксации с описанием изменений.

* Щелкните Зафиксировать изменения._____
____

## Работа с удаленными репозиториями

Для того, чтобы внести вклад в какой-либо Git-проект, вам необходимо уметь работать с удалёнными репозиториями. Удалённые репозитории представляют собой версии вашего проекта, сохранённые в интернете или ещё где-то в сети. У вас может быть несколько удалённых репозиториев, каждый из которых может быть доступен для чтения или для чтения-записи. Взаимодействие с другими пользователями предполагает управление удалёнными репозиториями, а также отправку и получение данных из них. Управление репозиториями включает в себя как умение добавлять новые, так и умение удалять устаревшие репозитории, а также умение управлять различными удалёнными ветками, объявлять их отслеживаемыми или нет и так далее. В данном разделе мы рассмотрим некоторые из этих навыков.

### Просмотр удалённых репозиториев

Для того, чтобы просмотреть список настроенных удалённых репозиториев, вы можете запустить команду **git remote**. Она выведет названия доступных удалённых репозиториев. Если вы клонировали репозиторий, то увидите как минимум origin — имя по умолчанию, которое Git даёт серверу, с которого производилось клонирование:

\$ git clone https://github.com/schacon/ticgit
Cloning into 'ticgit'...
remote: Reusing existing pack: 1857, done.
remote: Total 1857 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (1857/1857), 374.35 KiB | 268.00 KiB/s, done.
Resolving deltas: 100% (772/772), done.
Checking connectivity... done.
\$ cd ticgit
\$ git remote
origin

Вы можете также указать ключ -v, чтобы просмотреть адреса для чтения и записи, привязанные к репозиторию:

$ git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)

Если у вас больше одного удалённого репозитория, команда выведет их все. Например, для репозитория с несколькими настроенными удалёнными репозиториями в случае совместной работы нескольких пользователей, вывод команды может выглядеть примерно так:

\$ cd grit
$ git remote -v
bakkdoor  https://github.com/bakkdoor/grit (fetch)
bakkdoor  https://github.com/bakkdoor/grit (push)
cho45     https://github.com/cho45/grit (fetch)
cho45     https://github.com/cho45/grit (push)
defunkt   https://github.com/defunkt/grit (fetch)
defunkt   https://github.com/defunkt/grit (push)
koke      git://github.com/koke/grit.git (fetch)
koke      git://github.com/koke/grit.git (push)
origin    git@github.com:mojombo/grit.git (fetch)
origin    git@github.com:mojombo/grit.git (push)

Это означает, что мы можем легко получить изменения от любого из этих пользователей. Возможно, что некоторые из репозиториев доступны для записи и в них можно отправлять свои изменения, хотя вывод команды не даёт никакой информации о правах доступа.

### Добавление удалённых репозиториев

В предыдущих разделах мы уже упоминали и приводили примеры добавления удалённых репозиториев, сейчас рассмотрим эту операцию подробнее. Для того, чтобы добавить удалённый репозиторий и присвоить ему имя (shortname), просто выполните команду **git remote add shortname url**:

\$ git remote
origin
\$ git remote add pb https://github.com/paulboone/ticgit
$ git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)
pb	https://github.com/paulboone/ticgit (fetch)
pb	https://github.com/paulboone/ticgit (push)
Теперь вместо указания полного пути вы можете использовать pb. Например, если вы хотите получить изменения, которые есть у Пола, но нету у вас, вы можете выполнить команду git fetch pb:

\$ git fetch pb
remote: Counting objects: 43, done.
remote: Compressing objects: 100% (36/36), done.
remote: Total 43 (delta 10), reused 31 (delta 5)
Unpacking objects: 100% (43/43), done.
From https://github.com/paulboone/ticgit
 * [new branch]      master     -> pb/master
 * [new branch]      ticgit     -> pb/ticgit
Ветка master из репозитория Пола сейчас доступна вам под именем pb/master. Вы можете слить её с одной из ваших веток или переключить на неё локальную ветку, чтобы просмотреть содержимое ветки Пола.

### Получение изменений из удалённого репозитория — Fetch и Pull
Как вы только что узнали, для получения данных из удалённых проектов, следует выполнить:

\$ git fetch [remote-name]
Данная команда связывается с указанным удалённым проектом и забирает все те данные проекта, которых у вас ещё нет. После того как вы выполнили команду, у вас должны появиться ссылки на все ветки из этого удалённого проекта, которые вы можете просмотреть или слить в любой момент.

Когда вы клонируете репозиторий, команда clone автоматически добавляет этот удалённый репозиторий под именем «origin». Таким образом, git fetch origin извлекает все наработки, отправленные на этот сервер после того, как вы его клонировали (или получили изменения с помощью fetch). Важно отметить, что команда **git fetch** забирает данные в ваш локальный репозиторий, но не сливает их с какими-либо вашими наработками и не модифицирует то, над чем вы работаете в данный момент. Вам необходимо вручную слить эти данные с вашими, когда вы будете готовы.

Если ветка настроена на отслеживание удалённой ветки (см. следующий раздел и главу Ветвление в Git чтобы получить больше информации), то вы можете использовать команду git pull чтобы автоматически получить изменения из удалённой ветки и слить их со своей текущей. Этот способ может для вас оказаться более простым или более удобным. К тому же, по умолчанию команда git clone автоматически настраивает вашу локальную ветку master на отслеживание удалённой ветки master на сервере, с которого вы клонировали репозиторий. Название веток может быть другим и зависит от ветки по умолчанию на сервере. Выполнение git pull, как правило, извлекает (fetch) данные с сервера, с которого вы изначально клонировали, и автоматически пытается слить (merge) их с кодом, над которым вы в данный момент работаете.

Отправка изменений в удалённый репозиторий (Push)
Когда вы хотите поделиться своими наработками, вам необходимо отправить их в удалённый репозиторий. Команда для этого действия простая: **git push** remote-name branch-name. Чтобы отправить вашу ветку master на сервер origin (повторимся, что клонирование обычно настраивает оба этих имени автоматически), вы можете выполнить следующую команду для отправки ваших коммитов:

\$ git push origin master
Эта команда срабатывает только в случае, если вы клонировали с сервера, на котором у вас есть права на запись, и если никто другой с тех пор не выполнял команду push. Если вы и кто-то ещё одновременно клонируете, затем он выполняет команду push, а после него выполнить команду push попытаетесь вы, то ваш push точно будет отклонён. Вам придётся сначала получить изменения и объединить их с вашими и только после этого вам будет позволено выполнить push.

### Просмотр удалённого репозитория

Если хотите получить побольше информации об одном из удалённых репозиториев, вы можете использовать команду **git remote show remote**. Выполнив эту команду с некоторым именем, например, origin, вы получите следующий результат:

\$ git remote show origin
* remote origin
  Fetch URL: https://github.com/schacon/ticgit
  Push  URL: https://github.com/schacon/ticgit
  HEAD branch: master
  Remote branches:
    master                               tracked
    dev-branch                           tracked
  Local branch configured for 'git pull':
    master merges with remote master
  Local ref configured for 'git push':
    master pushes to master (up to date)

Она выдаёт URL удалённого репозитория, а также информацию об отслеживаемых ветках. Эта команда любезно сообщает вам, что если вы, находясь на ветке master, выполните **git pull**, ветка master с удалённого сервера будет автоматически влита в вашу сразу после получения всех необходимых данных. Она также выдаёт список всех полученных ею ссылок.

Это был пример для простой ситуации и вы наверняка встречались с чем-то подобным. Однако, если вы используете Git более интенсивно, вы можете увидеть гораздо большее количество информации от **git remote show**:

\$ git remote show origin
* remote origin
  URL: https://github.com/my-org/complex-project
  Fetch URL: https://github.com/my-org/complex-project
  Push  URL: https://github.com/my-org/complex-project
  HEAD branch: master
  Remote branches:
    master                           tracked
    dev-branch                       tracked
    markdown-strip                   tracked
    issue-43                         new (next fetch will store in remotes/origin)
    issue-45                         new (next fetch will store in remotes/origin)
    refs/remotes/origin/issue-11     stale (use 'git remote prune' to remove)
  Local branches configured for 'git pull':
    dev-branch merges with remote dev-branch
    master     merges with remote master
  Local refs configured for 'git push':
    dev-branch                     pushes to dev-branch                     (up to date)
    markdown-strip                 pushes to markdown-strip                 (up to date)
    master                         pushes to master                         (up to date)

Данная команда показывает какая именно локальная ветка будет отправлена на удалённый сервер по умолчанию при выполнении **git push**. Она также показывает, каких веток с удалённого сервера у вас ещё нет, какие ветки всё ещё есть у вас, но уже удалены на сервере, и для нескольких веток показано, какие удалённые ветки будут в них влиты при выполнении **git pull**.

### Удаление и переименование удалённых репозиториев

Для переименования удалённого репозитория можно выполнить git remote rename. Например, если вы хотите переименовать pb в paul, вы можете это сделать при помощи **git remote** rename:

\$ git remote rename pb paul
$ git remote
origin
paul

Стоит упомянуть, что это также изменит имена удалённых веток в вашем репозитории. То, к чему вы обращались как pb/master, теперь стало paul/master.

Если по какой-то причине вы хотите удалить удалённый репозиторий — вы сменили сервер или больше не используете определённое зеркало, или кто-то перестал вносить изменения — вы можете использовать **git remote rm**:

\$ git remote remove paul
$ git remote
origin

При удалении ссылки на удалённый репозиторий все отслеживаемые ветки и настройки, связанные с этим репозиторием, так же будут удалены.
______

## Создание запросов слияния (Pull Request) в Github

При подключении к работе сторонних специалистов может понадобиться функция запроса слияния *(Pull Request).* Инструмент для работы в таком формате называется DIFF. Он подчеркивает любые «чужие» изменения, чтобы владелец программы сразу видел, где код писал не он. Пометки будут доступны только после создания коммита.

## Пулл реквест

Последовательность действий:

Открыть вкладку «Pull Request».
Нажать на кнопку «Create Pull Request».
Выбрать ветку, которую следует слить с основной.
Просмотреть внесенные кодером изменения.
После изучения информации созданный запрос на слияние подтверждается нажатием «Merge Pull Request». Новый код будет импортирован в основную ветку, а созданная сторонним исполнителем может спокойно удаляться.

---
### Что такое origin 
Нашел [статью](https://www.atlassian.com/ru/git/tutorials/syncing#:~:text=%D0%92%20%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B5%20%D0%BA%D0%BB%D0%BE%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F%20%D1%81%20%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E,%D0%B8%D0%B7%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F%20%D0%B8%D0%BB%D0%B8%20%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2%D0%B0%D1%82%D1%8C%20%D0%BB%D0%BE%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5%20%D0%BA%D0%BE%D0%BC%D0%BC%D0%B8%D1%82%D1%8B.), в которой говорится следующее: 
> В процессе клонирования с помощью команды ```git clone``` автоматически создается удаленное подключение к исходному репозиторию (такое соединение называется origin). Это позволяет разработчикам, создающим локальную копию центрального репозитория, легко загружать вышестоящие изменения или публиковать локальные коммиты. Именно поэтому большинство проектов на основе Git называют свой центральный репозиторий origin.

Вызвав команду в терминале: ```git remove -v```, мы увидим наменование удаленного репозитория и его адрес.

---
### GitHub это еще и соцсеть!

Используя кнопку ```follow``` под фотографией пользователя, можно подписаться на пользователя на GitHub. Также будете получать уведомления о его общедоступной активности. Если тот, на кого вы подписаны, создает новый репозиторий, помечает репозиторий или подписывается на другого пользователя, это действие будет отображаться на панели мониторинга.  
Таким же способом, можно подписаться на организацию на GitHub.

Еще на GitHub Вы можете общаться с разработчиками по всему миру. 

---
### Что такое токен

Это альтернатива использованию паролей для аутентификации на GitHub. Создать его очень просто, вверху справа нажать на фото своего профиля, и зайти в меню ```settings```, далее меню ```<> Developer settings```, после заходим в меню ```Personal access tokens``` и открываем ```Tokens (classic)```. В открывшемся меню следует нажать кнопку ```Generate new token```. 

[Полная инструкция](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) по созданию токена. 

---

## Отчеты об ошибках
Платформа GitHub используется не только для совместной разработки, а еще и для получения обратной связи с пользователями продуктов. Так, на вкладке «Issue» любой «тестировщик» может оставить сообщение о проблемах, с которыми ему пришлось столкнуться при использовании ПО. Чтобы сделать это, нужно нажать кнопку «New issue».

После этого вносится заголовок и текст сообщения. «Проблема» отправляется нажатием на кнопку «Create new issue». Владелец ветки получает уведомления в личном кабинете или на электронную почту, указанную при регистрации.

## Заключение

Финалом разработки обычно становится выпуск определенного релиза программного продукта. Это отражается на вкладке «Releases». Здесь следует нажать на кнопку «Create New Release», указать номер версии в поле «Tag Version», внести ее название и небольшое описание. Здесь же прикрепляются архивы с компилированными файлами.

Остается нажать на «Create Release» и убедиться в публикации релиза. Ссылки на исходный код в tar.gz и zip создаются автоматически. Остальные файлы понадобится добавлять вручную.