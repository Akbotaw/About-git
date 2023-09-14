# Что такое GIT

'''
**GIT** это система контроля версий, которая помогает отслеживать изменения в проекте.
'''

## Как сделать папку репозиторием
'''
Создаем папку 
Через консоль  перейдем в ту папку и инициализируем GIT
$git init
$git status ##текущее состояние репозитория
$git add ##добавляет файлы в котором нужно отслеживать изменения 
$git commit ##сохраняем состояние 
##  Ещё раз о разнице между git add и git commit
'''
Сначала команда git add сообщает Git, какие именно файлы нужно сохранить и какую их версию. Затем с помощью команды git commit происходит само сохранение. 
Проведём ещё одну аналогию — с фотографией.
Сначала вы просите друзей встать в ряд — это команда git add. И только после того, как все заняли свои места, поправили волосы и улыбнулись, вы нажимаете кнопку и делаете снимок — это команда git commit. Сам получившийся снимок и будет коммитом. В нашем случае на этой фотографии с обратной стороны ещё есть подпись «Мой первый коммит!».

'''
$git log ##история коммитов

# Что такое GitHub

GitHub — платформа для хранения IT-проектов и совместной работы над ними с использованием Git. По сути, это сайт, куда можно загрузить файлы своего проекта для обмена с другими людьми.

'''
Git и GitHub — это два разных проекта, которые развиваются независимо друг от друга. 
Git:
- консольный инструмент для работы с локальными и удалёнными репозиториями;
- проект с открытым исходным кодом.
GitHub:
- платформа для размещения удалённых репозиториев;
- принадлежит компании Microsoft.
'''
### Как подключиться к GITHub
1.Сгенерировать SSH ключ 
2.В Github в настройках аккаунта добавить SSH ключ
3.Проверка правильности ключа через консоль:
$SSH -T git@hub.com

## Привязать удалённый репозиторий к локальному 
1.Скопировать SSH в GITHUB репозиторий 
2.Перейти в нужный файл через консоль 
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git 
$git push -u origin master ##загрузить содержимое локального репозитория на GitHub

# Файл HEAD
Файл HEAD (англ. «голова», «головной») — один из служебных файлов папки .git. Он указывает на коммит, который сделан последним (то есть на самый новый).

# Статусы untracked/tracked, staged и modified
Одна из ключевых задач Git — отслеживать изменения файлов в репозитории. Для этого каждый файл помечается каким-либо статусом. Рассмотрим основные.
untracked (англ. «неотслеживаемый»)

Мы говорили, что новые файлы в Git-репозитории помечаются как untracked, то есть неотслеживаемые. Git «видит», что такой файл существует, но не следит за изменениями в нём. У untracked-файла нет предыдущих версий, зафиксированных в коммитах или через команду git add.
staged (англ. «подготовленный»)
  После выполнения команды git add файл попадает в staging area (от англ. stage — «сцена», «этап [процесса]» и area — «область»), то есть в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии staged.
  В одном из предыдущих уроков мы сравнили коммит с фотографией. Можно развить эту аналогию и сказать, что команда git add добавляет персонажей (текущее содержимое файла или нескольких файлов) на сцену (англ. stage) для общей фотографии, а git commit делает снимок всей сцены целиком. 

tracked (англ. «отслеживаемый»)

Состояние tracked — это противоположность untracked. Оно довольно широкое по смыслу: в него попадают файлы, которые уже были зафиксированы с помощью git commit, а также файлы, которые были добавлены в staging area командой git add. То есть все файлы, в которых Git так или иначе отслеживает изменения.
modified (англ. «изменённый»)

Состояние modified означает, что Git сравнил содержимое файла с последней сохранённой версией и нашёл отличия. Например, файл был закоммичен и после этого изменён.


Файл только что создали. Git про него ещё ничего не знает. Состояние: untracked.
Файл добавили в staging area с помощью git add. Состояние: staged (+ tracked).
Возможно, изменили файл ещё раз. Состояния: staged, modified (+ tracked).
Обратите внимание: staged и modified у одного файла, но у разных его версий.
Ещё раз выполнили git add. Состояние: staged (+ tracked).
Сделали коммит с помощью git commit. Состояние: tracked.
Изменили файл. Состояние: modified (+ tracked).
Снова добавили в staging area с помощью git add. Состояния: staged (+ tracked).
Сделали коммит. Состояния: tracked.
Повторили пункты 
4
−
7
4−7 много-много раз.
Выглядит довольно запутанно! Но на практике разобраться с этим будет проще, чем кажется. Вы сможете наглядно проследить типичный жизненный цикл файла в Git в следующем уроке.