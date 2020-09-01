---
title: Приступая к работе с MySQL MongoDB, PostgreSQL, SQLite, Microsoft SQL Server или Redis, чтобы настроить базу данных в подсистеме Windows для Linux
description: Узнайте, как настроить MySQL MongoDB, PostgreSQL, SQLite, Microsoft SQL Server или Redis в подсистеме Windows для Linux.
keywords: WSL, Windows, виндовссубсистем, MySQL MongoDB, PostgreSQL, SQLite, Microsoft SQL Server, Redis, Windows 10
ms.date: 07/07/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 8ffd40ef21e8fb8ece529157852ba5d8bb676076
ms.sourcegitcommit: 16ffb1a096a4a7fbb77c58f92258051930cc82da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "86160229"
---
# <a name="get-started-with-databases-on-windows-subsystem-for-linux"></a>Начало работы с базами данных в подсистеме Windows для Linux

Это пошаговое руководство поможет приступить к подключению проекта в WSL к базе данных. Приступая к работе с MySQL, PostgreSQL, MongoDB, Redis, Microsoft SQL Server или SQLite.

## <a name="prerequisites"></a>Предварительные условия

- Использовать Windows 10 с [обновлением до версии 2004](ms-settings:windowsupdate), **сборкой 19041** или более поздней версии.
- [WSL включен и установлен и обновлен до WSL 2](https://docs.microsoft.com/windows/wsl/install-win10).
- [Дистрибутив Linux установлен](https://docs.microsoft.com/windows/wsl/install-win10#install-your-linux-distribution-of-choice) (Ubuntu 18,04 для наших примеров).
- Убедитесь, что дистрибутив Ubuntu 18,04 [работает в режиме WSL 2](https://docs.microsoft.com/windows/wsl/install-win10#set-your-distribution-version-to-wsl-1-or-wsl-2). (WSL может запускать дистрибутивы в режиме v1 или v2.) Это можно проверить, открыв PowerShell и введя следующее:`wsl -l -v`

## <a name="differences-between-database-systems"></a>Различия между системами баз данных

Наиболее [популярными вариантами](https://insights.stackoverflow.com/survey/2019#technology-_-databases) для системы базы данных являются:

- [MySQL](https://www.mysql.com/why-mysql/) (SQL)
- [PostgreSQL](https://www.postgresql.org/about/) (SQL)
- [Microsoft SQL Server](https://docs.microsoft.com/sql/?view=sql-server-ver15) (SQL)
- [SQLite](https://www.sqlite.org/about.html) (SQL)
- [MongoDB](https://www.mongodb.com/what-is-mongodb) (NoSQL)
- [Redis](https://redis.io/topics/introduction) (NoSQL)

**MySQL** — это реляционная база данных SQL с открытым исходным кодом, которая организует данные в одну или несколько таблиц, в которых типы данных могут быть связаны друг с другом. Он вертикально масштабируемый. Это означает, что один конечный компьютер выполняет свою работу. В настоящее время это наиболее широкое использование четырех систем баз данных.

**PostgreSQL** (иногда называется postgres) — это также реляционная база данных SQL с открытым исходным кодом, в которой особое внимание уделяется расширению и соответствию стандартам. Теперь она также может обрабатывать JSON, однако обычно лучше подходит для структурированных данных, вертикального масштабирования и требований ACID, таких как электронная коммерция и финансовые транзакции.

**Microsoft SQL Server** включает SQL Server в Windows, SQL Server на Linux и SQL в Azure. Это также системы управления реляционными базами данных, настроенные на серверах с основной функцией хранения и извлечения данных в соответствии с запросом программных приложений.

**SQLite** — это автономно автономная, основанная на файлах база данных с открытым исходным кодом, которая обеспечивает переносимость, надежность и высокую производительность даже в средах с нехваткой памяти.

**MongoDB** — это база данных документов NoSQL с открытым исходным кодом, предназначенная для работы с JSON и хранения данных без схемы. Это горизонтально масштабируемый. Это означает, что несколько небольших компьютеров будут выполнять свою работу. Это хорошо подходит для гибкости и неструктурированных данных, а также для кэширования аналитики в режиме реального времени.

**Redis** — это хранилище структуры данных NoSQL в памяти с открытым исходным кодом. Вместо документов используются пары "ключ-значение" для хранения. Redis известен как гибкость, производительность и широкая поддержка языка. Он достаточно гибок для использования в качестве кэша или брокера сообщений и может использовать такие структуры данных, как списки, наборы и хэши.

Выбор базы данных должен зависеть от типа приложения, с которым вы будете использовать базу данных. Мы рекомендуем вам изучить преимущества и недостатки структурированных и неструктурированных баз данных и сделать выбор в зависимости от конкретного случая использования.

## <a name="install-mysql"></a>Установка MySQL

Установка MySQL в WSL (Ubuntu 18,04):

1. Откройте терминал WSL (например, Ubuntu 18.04).
2. Обновите пакеты Ubuntu: `sudo apt update`
3. После обновления пакетов установите MySQL с помощью:`sudo apt install mysql-server`
4. Подтвердите установку и получите номер версии: `mysql --version`

Также может потребоваться запустить прилагаемый сценарий безопасности. Это изменяет некоторые менее безопасные параметры по умолчанию для таких вещей, как удаленные корневые имена входа и примеры пользователей. Чтобы запустить сценарий безопасности, выполните следующие действия.

1. Запустите сервер MySQL.`sudo /etc/init.d/mysql start`
2. Запустите запрос сценария безопасности:`sudo mysql_secure_installation`
3. В первом запросе будет указано, хотите ли вы настроить подключаемый модуль проверки пароля, который можно использовать для проверки надежности пароля MySQL. Затем вы установите пароль для привилегированного пользователя MySQL, решите, следует ли удалять анонимных пользователей, решите, следует ли разрешить вход привилегированного пользователя как локально, так и удаленно, решить, следует ли удалить тестовую базу данных, и, наконец, решить, нужно ли повторно загружать таблицы прав.

Чтобы открыть запрос MySQL, введите:`sudo mysql`

Чтобы узнать, какие базы данных доступны, в командной строке MySQL введите:`SHOW DATABASES;`

Чтобы создать новую базу данных, введите:`CREATE DATABASE database_name;`

Чтобы удалить базу данных, введите:` DROP DATABASE database_name;`

Дополнительные сведения о работе с базами данных MySQL см. в документации по [MySQL](https://dev.mysql.com/doc/mysql-getting-started/en/).

Для работы с базами данных MySQL в VS Code попробуйте [расширение MySQL](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-mysql-client2).

## <a name="install-postgresql"></a>Установка PostgreSQL

Чтобы установить PostgreSQL на WSL (Ubuntu 18,04), сделайте следующее:

1. Откройте терминал WSL (например, Ubuntu 18.04).
2. Обновите пакеты Ubuntu: `sudo apt update`
3. После обновления пакетов установите PostgreSQL (и пакет -contrib с некоторыми полезными служебными программами) с помощью команды `sudo apt install postgresql postgresql-contrib`.
4. Подтвердите установку и получите номер версии: `psql --version`

Есть 3 команды, о которых необходимо знать после установки PostgreSQL:

- `sudo service postgresql status` позволяет проверить состояние базы данных.
- `sudo service postgresql start` позволяет запустить базу данных.
- `sudo service postgresql stop` позволяет завершить работу с базой данных.

Администратору по умолчанию `postgres` требуется назначать пароль для подключения к базе данных. Чтобы задать пароль, сделайте следующее:

1. Введите команду: `sudo passwd postgres`.
2. Появится запрос на ввод нового пароля.
3. Закройте и снова откройте терминал.

Чтобы запустить PostgreSQL с помощью оболочки [psql](https://www.postgresql.org/docs/10/app-psql.html) , выполните следующие действия.

1. Запустите службу postgres: `sudo service postgresql start`
2. Подключитесь к службе postgres и откройте оболочку psql: `sudo -u postgres psql`

После успешного входа в оболочку psql вы увидите, что ваша командная строка будет выглядеть следующим образом: `postgres=#`

> [!NOTE]
> Кроме того, вы можете открыть оболочку psql, перейдя к пользователю postgres с помощью команды `su - postgres`, а затем введя команду `psql`.

Чтобы выйти из postgres = # ввод: `\q` или используйте сочетание клавиш, нажмите клавиши CTRL + D.

Чтобы узнать, какие учетные записи пользователей были созданы в установке PostgreSQL, в терминале WSL введите `psql -c "\du"` или просто `\du`, если оболочка psql открыта. Эта команда будет отображать столбцы: имя пользователя учетной записи, список атрибутов ролей и член групп ролей. Чтобы вернуться в командную строку, введите: `q`.

Дополнительные сведения о работе с базами данных PostgreSQL см. в документации по [PostgreSQL](https://www.postgresql.org/docs/13/tutorial-createdb.html).

Для работы с базами данных PostgreSQL в VS Code попробуйте использовать [расширение PostgreSQL](https://marketplace.visualstudio.com/items?itemName=ms-ossdata.vscode-postgresql).

## <a name="install-mongodb"></a>Установка MongoDB

Чтобы установить MongoDB на WSL (Ubuntu 18,04), сделайте следующее:

1. Откройте терминал WSL (например, Ubuntu 18.04).
2. Обновите пакеты Ubuntu: `sudo apt update`
3. После обновления пакетов установите MongoDB с помощью: `sudo apt-get install mongodb`
4. Подтвердите установку и получите номер версии: `mongod --version`

После установки MongoDB следует знать 3 команды:

- `sudo service mongodb status` позволяет проверить состояние базы данных.
- `sudo service mongodb start` позволяет запустить базу данных.
- `sudo service mongodb stop` позволяет завершить работу с базой данных.

> [!NOTE]
> Вы можете увидеть команду `sudo systemctl status mongodb`, используемую в учебниках или статьях. Чтобы остаться облегченным, WSL не включает `systemd` (система управления службами в Linux). Вместо этого он использует SysVinit для запуска служб на компьютере. Вы не должны заметить разницы, но если учебник рекомендует использовать `sudo systemctl`, используйте: `sudo /etc/init.d/`. Например, `sudo systemctl status mongodb`для WSL будет `sudo /etc/inid.d/mongodb status`... или вы также можете использовать `sudo service mongodb status`.

Порядок действий для запуска базы данных Mongo на локальном сервере:

1. Проверьте состояние базы данных: `sudo service mongodb status`
    Вы должны увидеть ответ [Fail], если вы еще не начали работу с базой данных.

2. Запустите базу данных. `sudo service mongodb start`
    Теперь должен отобразиться ответ [ОК].

3. Проверьте, подключившись к серверу базы данных и выполнив команду диагностики: `mongo --eval 'db.runCommand({ connectionStatus: 1 })'`
    В результате будет выведена Текущая версия базы данных, адрес и порт сервера, а также выходные данные команды Status. Значение `1` в поле "ОК" в ответе указывает на то, что сервер работает.

4. Чтобы предотвратить запуск службы MongoDB, введите: `sudo service mongodb stop`

> [!NOTE]
> MongoDB имеет несколько параметров по умолчанию, включая хранение данных в /data/db и выполнение на порте 27017. Кроме того, `mongod` является управляющей программой (хост-процессом для базы данных), а `mongo` — оболочкой командной строки, которая подключается к конкретному экземпляру `mongod`.

VS Code поддерживает работу с базами данных MongoDB с помощью [расширения Azure CosmosDB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb), вы можете создавать, управлять базами данных MongoDB и выполнять запросы из них в VS Code. Дополнительные сведения см. в VS Code документах: [Работа с MongoDB](https://code.visualstudio.com/docs/azure/mongodb).

Дополнительные сведения см. в документах MongoDB:

- [Общие сведения об использовании MongoDB](https://docs.mongodb.com/manual/introduction/)
- [Создание пользователей](https://docs.mongodb.com/manual/tutorial/create-users/)
- [Подключение к экземпляру MongoDB на удаленном узле](https://docs.mongodb.com/manual/mongo/#mongodb-instance-on-a-remote-host)
- [CRUD: создание, чтение, обновление, удаление](https://docs.mongodb.com/manual/crud/)
- [Справочные документы](https://docs.mongodb.com/manual/reference/)

## <a name="install-microsoft-sql-server"></a>Установка Microsoft SQL Server

Чтобы установить SQL Server на WSL (Ubuntu 18,04), следуйте указаниям в этом кратком руководстве: [установка SQL Server и создание базы данных на Ubuntu](https://docs.microsoft.com/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-ver15).

Для работы с Microsoft SQL Server базами данных в VS Code используйте [расширение MSSQL](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql).

## <a name="install-sqlite"></a>Установка SQLite

Установка SQLite в WSL (Ubuntu 18,04):

1. Откройте терминал WSL (например, Ubuntu 18.04).
2. Обновите пакеты Ubuntu: `sudo apt update`
3. После обновления пакетов установите SQLite3 с помощью:`sudo apt install sqlite3`
4. Подтвердите установку и получите номер версии: `sqlite3 --version`

Чтобы создать тестовую базу данных с именем example. DB, введите:`sqlite3 example.db`

Чтобы просмотреть список баз данных SQLite, введите:`.databases`

Чтобы просмотреть состояние базы данных, введите:`.dbinfo ?DB?`

Чтобы выйти из командной строки SQLite, введите:`.exit`

Дополнительные сведения о работе с базой данных SQLite см. в документации по [SQLite](https://www.sqlite.org/quickstart.html).

Для работы с базами данных SQLite в VS Code попробуйте [расширение SQLite](https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools).

## <a name="install-redis"></a>Установка Redis

Чтобы установить Redis на WSL (Ubuntu 18,04), сделайте следующее:

1. Откройте терминал WSL (например, Ubuntu 18.04).
2. Обновите пакеты Ubuntu: `sudo apt update`
3. После обновления пакетов установите Redis с помощью:`sudo apt install redis-server`
4. Подтвердите установку и получите номер версии: `redis-server --version`

Чтобы начать работу с сервером Redis, выполните следующие действия.`sudo service redis-server start`

Проверьте, работает ли Redis (Redis-CLI — служебная программа командной строки для взаимодействия с Redis): `redis-cli ping` это должно вернуть ответ "теннис".

Чтобы прерывать работу сервера Redis, выполните следующие действия.`sudo service redis-server stop`

Дополнительные сведения о работе с базой данных Redis см. в документации по [Redis](https://redis.io/topics/quickstart).

Для работы с базами данных Redis в VS Code попробуйте использовать [расширение Redis](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-redis-client).

## <a name="see-services-running-and-set-up-profile-aliases"></a>См. раздел службы запуск и настройка псевдонимов профилей.

Чтобы просмотреть службы, которые в настоящее время выполняются в дистрибутиве WSL, введите:`service --status-all`

Вводить `sudo service mongodb start` или `sudo service postgres start` и `sudo -u postgrest psql` может быть утомительно.  Однако, вы можете рассмотреть возможность установки псевдонимов в файле `.profile` на WSL, чтобы сделать эти команды более быстрыми в использовании и легкими в запоминании.

Настройка собственного пользовательского псевдонима или ярлыка для выполнения этих команд:

1. Откройте терминал WSL и введите `cd ~`, чтобы убедиться, что вы находитесь в корневом каталоге.
2. Откройте файл `.profile`, управляющий настройками терминала, в текстовом редакторе терминала Nano: `sudo nano .profile`.
3. В нижней части файла (не меняйте настройки `# set PATH`) добавьте следующее:

    ```bash
    # My Aliases
    alias start-pg='sudo service postgresql start'
    alias run-pg='sudo -u postgres psql'
    ```

    Это позволит вам ввести `start-pg` для запуска службы postgresql и `run-pg` — для открытия оболочки psql. Вы можете изменить `start-pg` и `run-pg` на любые имена, просто следите за тем, чтобы не перезаписать команду, которую postgres уже использует!

4. После добавления новых псевдонимов выйдите из текстового редактора Nano, используя **Ctrl+X** — выберите `Y` (Да) при запросе сохранения и Enter (имя файла останется `.profile`).
5. Закройте и снова откройте терминал WSL, а затем попробуйте использовать свои новые команды ввода псевдонима.

## <a name="additional-resources"></a>Дополнительные ресурсы

- [Настройка среды разработки в Windows 10](https://docs.microsoft.com/windows/dev-environment/)
