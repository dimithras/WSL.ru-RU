---
title: Заметки о выпуске подсистемы Windows для Linux
description: См. заметки о выпуске подсистемы Windows для Linux. Эти заметки о выпуске содержат исправленные проблемы и обновляются еженедельно.
keywords: заметки о выпуске, wsl, windows, подсистема windows для linux, windowssubsystem, ubuntu
author: benhillis
ms.date: 05/15/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 57d06a8666f8003b187f043bd18655a9287d8a63
ms.sourcegitcommit: fb79750bd71d6ebaed5203b3de71ba85a67227b1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88866105"
---
# <a name="release-notes-for-windows-subsystem-for-linux"></a>Заметки о выпуске подсистемы Windows для Linux

## <a name="build-20190"></a>Сборка 20190
Общие сведения о сборке Windows 20190 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2020/08/12/announcing-windows-10-insider-preview-build-20190/).

* Исправлена ошибка, препятствующая запуску экземпляров WSL1 [GH 5633].
* Исправлена ошибка с зависанием при перенаправлении выходных данных процесса Windows [GH 5648].
* Добавлен параметр %userprofile%\\.wslconfig для управления временем ожидания при простое виртуальной машины (wsl2.vmIdleTimeout=<время_в_миллисекундах>).
* Включена поддержка запуска псевдонимов выполнения приложений из WSL.
* Включена поддержка установки ядра WSL2 и дистрибутивов с помощью команды wsl.exe --install.

## <a name="build-20175"></a>Сборка 20175
Общие сведения о сборке Windows 20175 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2020/07/22/announcing-windows-10-insider-preview-build-20175/).

* В качестве выделяемого по умолчанию объема памяти виртуальной машины WSL2 теперь используется 50 % от памяти узла или 8 ГБ в зависимости от того, что меньше [GH 4166].
* Префикс \\\\wsl$ изменен на \\\\wsl для поддержки синтаксического анализа URI. Старый путь \\\\wsl$ по-прежнему поддерживается.
* В архитектуре AMD64 вложенная виртуализация для WSL2 включена по умолчанию. Вы можете отключить ее с помощью команды %userprofile%\\.wslconfig ([wsl2] nestedVirtualization=false).
* По запросу wsl.exe --update запускается Центр обновления Майкрософт.
* В DrvFs поддерживается переименование файлов, доступных только для чтения.
* Сообщения об ошибках всегда выводятся на правильной странице кода.

## <a name="build-20150"></a>Сборка 20150
Общие сведения о сборке Windows 20150 см. в [блоге о Windows](https://blogs.windows.com/windowsexperience/2020/06/17/announcing-windows-10-insider-preview-build-20150/).

* Сведения о вычислениях GPU WSL2 см. в [блоге о Windows](https://blogs.windows.com/windowsexperience/2020/06/17/announcing-windows-10-insider-preview-build-20150/).
* Добавлен параметр wsl.exe --install командной строки для быстрой настройки WSL.
* Добавлен параметр командной строки wsl.exe --update для управления обновлениями ядра WSL2. 
* Используйте WSL2 в качестве значения по умолчанию.
* Увеличено время ожидания корректного завершения работы виртуальной машины WSL2.
* Исправлено состояние гонки virtio-9p при сопоставлении памяти устройства.
* Не запускайте сервер 9p с повышенными привилегиями, если контроль учетных записей отключен.

## <a name="build-19640"></a>Сборка 19640
Общие сведения о сборке Windows 19640 см. в [блоге о Windows](https://blogs.windows.com/windowsexperience/2020/06/03/announcing-windows-10-insider-preview-build-19640/).

* [WSL2] Улучшения стабильности для virtio-9p (drvfs).

## <a name="build-19555"></a>Сборка 19555
Общие сведения о сборке Windows 19555 см. в [блоге Windows](https://blogs.windows.com/windowsexperience/2020/01/30/announcing-windows-10-insider-preview-build-19555/).

* [WSL2] Применение memory cgroup для ограничения объема памяти, используемой операциями установки и преобразования [GH 4669].
* Предоставление команды wsl.exe для улучшения обнаружения компонентов, если дополнительный компонент подсистемы Windows для Linux не включен.
* Изменение wsl.exe для вывода текста справки, если дополнительный компонент WSL не установлен.
* Устранение состояния гонки при создании экземпляров.
* Создание файла wslclient.dll, который содержит все функции командной строки.
* Предотвращение аварийного завершения при остановке службы LxssManagerUser.
* Исправление завершения работы wslapi.dll при первой ошибке, если значение параметра distroName равно NULL.

## <a name="build-19041"></a>Сборка 19041
Общие сведения о сборке Windows 19041 см. в [блоге Windows](https://blogs.windows.com/windowsexperience/2019/12/10/announcing-windows-10-insider-preview-build-19041/).

* [WSL2] Очищение маски сигналов перед запуском процессов.
* [WSL2] Обновление ядра Linux до версии 4.19.84.
* Обработка созданной символической ссылки /etc/resolv.conf, если символическая ссылка не является относительной.

## <a name="build-19028"></a>Сборка 19028
Общие сведения о сборке Windows 19028 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/11/19/announcing-windows-10-insider-preview-build-19028/).

* [WSL2] Ядро Linux обновлено до версии 4.19.81
* [WSL2] Разрешение по умолчанию /dev/net/tun изменено на 0666 [GH 4629]
* [WSL2] Объем памяти, назначенный виртуальной машине Linux по умолчанию, оптимизирован до 80 % памяти узла
* [WSL2] Внесены исправления в работу сервера взаимодействия для обработки запросов со временем ожидания, чтобы сервер не перестал отвечать на запросы из-за неправильных вызовов

## <a name="build-19018"></a>Сборка 19018
Общие сведения о сборке Windows 19018 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/11/05/announcing-windows-10-insider-preview-build-19018/).

* [WSL2] Для исправления неполадок с приложениями .NET по умолчанию используется параметр cache=mmap для подключения ресурсов 9p.
* [WSL2] Исправления для ретранслятора localhost [GH 4340].
* [WSL2] Добавлен подключаемый общедоступный ресурс tmpfs для передачи состояний между дистрибутивами.
* Исправлено восстановление постоянного сетевого диска для \\\\wsl$.

## <a name="build-19013"></a>Сборка 19013
Общие сведения о сборке Windows 19013 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/10/29/announcing-windows-10-insider-preview-build-19013/).

* [WSL2] Повышение производительности памяти служебной виртуальной машины WSL. Память, которая больше не используется, будет освобождена для узла.
* [WSL2] Ядро обновлено до версии 4.19.79. (Добавлены модули CONFIG_HIGH_RES_TIMERS, CONFIG_TASK_XACCT, CONFIG_TASK_IO_ACCOUNTING, CONFIG_SCHED_HRTICK и CONFIG_BRIDGE_VLAN_FILTERING.)
* [WSL2] Исправлен ретранслятор ввода для обработки ситуаций, когда STDIN является незакрытым обработчиком канала [GH 4424].
* При проверке наличия \\\\wsl$ не учитывается регистр.
```
[wsl2]
pageReporting = <bool>    # Enable or disable the free memory page reporting feature (default true).
idleThreshold = <integer> # Set the idle threshold for memory compaction, 0 disables the feature (default 1).
```

## <a name="build-19002"></a>Сборка 19002
Общие сведения о сборке Windows 19002 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/10/17/announcing-windows-10-insider-preview-build-19002/).

* [WSL] Устранена проблема с обработкой некоторых знаков Юникода: https://github.com/microsoft/terminal/issues/2770
* [WSL] Исправлена редко возникавшая проблема, приводившая к отмене регистрации дистрибутива, если он запускался сразу после обновления сборки новой сборкой.
* [WSL] Устранена незначительная проблема с wsl.exe --shutdown, из-за которой таймеры бездействия экземпляра не отменялись.

## <a name="build-18995"></a>Сборка 18995
Общие сведения о сборке Windows 18995 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/10/03/announcing-windows-10-insider-preview-build-18995/).

* [WSL2] Устранена проблема, из-за которой подключения DrvFs прекращали работать после прерывания операции (например, нажатия клавиш CTRL+C) [GH 4377].
* [WSL2] Исправлена обработка очень больших сообщений hvsocket [GH 4105].
* [WSL2] Устранена проблема с взаимодействием, возникавшая, если в качестве stdin использовался файл [GH 4475].
* [WSL2] Устранено аварийное завершение службы при обнаружении непредвиденного состояния сети [GH 4474].
* [WSL2] Запрос имени дистрибутива с сервера взаимодействия, если текущий процесс не имеет переменной среды.
* [WSL2] Устранена проблема с взаимодействием, возникавшая, если в качестве stdin использовался файл.
* [WSL2] Ядро Linux обновлено до версии 4.19.72.
* [WSL2] Добавлена возможность указать дополнительные параметры командной строки ядра с помощью wslconfig.
```
[wsl2]
kernelCommandLine = <string> # Additional kernel command line arguments
```

## <a name="build-18990"></a>Сборка 18990
Общие сведения о сборке Windows 18990 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/09/24/announcing-windows-10-insider-preview-build-18990/).

* Ускорен вывод списка каталогов в \\\\wsl$.
* [WSL2] Внедрена дополнительная энтропия загрузки [GH 4416].
* [WSL2] Исправлено взаимодействие с Windows при использовании su или sudo [GH 4465].

## <a name="build-18980"></a>Сборка 18980
Общие сведения о сборке Windows 18980 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/09/11/announcing-windows-10-insider-preview-build-18980/).

* Исправлено чтение символических ссылок, которые запрещают FILE_READ_DATA. Сюда входят все символические ссылки Windows, создаваемые для обеспечения обратной совместимости, такие как "C:\Document and Settings", а также множество символических ссылок в каталоге профиля пользователя.
* Непредвиденное состояние файловой системы перестало быть неустранимым [GH 4334, 4305].
* [WSL2] Добавлена поддержка arm64, если ЦП или встроенное ПО поддерживает виртуализацию.
* [WSL2] Непривилегированным пользователям разрешено просматривать журнал ядра.
* [WSL2] Исправлена ретрансляция вывода при закрытии сокетов stdout и stderr [GH 4375].
* [WSL2] Поддержка сквозного режима батареи и адаптера питания.
* [WSL2] Ядро Linux обновлено до версии 4.19.67.
* Добавлена возможность задать имя пользователя по умолчанию в /etc/wsl.conf:
```
[user]
default=<string>
```

## <a name="build-18975"></a>Сборка 18975
Общие сведения о сборке Windows 18975 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/09/06/announcing-windows-10-insider-preview-build-18975/).

* [WSL2] Исправлен ряд проблем с надежностью localhost [GH 4340].

## <a name="build-18970"></a>Сборка 18970
Общие сведения о сборке Windows 18970 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/08/29/announcing-windows-10-insider-preview-build-18970/).

* [WSL2] Синхронизация времени с временем узла при выходе системы из спящего режима [GH 4245].
* [WSL2] Создание символических ссылок NT на тома Windows, если это возможно.
* [WSL2] Создание дистрибутивов в пространствах имен UTS, IPC, PID и Mount.
* [WSL2] Исправлена ретрансляция портов localhost при привязке сервера к localhost напрямую [GH 4353].
* [WSL2] Исправлено взаимодействие при перенаправлении вывода [GH 4337].
* [WSL2] Поддержка преобразования абсолютных символических ссылок NT.
* [WSL2] Ядро обновлено до версии 4.19.59.
* [WSL2] Правильное задание маски подсети для eth0.
* [WSL2] Изменение логики для выхода из циклов консольного рабочего процесса при получении сигнала о событии выхода.
* [WSL2] Если дистрибутив не работает, то его VHD-файл можно извлечь.
* [WSL2] Исправлена библиотека анализа конфигурации, чтобы правильно обрабатывать пустые значения.
* [WSL2] Поддержка рабочего стола Docker путем создания подключений между дистрибутивами. Дистрибутив можно настроить для такого режима, добавив следующую строку в файл /etc/wsl.conf:
```
[automount]
crossDistro = true
```

## <a name="build-18945"></a>Сборка 18945
Общие сведения о сборке Windows 18945 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/07/26/announcing-windows-10-insider-preview-build-18945/).

### <a name="wsl"></a>WSL
* [WSL2] Разрешен доступ к ожидающим передачи данных TCP-сокетам в WSL2 с узла по адресу localhost:<порт>.
* [WSL2] Устранены сбои при установке и преобразовании. Добавлена дополнительная диагностика для отслеживания будущих проблем [GH 4105]. 
* [WSL2] Улучшена диагностируемость проблем с сетью WSL2.
* [WSL2] Ядро обновлено до версии 4.19.55.
* [WSL2] Ядро обновлено с помощью параметров конфигурации, необходимых для Docker [GH 4165].
* [WSL2] Увеличено число ЦП, назначаемых упрощенной служебной виртуальной машине, чтобы оно совпадало с числом ЦП узла (ранее это значение было ограничено 8 ЦП с помощью параметра CONFIG_NR_CPUS в конфигурации ядра) [GH 4137].
* [WSL2] Создание файла подкачки для упрощенной виртуальной машины WSL2.
* [WSL2] Разрешено отображение подключений пользователей в \\\\wsl$\\<имя_дистрибутива> (например, sshfs) [GH 4172].
* [WSL2] Повышена производительность файловой системы 9p.
* [WSL2] Предотвращение неограниченного роста списка ACL виртуального жесткого диска [GH 4126].
* [WSL2] Обновлена конфигурации ядра для поддержки squashfs и xt_conntrack [GH 4107, 4123].
* [WSL2] Исправлен параметр interop.enabled в /etc/wsl.conf [GH 4140].
* [WSL2] Если файловая система не поддерживает EA, возвращается ENOTSUP.
* [WSL2] CopyFile больше не прекращает отвечать на запросы при работе с \\\\wsl$.
* Параметр umask по умолчанию переключен на значение 0022, и добавлен параметр filesystem.umask в /etc/wsl.conf.
* Исправлен wslpath, чтобы правильно разрешать символические ссылки, что повторно происходило в 19h1 [GH 4078].
* Введен файл %UserProfile%\\.wslconfig для настройки параметров WSL2.
```
[wsl2]
kernel=<path>              # An absolute Windows path to a custom Linux kernel.
memory=<size>              # How much memory to assign to the WSL2 VM.
processors=<number>        # How many processors to assign to the WSL2 VM.
swap=<size>                # How much swap space to add to the WSL2 VM. 0 for no swap file.
swapFile=<path>            # An absolute Windows path to the swap vhd.
localhostForwarding=<bool> # Boolean specifying if ports bound to wildcard or localhost in the WSL2 VM should be connectable from the host via localhost:port (default true).

# <path> entries must be absolute Windows paths with escaped backslashes, for example C:\\Users\\Ben\\kernel
# <size> entries must be size followed by unit, for example 8GB or 512MB
```

## <a name="build-18917"></a>Сборка 18917
Общие сведения о сборке Windows 18917 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/06/12/announcing-windows-10-insider-preview-build-18917/).

### <a name="wsl"></a>WSL
* Уже доступна версия WSL 2! Дополнительные сведения см. в [блоге](https://devblogs.microsoft.com/commandline/wsl-2-is-now-available-in-windows-insiders/).
* Устранена регрессия, из-за которой запуск процессов Windows через символические ссылки выполнялся некорректно [GH 3999].
* Добавлены следующие параметры wsl.exe: wsl.exe --list --verbose, wsl.exe --list --quiet и wsl.exe --import --version.
* Добавлен параметр wsl.exe --shutdown.
* Plan 9: для успешной работы разрешено открытие каталога для записи.

## <a name="build-18890"></a>Сборка 18890
Общие сведения о сборке Windows 18890 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/05/01/announcing-windows-10-insider-preview-build-18890/).

### <a name="wsl"></a>WSL
* Утечка сокетов не блокирует работу [GH 2913].
* Ввод EOF в терминал может заблокировать последующие операции чтения [GH 3421].
* В заголовок resolv.conf добавлена ссылка на wsl.conf [рассмотрено в GH 3928].
* Взаимоблокировка в коде epoll delete [GH 3922].
* Обработка пробелов в аргументах параметров --import и --export [GH 3932].
* Расширение файлов, обработанных с помощью mmap, не работает должным образом [GH 3939].
* Устранена проблема с доступом ARM64 к \\\\wsl$.
* Улучшен значок по умолчанию для wsl.exe.

## <a name="build-18342"></a>Сборка 18342
Общие сведения о сборке Windows 18342 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/02/20/announcing-windows-10-insider-preview-build-18342/).

### <a name="wsl"></a>WSL
* Мы добавили возможность доступа пользователей к файлам Linux в дистрибутиве WSL из Windows. Доступ к этим файлам можно получить с помощью командной строки. Кроме того, такие приложения для Windows, как проводник, VSCode и т. д., могут взаимодействовать с этими файлами. Чтобы получить доступ к файлам, перейдите в папку \\\\wsl$\\<имя_дистрибутива>, или просмотрите список выполняющихся дистрибутивов, перейдя в \\\\wsl$.
* Добавлены дополнительные теги сведений о ЦП и исправлены значения Cpus_allowed[_list] [GH 2234].
* Поддержка выполнения из ведомого потока [GH 3800].
* Ошибки обновления конфигурации не считаются критическими [GH 3785].
* Подсистема binfmt обновлена для правильной обработки смещений [GH 3768].
* Включено сопоставление сетевых дисков для Plan 9 [GH 3854].
* Поддержка преобразования путей Windows в Linux и наоборот для подключения привязок.
* Создание разделов только для чтения для сопоставлений файлов, открытых только для чтения.

## <a name="build-18334"></a>Сборка 18334
Общие сведения о сборке Windows 18334 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2019/02/08/announcing-windows-10-insider-preview-build-18334/).

### <a name="wsl"></a>WSL
* Перепроектирован способ сопоставления часового пояса Windows с часовым поясом Linux [GH 3747].
* Устранены утечки памяти и добавлены новые функции преобразования строк [GH 3746].
* Выполнение SIGCONT для группы потоков без потоков является холостой командой [GH 3741]. 
* Правильное отображение дескрипторов файлов socket и epoll в /proc/self/fd.

## <a name="build-18305"></a>Сборка 18305
Общие сведения о сборке Windows 18305 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/12/19/announcing-windows-10-insider-preview-build-18305/).

### <a name="wsl"></a>WSL
* Когда основной поток завершает работу, pthreads утрачивает доступ к файлам [GH 3589].
* Команда TIOCSCTTY должна игнорировать параметр force, если он не является обязательным [GH 3652].
* Усовершенствована командная строка wsl.exe и добавлены функции импорта и экспорта.
```
Usage: wsl.exe [Argument] [Options...] [CommandLine]

Arguments to run Linux binaries:

    If no command line is provided, wsl.exe launches the default shell.

    --exec, -e <CommandLine>
        Execute the specified command without using the default Linux shell.

    --
        Pass the remaining command line as is.

Options:
    --distribution, -d <DistributionName>
        Run the specified distribution.

    --user, -u <UserName>
        Run as the specified user.

Arguments to manage Windows Subsystem for Linux:

    --export <DistributionName> <FileName>
        Exports the distribution to a tar file.
        The filename can be - for standard output.

    --import <DistributionName> <InstallLocation> <FileName>
        Imports the specified tar file as a new distribution.
        The filename can be - for standard input.

    --list, -l [Options]
        Lists distributions.

        Options:
            --all
                List all distributions, including distributions that are currently
                being installed or uninstalled.

            --running
                List only distributions that are currently running.

    -setdefault, -s <DistributionName>
        Sets the distribution as the default.

    --terminate, -t <DistributionName>
        Terminates the distribution.

    --unregister <DistributionName>
        Unregisters the distribution.

    --upgrade <DistributionName>
        Upgrades the distribution to the WslFs file system format.

    --help
        Display usage information.
```

## <a name="build-18277"></a>Сборка 18277
Общие сведения о сборке Windows 18277 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/11/07/announcing-windows-10-insider-preview-build-18277/).

### <a name="wsl"></a>WSL
* Устранена ошибка "Интерфейс не поддерживается" в сборке 18272 [GH 3645].
* Игнорируется флаг MNT_FORCE для umount syscall [GH 3605].
* Переключено взаимодействие WSL для использования официального API CreatePseudoConsole.
* При перезапуске FUTEX_WAIT значение времени ожидания не сохраняется.

## <a name="build-18272"></a>Сборка 18272
Общие сведения о сборке Windows 18272 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/10/31/announcing-windows-10-insider-preview-build-18272/).

### <a name="wsl"></a>WSL
* **Предупреждение**. В этой сборке есть проблема, делающая компонент WSL неработоспособным. При попытке запустить дистрибутив появится сообщение об ошибке "Интерфейс не поддерживается". Эта проблема устранена, и соответствующее исправление будет добавлено в сборку для предварительной оценки с ранним доступом, выпускаемую на следующей неделе. Если вы установили эту сборку, можно вернуться к предыдущей сборке Windows, выбрав "Параметры" > "Обновление и безопасность" > "Восстановление" и щелкнув "Вернуться к предыдущей версии Windows 10".

## <a name="build-18267"></a>Сборка 18267
Общие сведения о сборке Windows 18267 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/10/24/announcing-windows-10-insider-preview-build-18267/).

### <a name="wsl"></a>WSL
* Устранена проблема, из-за которой зомби-процесс мог быть не удален и существовал неограниченное время.
* WslRegisterDistribution переставал отвечать на запросы, если сообщение об ошибке превышало максимальную длину [GH 3592].
* Разрешено использование fsync с файлами только для чтения в DrvFs [GH 3556].
* Перед созданием символических ссылок в каталогах /bin и /sbin убедитесь, что эти каталоги существуют [GH 3584].
* Добавлен механизм времени ожидания завершения экземпляра для экземпляров WSL. Сейчас время ожидания равно 15 секундам, то есть работа экземпляра завершается через 15 секунд после завершения последнего процесса WSL. Чтобы немедленно завершить дистрибутив, используйте следующую команду.
```
wslconfig.exe /terminate <DistributionName>
```

## <a name="build-17763-1809"></a>Сборка 17763 (1809)
Общие сведения о сборке Windows 17763 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).

### <a name="wsl"></a>WSL
* Проверка разрешения SetPriority для syscall была слишком строгая для изменения приоритета того же потока [GH 1838].
* Убедитесь, что для времени загрузки используется несмещенное время прерывания, чтобы избежать возврата отрицательных значений clock_gettime (CLOCK_BOOTTIME) [GH 3434].
* Обработка символических ссылок в интерпретаторе binfmt для WSL [GH 3424].
* Улучшена обработка очистки дескриптора файла ведущего потока группы потоков.
* Чтобы избежать переполнения, переключите WSL на использование KeQueryInterruptTimePrecise вместо KeQueryPerformanceCounter [GH 3252].
* Подключение Ptrace могло вызывать неправильное возвращаемое значение из системных вызовов [GH 1731].
* Устранено несколько проблем, связанных с AF_UNIX [GH 3371].
* Устранена проблема, которая могла привести к сбою взаимодействия WSL, если длина текущего рабочего каталога была меньше 5 знаков [GH 3379].
* Предотвращена задержка в 1 секунду при сбое замыкания на себя подключений к несуществующим портам (GH 3286).
* Добавлен файл заглушки /proc/sys/fs/file-max [GH 2893].
* Уточнены сведения об области действия IPv6.
* Поддержка PR_SET_PTRACER [GH 3053].
* Канальная файловая система необоснованно очищала событие epoll, активируемое переходом [GH 3276].
* Исполняемый файл Win32, запущенный с помощью символической ссылки NTFS, не учитывал имя символической ссылки [GH 2909].
* Улучшена поддержка зомби [GH 1353].
* Добавлены записи wsl.conf для управления поведением взаимодействия с Windows [GH 1493].
  ```
    [interop]

    enabled=false # enable launch of Windows binaries; default is true

    appendWindowsPath=false # append Windows path to $PATH variable; default is true
  ```
* Устранена проблема, из-за которой команда getsockname не всегда возвращала тип семейства сокетов UNIX [GH 1774].
* Добавлена поддержка TIOCSTI [GH 1863].
* Неблокирующие сокеты в процессе подключения должны возвращать EAGAIN для попыток записи [GH 2846].
* Поддержка взаимодействия с подключенными виртуальными жесткими дисками [GH 3246, 3291].
* Устранена проблема с проверкой разрешений для корневой папки [GH 3304].
* Ограниченная поддержка вызовов ioctl с аргументами KDGKBTYPE, KDGKBMODE и KDSKBMODE для клавиатуры tty.
* Приложения пользовательского интерфейса Windows должны выполняться, даже если они запущены в фоновом режиме.
* Добавлен параметр wsl --u или --user [GH 1203].
* Устранены проблемы с запуском WSL, когда включен быстрый запуск [GH 2576].
* Сокеты UNIX должны хранить учетные данные отключенных одноранговых узлов [GH 3183].
* Работа неблокирующих сокетов UNIX неограниченное время завершалась сбоем и возвращалось значение EAGAIN [GH 3191].
* Новый тип подключения drvfs по умолчанию case=off [GH 2937, 3212, 3328].
    * Дополнительные сведения см. в [этом блоге](https://blogs.msdn.microsoft.com/commandline/2018/06/14/improved-per-directory-case-sensitivity-support-in-wsl/).
* Добавлен параметр wslconfig /terminate для остановки выполнения дистрибутивов.
* Устранена проблема с пунктами в контекстном меню оболочки WSL, из-за которой неправильно обрабатывались пути с пробелами.
* Учет регистра в именах каталогов реализован в качестве расширенного атрибута.
* ARM64: имитация операций обслуживания кэша. Устранена [проблема с dotnet](https://github.com/dotnet/core/issues/1561).
* DrvFs: в частном диапазоне допускаются только неэкранированные знаки, которые соответствуют экранированному знаку.
* Устранена ошибка завышения или занижения на единицу при проверке длины интерпретатором анализатора ELF [GH 3154].
* Абсолютные таймеры WSL со временем в прошлом не срабатывали [GH 3091].
* Убедитесь, что вновь созданные точки повторного анализа указаны как таковые в родительском каталоге.
* Атомарное создание каталогов с учетом регистра в DrvFs.
* Устранена дополнительная проблема, из-за которой многопоточные операции могли возвращать ENOENT, даже если файл существовал. [GH 2712]
* Устранена ошибка запуска WSL при включенном режиме UMCI. [GH 3020]
* Добавлено контекстное меню обозревателя для запуска WSL [GH 437, 603, 1836]. Чтобы открыть его, нажмите и удерживайте клавишу SHIFT и щелкните правой кнопкой мыши в окне проводника.
* Устранено неблокирующее поведение сокетов UNIX [GH 2822, 3100].
* Устранена проблема, из-за которой команда NETLINK переставала отвечать на запросы, как было сообщено в GH 2026.
* Добавлена поддержка флагов распространения подключения [GH 2911].
* Устранена проблема, из-за которой усечение не вызывало события inotify [GH 2978].
* Добавлен параметр --exec для wsl.exe, позволяющий вызвать отдельный двоичный файл без оболочки.
* Добавлен параметр --distribution для wsl.exe, позволяющий выбрать конкретный дистрибутив.
* Ограниченная поддержка dmesg. Теперь приложения могут входить в dmesg. Драйвер WSL записывает ограниченные сведения в dmesg. В будущем эти возможности можно будет расширить, чтобы записывать другие сведения и данные диагностики из драйвера.
    * Примечание. Сейчас dmesg поддерживается через интерфейс устройства `/dev/kmsg`. Интерфейс syscall `syslog` пока не поддерживается. Поэтому некоторые параметры командной строки `dmesg`, такие как `-S` и `-C`, не работают.
* Изменены GID и режим по умолчанию для последовательных устройств, чтобы обеспечить соответствие собственному режиму [GH 3042].
* Теперь DrvFs поддерживает расширенные атрибуты.
    * Примечание. В DrvFs были некоторые ограничения для имен расширенных атрибутов. Некоторые знаки (например, "/", ":" и "\*") не допускаются, а в именах расширенных атрибутов в DrvFs не учитывается регистр.

## <a name="build-18252-skip-ahead"></a>Сборка 18252 (Skip Ahead)
Общие сведения о сборке Windows 18252 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/10/03/announcing-windows-10-insider-preview-build-18252/).

### <a name="wsl"></a>WSL
* Двоичные файлы init и bsdtar перемещены из библиотеки DLL lxssmanager в отдельную папку tools.
* Устранено состязание при закрытии дескриптора файла в случае использования CLONE_FILES.
* Обработка необязательных полей в /proc/pid/mountinfo при преобразовании путей DrvFs.
* Допускается успешное выполнение mknod DrvFs без поддержки метаданных для S_IFREG.
* Файлы только для чтения, созданные в DrvFs, должны иметь атрибут readonly [GH 3411].
* Добавлено вспомогательное приложение /sbin/mount.drvfs для управления подключением DrvFs.
* Использование переименования POSIX в DrvFs.
* Разрешено преобразование путей в томах без GUID тома.

## <a name="build-17738-fast"></a>Сборка 17738 (Fast)
Общие сведения о сборке Windows 17738 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/08/14/announcing-windows-10-insider-preview-build-17738/).

### <a name="wsl"></a>WSL
* Проверка разрешения SetPriority для syscall была слишком строгая для изменения приоритета того же потока [GH 1838].
* Убедитесь, что для времени загрузки используется несмещенное время прерывания, чтобы избежать возврата отрицательных значений clock_gettime (CLOCK_BOOTTIME) [GH 3434].
* Обработка символических ссылок в интерпретаторе binfmt для WSL [GH 3424].
* Улучшена обработка очистки дескриптора файла ведущего потока группы потоков.

## <a name="build-17728-fast"></a>Сборка 17728 (Fast)
Общие сведения о сборке Windows 17728 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/07/31/announcing-windows-10-insider-preview-build-17728/).

### <a name="wsl"></a>WSL
* Чтобы избежать переполнения, переключите WSL на использование KeQueryInterruptTimePrecise вместо KeQueryPerformanceCounter [GH 3252].
* Подключение Ptrace могло вызывать неправильное возвращаемое значение из системных вызовов [GH 1731].
* Устранен ряд проблем, связанных с AF_UNIX [GH 3371].
* Устранена проблема, которая могла привести к сбою взаимодействия WSL, если длина текущего рабочего каталога была меньше 5 знаков [GH 3379].

## <a name="build-18204-skip-ahead"></a>Сборка 18204 (Skip Ahead)
Общие сведения о сборке Windows 18204 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/07/25/announcing-windows-10-insider-preview-build-17723-and-build-18204/).

### <a name="wsl"></a>WSL
* Канальная файловая система необоснованно очищала событие epoll, активируемое переходом [GH 3276].
* Исполняемый файл Win32, запущенный с помощью символической ссылки NTFS, не учитывал имя символической ссылки [GH 2909].

## <a name="build-17723-fast"></a>Сборка 17723 (Fast)
Общие сведения о сборке Windows 17723 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/07/25/announcing-windows-10-insider-preview-build-17723-and-build-18204/).

### <a name="wsl"></a>WSL
* Предотвращена задержка в 1 секунду при сбое замыкания на себя подключений к несуществующим портам (GH 3286).
* Добавлен файл заглушки /proc/sys/fs/file-max [GH 2893].
* Уточнены сведения об области действия IPv6.
* Поддержка PR_SET_PTRACER [GH 3053].
* Канальная файловая система необоснованно очищала событие epoll, активируемое переходом [GH 3276].
* Исполняемый файл Win32, запущенный с помощью символической ссылки NTFS, не учитывал имя символической ссылки [GH 2909].

## <a name="build-17713"></a>Сборка 17713
Общие сведения о сборке Windows 17713 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/07/11/announcing-windows-10-insider-preview-build-17713/).

### <a name="wsl"></a>WSL
* Улучшена поддержка зомби [GH 1353].
* Добавлены записи wsl.conf для управления поведением взаимодействия с Windows [GH 1493].
  ```
    [interop]

    enabled=false # enable launch of Windows binaries; default is true

    appendWindowsPath=false # append Windows path to $PATH variable; default is true
  ```
* Устранена проблема, из-за которой команда getsockname не всегда возвращала тип семейства сокетов UNIX [GH 1774].
* Добавлена поддержка TIOCSTI [GH 1863].
* Неблокирующие сокеты в процессе подключения должны возвращать EAGAIN для попыток записи [GH 2846].
* Поддержка взаимодействия с подключенными виртуальными жесткими дисками [GH 3246, 3291].
* Устранена проблема с проверкой разрешений для корневой папки [GH 3304].
* Ограниченная поддержка вызовов ioctl с аргументами KDGKBTYPE, KDGKBMODE и KDSKBMODE для клавиатуры tty.
* Приложения пользовательского интерфейса Windows должны выполняться, даже если они запущены в фоновом режиме.

## <a name="build-17704"></a>Сборка 17704
Общие сведения о сборке Windows 17704 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/06/27/announcing-windows-10-insider-preview-build-17704/).

### <a name="wsl"></a>WSL
* Добавлен параметр wsl --u или --user [GH 1203].
* Устранены проблемы с запуском WSL, когда включен быстрый запуск [GH 2576].
* Сокеты UNIX должны хранить учетные данные отключенных одноранговых узлов [GH 3183].
* Работа неблокирующих сокетов UNIX неограниченное время завершалась сбоем и возвращалось значение EAGAIN [GH 3191].
* Новый тип подключения drvfs по умолчанию case=off [GH 2937, 3212, 3328].
    * Дополнительные сведения см. в [этом блоге](https://blogs.msdn.microsoft.com/commandline/2018/06/14/improved-per-directory-case-sensitivity-support-in-wsl/).
* Добавлен параметр wslconfig /terminate для остановки выполнения дистрибутивов.

## <a name="build-17692"></a>Сборка 17692
Общие сведения о сборке Windows 17692 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/06/14/announcing-windows-10-insider-preview-build-17692).

### <a name="wsl"></a>WSL
* Устранена проблема с пунктами в контекстном меню оболочки WSL, из-за которой неправильно обрабатывались пути с пробелами.
* Учет регистра в именах каталогов реализован в качестве расширенного атрибута.
* ARM64: имитация операций обслуживания кэша. Устранена [проблема с dotnet](https://github.com/dotnet/core/issues/1561).
* DrvFs: в частном диапазоне допускаются только неэкранированные знаки, которые соответствуют экранированному знаку.

## <a name="build-17686"></a>Сборка 17686
Общие сведения о сборке Windows 17686 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/06/06/announcing-windows-10-insider-preview-build-17686).

### <a name="wsl"></a>WSL
* Устранена ошибка завышения или занижения на единицу при проверке длины интерпретатором анализатора ELF [GH 3154].
* Абсолютные таймеры WSL со временем в прошлом не срабатывали [GH 3091].
* Убедитесь, что вновь созданные точки повторного анализа указаны как таковые в родительском каталоге.
* Атомарное создание каталогов с учетом регистра в DrvFs.

## <a name="build-17677"></a>Сборка 17677
Общие сведения о сборке Windows 17677 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/05/24/announcing-windows-10-insider-preview-build-17677/).

### <a name="wsl"></a>WSL
* Устранена дополнительная проблема, из-за которой многопоточные операции могли возвращать ENOENT, даже если файл существовал. [GH 2712]
* Устранена ошибка запуска WSL при включенном режиме UMCI. [GH 3020]

## <a name="build-17666"></a>Сборка 17666
Общие сведения о сборке Windows 17666 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/05/09/announcing-windows-10-insider-preview-build-17666/).

### <a name="wsl"></a>WSL
#### <a name="warning-there-is-an-issue-preventing-wsl-from-running-on-some-amd-chipsets-gh-3134-a-fix-is-ready-and-making-its-way-to-the-insider-build-branch"></a>ПРЕДУПРЕЖДЕНИЕ! Существует проблема, препятствующая запуску WSL на некоторых наборах микросхем AMD [GH 3134]. Исправление готово и находится в процессе добавления в ветвь сборок для программы предварительной оценки Windows.
* Добавлено контекстное меню обозревателя для запуска WSL [GH 437, 603, 1836]. Чтобы открыть его, нажмите и удерживайте клавишу SHIFT и щелкните правой кнопкой мыши в окне проводника.
* Устранено неблокирующее поведение сокетов UNIX [GH 2822, 3100].
* Устранена проблема, из-за которой команда NETLINK переставала отвечать на запросы, как было сообщено в GH 2026.
* Добавлена поддержка флагов распространения подключения [GH 2911].
* Устранена проблема, из-за которой усечение не вызывало события inotify [GH 2978].
* Добавлен параметр --exec для wsl.exe, позволяющий вызвать отдельный двоичный файл без оболочки.
* Добавлен параметр --distribution для wsl.exe, позволяющий выбрать конкретный дистрибутив.

## <a name="build-17655-skip-ahead"></a>Сборка 17655 (Skip Ahead)
Общие сведения о сборке Windows 17655 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/04/25/announcing-windows-10-insider-preview-build-17655-for-skip-ahead/).

### <a name="wsl"></a>WSL
* Ограниченная поддержка dmesg. Теперь приложения могут входить в dmesg. Драйвер WSL записывает ограниченные сведения в dmesg. В будущем эти возможности можно будет расширить, чтобы записывать другие сведения и данные диагностики из драйвера.
    * Примечание. Сейчас dmesg поддерживается через интерфейс устройства `/dev/kmsg`. Интерфейс sycall `syslog` еще не поддерживается. Поэтому некоторые параметры командной строки `dmesg`, такие как `-S` и `-C`, не работают.
* Устранена проблема, из-за которой многопоточные операции могли возвращать ENOENT, даже если файл существовал. [GH 2712]

## <a name="build-17639-skip-ahead"></a>Сборка 17639 (Skip Ahead)
Общие сведения о сборке Windows 17639 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/04/04/announcing-windows-10-insider-preview-build-17639-for-skip-ahead/).

### <a name="wsl"></a>WSL
* Изменены GID и режим по умолчанию для последовательных устройств, чтобы обеспечить соответствие собственному режиму [GH 3042].
* Теперь DrvFs поддерживает расширенные атрибуты.
    * Примечание. В DrvFs были некоторые ограничения для имен расширенных атрибутов. В частности, некоторые знаки (например, "/", ":" и "\*") не допускаются, а в именах расширенных атрибутов в DrvFs не учитывается регистр.

## <a name="build-17133-fast"></a>Сборка 17133 (Fast)
Общие сведения о сборке Windows 17133 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/03/27/announcing-windows-10-insider-preview-build-17133-for-fast/).

### <a name="wsl"></a>WSL
* Устранено прекращение ответа на запросы в WSL. [GH 3039, 3034]

## <a name="build-17128-fast"></a>Сборка 17128 (Fast)
Общие сведения о сборке Windows 17128 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/03/23/announcing-windows-10-insider-preview-build-17128-for-fast/).

### <a name="wsl"></a>WSL
* Нет

## <a name="build-17627-skip-ahead"></a>Сборка 17627 (Skip Ahead)
Общие сведения о сборке Windows 17627 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/03/21/announcing-windows-10-insider-preview-build-17627-for-skip-ahead/).

### <a name="wsl"></a>WSL
* Добавлена поддержка фьютексных операций с поддержкой числа пи. [GH 1006]
    * Обратите внимание на то, что приоритеты в настоящее время не поддерживаются компонентом WSL, так что существуют ограничения, но стандартное использование должно быть доступно.
* Поддержка брандмауэра Windows для процессов WSL. [GH 1852]
    * Например, чтобы разрешить процессу Python в WSL ожидать передачи данных через какой-либо порт, используйте командную строку Windows с повышенными привилегиями: ```netsh.exe advfirewall firewall add rule name=wsl_python dir=in action=allow program="C:\users\<username>\appdata\local\packages\canonicalgrouplimited.ubuntuonwindows_79rhkp1fndgsc\localstate\rootfs\usr\bin\python2.7" enable=yes```
    * Дополнительные сведения о добавлении правил брандмауэра доступны по [этой ссылке](https://support.microsoft.com/help/947709/how-to-use-the-netsh-advfirewall-firewall-context-instead-of-the-netsh).
* При использовании wsl.exe учитывается оболочка по умолчанию пользователя. [GH 2372]
* Все сетевые интерфейсы отображаются как Ethernet. [GH 2996]
* Улучшена обработка поврежденного файла /etc/passwd. [GH 3001]

### <a name="console"></a>Консоль
* Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17618-skip-ahead"></a>Сборка 17618 (Skip Ahead)
Общие сведения о сборке Windows 17618 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/03/07/announcing-windows-10-insider-preview-build-17618-skip-ahead/).

### <a name="wsl"></a>WSL
* Введена функция псевдоконсоли для взаимодействия с NT [GH 988, 1366, 1433, 1542, 2370, 2406].
* Устаревший механизм установки (lxrun.exe) является нерекомендуемым. Для установки дистрибутивов используется Microsoft Store.

### <a name="console"></a>Консоль
* Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17110"></a>Сборка 17110
Общие сведения о сборке Windows 17110 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/02/27/announcing-windows-10-insider-preview-build-17110-fast/).

### <a name="wsl"></a>WSL
* Разрешено завершение /init из Windows [GH 2928].
* Теперь DrvFs по умолчанию учитывает регистр в имени отдельно для каждого каталога (аналогично параметру подключения case=dir).
    * Для использования параметра case=force (прежнее поведение) требуется задать раздел реестра. Выполните следующую команду, чтобы включить режим case=force, если его необходимо использовать: reg add HKLM\SYSTEM\CurrentControlSet\Services\lxss /v DrvFsAllowForceCaseSensitivity /t REG_DWORD /d 1
    * Если у вас есть каталоги, созданные с помощью WSL в более ранней версии Windows, в которых должен учитываться регистр, используйте fsutil.exe, чтобы пометить их как каталоги с учетом регистра: fsutil.exe file setcasesensitiveinfo <path> enable
* Строки, возвращаемые из uname syscall, завершаются значением NULL.

### <a name="console"></a>Консоль
* Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17107"></a>Сборка 17107
Общие сведения о сборке Windows 17107 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/02/23/announcing-windows-10-insider-preview-build-17107-fast-ring/).

### <a name="wsl"></a>WSL
* Поддержка TCSETSF и TCSETSW на главных конечных точках PTY [GH 2552].
* Запуск одновременных процессов взаимодействия мог привести к возвращению EINVAL [GH 2813].
* Устранена проблема с PTRACE_ATTACH для отображения правильного состояния трассировки в /proc/pid/status.
* Устранено состязание, когда кратковременные процессы, клонированные с флагами CLEARTID и SETTID, могли завершиться без очистки адреса TID.
* Отображается сообщение, если при переходе со сборки, предшествующей сборке 17093, выполняется обновление каталогов файловой системы Linux. Дополнительные сведения об изменениях в файловой системе в сборке 17093 доступны в заметках о выпуске [17093](https://github.com/MicrosoftDocs/WSL/blob/live/WSL/release-notes.md#build-17093).

### <a name="console"></a>Консоль
* Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17101"></a>Сборка 17101
Общие сведения о сборке Windows 17101 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/02/14/announcing-windows-10-insider-preview-build-17101-fast-build-17604-skip-ahead/).

### <a name="wsl"></a>WSL
* Поддержка signalfd. [GH 129]
* Поддержка имен файлов, содержащих недопустимые знаки NTFS, благодаря их кодированию в виде частных знаков Юникода. [GH 1514]
* Функция автоматического подключения будет переключаться в режим только для чтения, если запись не поддерживается. [GH 2603]
* Допускается вставка суррогатных пар Юникода (например, знаков эмодзи). [GH 2765]
* Псевдофайлы в /proc и /sys должны возвращаться готовыми для чтения и записи после выполнения команд select, poll, epoll и т. д. [GH 2838].
* Устранена проблема, из-за которой служба могла уйти в бесконечный цикл, если реестр был незаконно изменен или поврежден.
* Сообщения NETLINK исправлены для работы с более новой версией iproute2 (начиная с версии 4.14).

### <a name="console"></a>Консоль
* Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17093"></a>Сборка 17093
Общие сведения о сборке Windows 17093 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/02/07/announcing-windows-10-insider-preview-build-17093-pc/).

#### <a name="important"></a>Важно!
При запуске WSL в первый раз после обновления до этой сборки необходимо выполнить некоторые действия, чтобы обновить каталоги файловой системы Linux. Это может занять несколько минут, поэтому может показаться, что WSL медленно запускается. Это должно произойти только один раз для каждого дистрибутива, установленного из Store.
* Улучшена поддержка учета регистра в DrvFs.
    * Теперь DrvFs поддерживает учет регистра отдельно для каждого каталога. Это новый флаг, который можно задать для каталогов, чтобы указать, что все операции в этих каталогах должны выполняться с учетом регистра, что позволит даже приложениям для Windows правильно открывать файлы, отличающиеся только регистром в именах.
    * В DrvFs есть новые параметры подключения, управляющие учетом регистра для каждого каталога:
        * case=force: для всех каталогов учитывается регистр (за исключением корневого диска). Новые каталоги, созданные с помощью WSL, помечаются как каталоги с учетом регистра. Это устаревшее поведение, за исключением пометки новых каталогов как каталогов с учетом регистра.
        * case=dir: регистр учитывается только для каталогов с флагом учета регистра; для других каталогов регистр не учитывается. Новые каталоги, созданные с помощью WSL, помечаются как каталоги с учетом регистра.
        * case=off: регистр учитывается только для каталогов с флагом учета регистра; для других каталогов регистр не учитывается. Новые каталоги, созданные с помощью WSL, помечаются как каталоги без учета регистра.
    * Примечание. Каталоги, созданные WSL в предыдущих выпусках, не имеют этого флага, поэтому для них регистр не будет учитываться, если задан параметр case=dir. Способ задания этого флага для существующих каталогов будет реализован в ближайшее время.
    * Пример подключения с этими параметрами (существующие диски необходимо сначала отключить, чтобы подключить их с другими параметрами): sudo mount -t drvfs C: /mnt/c -o case=dir
    * Пока что параметр "case=force" все еще используется по умолчанию. В будущем по умолчанию будет использоваться параметр case=dir.
* Теперь вы можете использовать косую черту в путях Windows при подключении DrvFs, например: sudo mount -t drvfs //server/share /mnt/share
* WSL теперь обрабатывает файл /etc/fstab во время запуска экземпляра [GH 2636].
    * Это делается до автоматического подключения дисков DrvFs. Все диски, которые уже были подключены fstab, не будут автоматически подключаться. Это позволит вам изменить точку подключения для конкретных дисков.
    * Это поведение можно отключить с помощью wsl.conf.
* Файлы mount, mountinfo и mountstats в /proc правильно экранируют специальные знаки, такие как символы обратной косой черты и пробелы [GH 2799].
* Теперь можно копировать и перемещать из Windows специальные файлы, созданные с помощью DrvFs, такие как символьные ссылки WSL, или файлы FIFO и сокеты, если метаданные включены.

#### <a name="wsl-is-more-configurable-with-wslconf"></a>Можно настроить больше параметров WSL с помощью wsl.conf.
Мы добавили метод для автоматической настройки определенных функций в WSL, которые будут применяться при каждом запуске подсистемы. Сюда входят параметры автоподключения и конфигурация сети. Дополнительные сведения об этом можно получить из нашей записи блога: https://aka.ms/wslconf

#### <a name="af_unix-allows-socket-connections-between-linux-processes-on-wsl-and-windows-native-processes"></a>AF_UNIX позволяет устанавливать подключения через сокет между процессами Linux в собственных процессах WSL и Windows.
Теперь приложения WSL и приложения для Windows могут взаимодействовать друг с другом через сокеты UNIX. Представьте, что вы хотите запустить службу в Windows и сделать ее доступной для приложений для Windows и приложений WSL. Теперь это возможно благодаря сокетам UNIX. Узнайте больше в записи блога https://aka.ms/afunixinterop

### <a name="wsl"></a>WSL
* Поддержка mmap() с MAP_NORESERVE [GH 121, 2784].
* Поддержка CLONE_PTRACE и CLONE_UNTRACED [GH 121, 2781].
* Обработка сигнала завершения без SIGCHLD в клоне [GH 121, 2781].
* Добавлены заглушки /proc/sys/fs/inotify/max_user_instances и /proc/sys/fs/inotify/max_user_watches [GH 1705].
* Устранена ошибка при загрузке двоичных файлов ELF, содержащих заголовки загрузки с ненулевыми смещениями [GH 1884].
* Заполнение нулями конечных байтов страниц при загрузке образов.
* Сокращены случаи, когда execve автоматически завершает процесс.

### <a name="console"></a>Консоль
* Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17083"></a>Сборка 17083
Общие сведения о сборке Windows 17083 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/01/24/announcing-windows-10-insider-preview-build-17083-for-pc/).

### <a name="wsl"></a>WSL
* Исправлена критическая ошибка, связанная с epoll [GH 2798, 2801, 2857].
* Исправлено прекращение реагирования на запросы при отключении ASLR [GH 1185, 2870].
* Обеспечена атомарность операций mmap [GH 2732].

### <a name="console"></a>Консоль
* Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17074"></a>Сборка 17074
Общие сведения о сборке Windows 17074 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2018/01/11/announcing-windows-10-insider-preview-build-17074-pc/).

### <a name="wsl"></a>WSL
* Исправлен формат хранения метаданных DrvFs [GH 2777]. </br>
**Важно!** Метаданные DrvFs, созданные до выпуска этой сборки, будут отображаться неправильно или вообще не будут отображаться. Чтобы исправить затронутые файлы, используйте chmod и chown для повторного применения метаданных.
* Устранена проблема с несколькими сигналами и перезапускаемыми вызовами syscall.

### <a name="console"></a>Консоль
* Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17063"></a>Сборка 17063
Общие сведения о сборке Windows 17063 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/12/19/announcing-windows-10-insider-preview-build-17063-pc/).

### <a name="wsl"></a>WSL
* DrvFs поддерживает дополнительные метаданные Linux. Это позволяет задать владельца и режим файлов с помощью chmod или chown, а также создать специальные файлы, такие как FIFO, сокеты UNIX и файлы устройств. Сейчас эта функция отключена по умолчанию, так как еще является экспериментальной.
**Примечание**.  Исправлена ошибка в формате метаданных, используемом DrvFs. Хотя метаданные используются в этой сборке в качестве эксперимента, будущие сборки не будут правильно считывать метаданные, созданные этой сборкой.  Возможно, потребуется вручную обновить владельца измененных файлов, а устройства с пользовательским идентификатором устройства потребуется создать заново.

  Чтобы включить эту функцию, подключите DrvFs с параметром metadata (чтобы включить эту функцию для существующего подключения, его необходимо сначала отключить):

  ```bash
  mount -t drvfs C: /mnt/c -o metadata
  ```

  Разрешения Linux добавляются в файл в качестве дополнительных метаданных; они не влияют на разрешения Windows.  Помните, что изменение файла с помощью редактора Windows может привести к удалению метаданных. В этом случае будут восстановлены разрешения этого файла по умолчанию.

* Добавлены параметры подключения к DrvFs для управления файлами без метаданных.
  * uid: идентификатор пользователя, используемый для владельца всех файлов.
  * gid: идентификатор группы, используемый для владельца всех файлов.
  * umask: восьмеричная маска разрешений, исключаемых для всех файлов и каталогов.
  * fmask: восьмеричная маска разрешений, исключаемых для всех обычных файлов.
  * dmask: восьмеричная маска разрешений, исключаемых для всех каталогов.

  Например:
  ```
  mount -t drvfs C: /mnt/c -o uid=1000,gid=1000,umask=22,fmask=111
  ```

  Используйте вместе с параметром metadata, чтобы указать разрешения по умолчанию для файлов без метаданных.

* Появилась новая переменная среды, `WSLENV`, позволяющая настроить поток переменных среды между WSL и Win32.

  Например:

  ``` bash
  WSLENV=GOPATH/l:USERPROFILE/pu:DISPLAY
  ```

  `WSLENV` — разделенный двоеточиями список переменных среды, которые могут быть добавлены при запуске процессов WSL из Win32 или при запуске процессов Win32 из WSL.  Каждая переменная может иметь суффикс с косой чертой, за которой следуют флаги для указания способа преобразования.
  * p: значение — это путь, который должен быть преобразован между WSL и Win32.
  * l: значение — это список путей. В WSL это список, разделенный двоеточиями. В Win32 это список, разделенный точками с запятой.
  * u: это значение должно добавляться только при вызове WSL из Win32.
  * w: это значение должно добавляться только при вызове Win32 из WSL.

  Вы можете задать `WSLENV` в bashrc или в пользовательской среде Windows для пользователя.

* Подключения DrvFs правильно сохраняют метки времени из tar, cp -p (GH 1939).
* Символические ссылки DrvFs сообщают правильный размер (GH 2641).
* Операции чтения и записи могут обрабатывать очень большие объемы ввода-вывода (GH 2653).
* Функция waitpid работает с идентификаторами групп процессов (GH 2534).
* Значительно улучшена производительность mmap для больших резервных регионов. Повышена производительность ghc (GH 1671).
* Personality поддерживает READ_IMPLIES_EXEC; реализованы исправления для maxima и clisp (GH 1185).
* Mprotect поддерживает PROT_GROWSDOWN; реализованы исправления для clisp (GH 1128).
* Устранены сбои страниц в режиме перегрузки; реализованы исправления для sbcl (GH 1128).
* Функция clone поддерживает больше сочетаний флагов.
* Поддержка select/epoll для файлов epoll (ранее это считалось холостой командой).
* Уведомление ptrace о нереализованных вызовах syscall.
* Игнорирование интерфейсов, которые не выполняются, при создании серверов имен resolv.conf [GH 2694].
* Перечисление сетевых интерфейсов без физического адреса. [GH 2685]
* Дополнительные исправления ошибок и улучшения.

### <a name="linux-tools-available-to-developers-on-windows"></a>Инструменты Linux, доступные для разработчиков в Windows

* Цепочка инструментов командной строки Windows включает в себя bsdtar (tar) и curl.
  Ознакомьтесь с [этим блогом](https://aka.ms/tarcurlwindows), чтобы узнать больше о добавлении этих двух новых инструментов и о том, как они меняют возможности разработки в Windows.

*   `AF_UNIX` доступен в пакете SDK для программы предварительной оценки Windows (начиная со сборки 17061).
  Ознакомьтесь с [этим блогом](https://blogs.msdn.microsoft.com/commandline/2017/12/19/af_unix-comes-to-windows/), чтобы узнать больше о `AF_UNIX` и способах его использования разработчиками в Windows.

### <a name="console"></a>Консоль
* Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.


## <a name="build-17046"></a>Сборка 17046

Общие сведения о сборке Windows 17046 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/11/22/announcing-windows-10-insider-preview-build-17046-pc).

### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Разрешено выполнение процессов без активного терминала. [GH 709, 1007, 1511, 2252, 2391 и т. д.]
- Улучшена поддержка CLONE_VFORK и CLONE_VM. [GH 1878, 2615]
- Пропуск драйверов фильтра TDI для сетевых операций WSL. [GH 1554]
- DrvFs создает символические ссылки NT при выполнении определенных условий. [GH 353, 1475, 2602]
    - Цель ссылки должна быть относительной, не должна пересекать точки подключения или символические ссылки и должна существовать.
    - Пользователь должен иметь разрешение SE_CREATE_SYMBOLIC_LINK_PRIVILEGE (обычно для этого требуется запустить wsl.exe с повышенными привилегиями), если режим разработчика не включен.
    - Во всех остальных случаях DrvFs по-прежнему создает символические ссылки WSL.
- Разрешено одновременное выполнение экземпляров WSL с повышенными привилегиями и без повышенных привилегий.
- Поддержка /proc/sys/kernel/yama/ptrace_scope.
- Добавлена функция wslpath для преобразования путей WSL в пути Windows и наоборот. [GH 522, 1243, 1834, 2327 и т. д.]
  ```
    wslpath usage:
      -a    force result to absolute path format
      -u    translate from a Windows path to a WSL path (default)
      -w    translate from a WSL path to a Windows path
      -m    translate from a WSL path to a Windows path, with '/' instead of '\\'

      EX: wslpath 'c:\users'
  ```
  #### <a name="console"></a>Консоль
- Исправления отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.


## <a name="build-17040"></a>Сборка 17040

Общие сведения о сборке Windows 17040 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/11/16/announcing-windows-10-insider-preview-build-17040-pc).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Исправления с момента выпуска сборки 17035 отсутствуют.

#### <a name="console"></a>Консоль
- Исправления с момента выпуска сборки 17035 отсутствуют.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17035"></a>Сборка 17035

Общие сведения о сборке Windows 17035 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/11/08/announcing-windows-10-insider-preview-build-17035-pc).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Иногда не удавалось получить доступ к файлам в DrvFs с ошибкой EINVAL. [GH 2448]

#### <a name="console"></a>Консоль
- Устранена небольшая потеря цветов при вставке или удалении строк в режиме VT.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17025"></a>Сборка 17025

Общие сведения о сборке Windows 17025 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/10/25/announcing-windows-10-insider-preview-build-17025-pc).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Запуск начальных процессов в новой группе процессов переднего плана [GH 1653, 2510].
- Исправления доставки SIGHUP [GH 2496].
- Создание имени виртуального моста по умолчанию, если оно не указано [GH 2497].
- Реализовано /proc/sys/kernel/Random/boot_id [GH 2518].
- Дополнительные исправления взаимодействия с каналом stdout/stderr.
- Заглушка системного вызова syncfs.

#### <a name="console"></a>Консоль
- Исправление входного преобразования VT для консолей сторонних разработчиков [GH 111].

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="build-17017"></a>Сборка 17017

Общие сведения о сборке Windows 17017 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/10/13/announcing-windows-10-insider-preview-build-17017-pc).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Пропуск пустых заголовков программы ELF [GH 330].
- LxssManager разрешено создавать экземпляры WSL для неинтерактивных пользователей (поддержка SSH и запланированных задач) [GH 777, 1602].
- Поддержка сценариев WSL > Win32 > WSL ("порождение") [GH 1228].
- Ограниченная поддержка завершения работы консольных приложений, вызванных посредством взаимодействия [GH 1614].
- Поддержка параметров подключения для devpts [GH 1948].
- Устранена блокировка Ptrace запуска дочерних процессов [GH 2333].
- В EPOLLET отсутствовали некоторые события [GH 2462].
- PTRACE_GETSIGINFO возвращает больше данных.
- Функция getdents с lseek выдавала неправильные результаты.
- Устранены некоторые сценарии, в которых взаимодействующее приложение Win32 переставало отвечать на запросы, ожидая входных данных в канале, который больше не содержал данные.
- Поддержка O_ASYNC для файлов tty и pty.
- Дополнительные улучшения и исправления.

#### <a name="console"></a>Консоль
- В этом выпуске нет изменений, связанных с консолью.

### <a name="ltp-results"></a>Результаты LTP:
выполняется тестирование.

## <a name="fall-creators-update"></a>Обновление Fall Creators Update

## <a name="build-16288"></a>Сборка 16288

Общие сведения о сборке Windows 16288 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/09/12/announcing-windows-10-insider-preview-build-16288-pc-build-15250-mobile/#7pLWQbj23JisfzV5.97/).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Правильная инициализация и отображение UID, GID и режима для дескрипторов файлов сокетов [GH 2490].
- Дополнительные улучшения и исправления.

#### <a name="console"></a>Консоль
- В этом выпуске нет изменений, связанных с консолью.

### <a name="ltp-results"></a>Результаты LTP:
Изменения с момента выпуска сборки 16273 отсутствуют.

## <a name="build-16278"></a>Сборка 16278

Общие сведения о сборке Windows 162738 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/08/29/announcing-windows-10-insider-preview-build-16278-pc/#HMz6Xq7Su68WKi0t.97/).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Явная отмена сопоставления сопоставленных представлений разделов с файлами при завершении состояния LX MM [GH 2415].
- Дополнительные улучшения и исправления.

#### <a name="console"></a>Консоль
- В этом выпуске нет изменений, связанных с консолью.

### <a name="ltp-results"></a>Результаты LTP:
Изменения с момента выпуска сборки 16273 отсутствуют.

## <a name="build-16275"></a>Сборка 16275

Общие сведения о сборке Windows 162735 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/08/25/announcing-windows-10-insider-preview-build-16275-pc-build-15245-mobile/#8QkxWqQbY37yZslV.97/).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- В этом выпуске нет изменений, связанных с WSL.

#### <a name="console"></a>Консоль
- В этом выпуске нет изменений, связанных с консолью.

### <a name="ltp-results"></a>Результаты LTP:
Изменения с момента выпуска сборки 16273 отсутствуют.

## <a name="build-16273"></a>Сборка 16273

Общие сведения о сборке Windows 16273 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/08/23/announcing-windows-10-insider-preview-build-16273-pc/).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Исправлена проблема, из-за которой DrvFs иногда сообщал о неправильном типе файла для каталогов [GH 2392].
- Разрешено создание сокетов NETLINK_KOBJECT_UEVENT для разблокирования программ, использующих uevent [GH 1121, 2293, 2242, 2295, 2235, 648, 637].
- Добавлена поддержка неблокирующего подключения [GH 903, 1391, 1584, 1585, 1829, 2290, 2314].
- Реализован флаг системного вызова клонирования CLONE_FS [GH 2242].
- Устранены проблемы, связанные с неправильной обработкой знаков табуляции или кавычек при взаимодействии с NT [GH 1625, 2164].
- Устранена ошибка отказа в доступе при попытке повторного запуска экземпляров WSL [GH 651, 2095].
- Реализованы фьютексные операции FUTEX_REQUEUE и FUTEX_CMP_REQUEUE [GH 2242].
- Исправлены разрешения для различных файлов SysFs [GH 2214].
- Устранена проблема, из-за которой стек Haskell переставал отвечать на запросы во время установки [GH 2290].
- Реализованы флаги binfmt_misc "C", "O" и "P" [GH 2103].
- Добавлены /proc/sys/kernel, /shmmax, /shmmni и /threads-max [GH 1753].
- Добавлена частичная поддержка системного вызова ioprio_set [GH 498].
- Реализована заглушка SO_REUSEPORT и добавлена поддержка SO_PASSCRED для сокетов NETLINK [GH 69].
- Возвращение разных кодов ошибок из RegisterDistribuiton, если дистрибутив в данный момент устанавливается или удаляется.
- Обеспечена отмена регистрации частично установленных дистрибутивов WSL с помощью wslconfig.exe.
- Устранена ошибка, из-за которой сокет Python переставал отвечать на запросы при выполнении udp::msg_peek.
- Дополнительные улучшения и исправления.

#### <a name="console"></a>Консоль
- В этом выпуске нет изменений, связанных с консолью.

### <a name="ltp-results"></a>Результаты LTP:
Всего тестов: 1904.<br/>
Всего пропущенных тестов: 209.<br/>
Всего сбоев: 229.<br/>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/16273)<br/>

## <a name="build-16257"></a>Сборка 16257

Общие сведения о сборке Windows 16257 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/08/02/announcing-windows-10-insider-preview-build-16257-pc-build-15237-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Реализован системный вызов prlimit64.
- Добавлена поддержка ulimit -n (setrlimit RLIMIT_NOFILE) [GH 1688].
- Заглушка MSG_MORE для TCP-сокетов [GH 2351].
- Исправлено недопустимое поведение вспомогательного вектора AT_EXECFN [GH 2133].
- Исправлено поведение копирования и вставки для консоли и tty и добавлена улучшенная обработка полного буфера [GH 2204, 2131].
- Установка AT_SECURE в дополнительном векторе для программ set-user-ID и set-group-ID [GH 2031].
- Главная конечная точка псевдотерминала не обрабатывала TIOCPGRP [GH 1063].
- Исправлена проблема lseek с перемоткой каталогов в LxFs [GH 2310].
- Исправлена блокировка /dev/ptmx после интенсивного использования [GH 1882].
- Дополнительные улучшения и исправления.

#### <a name="console"></a>Консоль
- Исправлено отображение горизонтальных линий и знаков подчеркивания везде [GH 2168].
- Исправлено изменение порядка процессов, усложнявшее закрытие NPM [GH 2170].
- Добавлена новая цветовая схема: https://blogs.msdn.microsoft.com/commandline/2017/08/02/updating-the-windows-console-colors/.

### <a name="ltp-results"></a>Результаты LTP:
Изменения с момента выпуска сборки 16251 отсутствуют.

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`prlimit64`<br/>

### <a name="known-issues"></a>Известные проблемы
#### <a name="github-issue-2392-windows-folders-not-recognized-by-wsl-"></a>[Проблема GitHub 2392: WSL не распознает папки Windows…](https://github.com/Microsoft/BashOnWindows/issues/2392)
В сборке 16257 в WSL возникли проблемы при перечислении файлов и папок Windows с помощью `/mnt/c/...`.
Эта проблема устранена, и исправление будет выпущено в сборке для программы предварительной оценки в течение недели после 14 августа 2017 года.

<br/>

## <a name="build-16251"></a>Сборка 16251

Общие сведения о сборке Windows 16251 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/07/26/announcing-windows-10-insider-preview-build-16251-pc-build-15235-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- Удален тег бета-версии из дополнительного компонента WSL. Дополнительные сведения см. в этой [записи блога](https://blogs.msdn.microsoft.com/commandline/2017/07/28/windows-subsystem-for-linux-out-of-beta/).
- Правильная инициализация сохраненных заданных UID и GID для двоичных файлов set-user-ID и set-group-ID при выполнении [GH 962, 1415, 2072].
- Добавлена поддержка PTRACE_O_TRACEEXIT в ptrace [GH 555].
- В ptrace добавлена поддержка PTRACE_GETFPREGS и PTRACE_GETREGSET с NT_FPREGSET [GH 555].
- Исправлена проблема, из-за которой выполнение ptrace останавливалось на пропущенных сигналах.
- Дополнительные улучшения и исправления.

#### <a name="console"></a>Консоль
- В этом выпуске нет изменений, связанных с консолью.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 768</br>
Число непройденных тестов: 244.</br>
Число пропущенных тестов: 96</br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/16251)<br/>

</br>

## <a name="build-16241"></a>Сборка 16241

Общие сведения о сборке Windows 16241 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/07/13/announcing-windows-10-insider-preview-build-16241-pc-build-15230-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
#### <a name="wsl"></a>WSL
- В этом выпуске нет изменений, связанных с WSL.

#### <a name="console"></a>Консоль
- Исправлено вывода неправильного знака для пересечения линий DEC, о котором первоначально было сообщено [здесь](https://www.reddit.com/r/Windows10/comments/6in82t/i_believe_ive_found_the_most_obscure_bug_ever/).
- Исправлено отсутствие вывода текста в кодовой странице 65001 (UTF8).
- Изменения, внесенные в значения RGB одного цвета, не переносятся в другие части палитры при изменении выбора. Это заметно облегчит использование страницы свойств консоли.
- Нажатие клавиш Ctrl+S не работало правильно.
- Un-Bold и -Dim полностью отсутствуют в escape-кодах ANSI [GH 2174].
- Консоль неправильно поддерживала цветовые темы Vim [GH 1706].
- Не удавалось вставить определенные знаки [GH 2149].
- Изменение размера расплавления приводило к необычному изменению размера окна Bash, когда что-то было введено в строке редактирования или командной строке [GH ConEmu 1123].
- Нажатие клавиш CTRL+L не очищало экран [GH 1978].
- Устранена ошибка отрисовки консоли при отображении VT в HDPI [GH 1907].
- Японские знаки выглядели необычно со знаком Юникода U+30FB [GH 2146].
- Дополнительные улучшения и исправления.

</br>

## <a name="build-16237"></a>Сборка 16237

Общие сведения о сборке Windows 16237 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/07/07/announcing-windows-10-insider-preview-build-16237-pc/).<br/>


### <a name="fixed"></a>Фиксированный
- Использование атрибутов по умолчанию для файлов без EA в lxfs (root, root, 0000).
- Добавлена поддержка дистрибутивов, использующих расширенные атрибуты.
- Исправлено заполнение записей, возвращаемых getdents и getdents64.
- Исправлена проверка разрешений для системного вызова shmctl SHM_STAT [GH 2068].
- Исправлено неправильное начальное состояние epoll для tty [GH 2231].
- Устранена проблема в DrvFs, из-за которой команда readdir не возвращала все записи [GH 2077].
- Исправлена операция LxFs readdir с несвязанными файлами [GH 2077].
- Допускается повторное открытие несвязанных файлов DrvFs с помощью procfs.
- Добавлено переопределение глобального раздела реестра для отключения функций WSL (взаимодействие и монтирование дисков).
- Исправлено неправильное число блокировок в "stat" для DrvFs (и LxFs) [GH 1894].
- Дополнительные улучшения и исправления.

</br>

## <a name="build-16232"></a>Сборка 16232

Общие сведения о сборке Windows 16232 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/06/28/announcing-windows-10-insider-preview-build-16232-pc-build-15228-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
- В этом выпуске нет изменений, связанных с WSL.

</br>

## <a name="build-16226"></a>Сборка 16226

Общие сведения о сборке Windows 16226 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/06/21/announcing-windows-10-insider-preview-build-16226-pc/).<br/>


### <a name="fixed"></a>Фиксированный
- Поддержка системных вызовов, связанных с xattr (getxattr, setxattr, listxattr, removexattr).
- Поддержка security.capablity xattr.
- Улучшена совместимость с некоторыми файловыми системами и фильтрами, включая серверы SMB сторонних производителей. [GH 1952]
- Улучшена поддержка заполнителей OneDrive, заполнителей GVFS и сжатых файлов Compact OS.
- Дополнительные улучшения и исправления.

</br>

## <a name="build-16215"></a>Сборка 16215

Общие сведения о сборке Windows 16215 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/06/08/announcing-windows-10-insider-preview-build-16215-pc-build-15222-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
- Для WSL больше не требуется режим разработчика.
- Поддержка соединений каталогов в DrvFs.
- Обработка удаления пакетов appx дистрибутивов WSL.
- Обновление procfs для отображения частных и общих сопоставлений.
- В wslconfig.exe добавлена возможность очистки частично установленных или частично удаленных дистрибутивов.
- Добавлена поддержка IP_MTU_DISCOVER для TCP-сокетов. [GH 1639, 2115, 2205]
- Вывод семейства протоколов для маршрутов к AF_INADDR.
- Улучшения для последовательных устройств [GH 1929].

</br>

## <a name="build-16199"></a>Сборка 16199

Общие сведения о сборке Windows 16199 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/05/17/announcing-windows-10-insider-preview-build-16199-pc-build-15215-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
- В этих выпусках нет изменений, связанных с WSL.

</br>

## <a name="build-16193"></a>Сборка 16193

Общие сведения о сборке Windows 16193 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/05/11/announcing-windows-10-insider-preview-build-16193-pc-build-15213-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
- Исправлено состояние состязания между отправкой SIGCONT и завершением группы потоков [GH 1973].
- Устройства tty и pty изменены для передачи FILE_DEVICE_NAMED_PIPE вместо FILE_DEVICE_CONSOLE [GH 1840].
- Исправление SSH для IP_OPTIONS.
- Подключение DrvFs перемещено в управляющую программу инициализации [GH 1862, 1968, 1767, 1933].
- Добавлена поддержка в DrvFs приведенных ниже символических ссылок NT.

</br>

## <a name="build-16184"></a>Сборка 16184

Общие сведения о сборке Windows 16184 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/04/28/announcing-windows-10-insider-preview-build-16184-pc-build-15208-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
- Удалена задача обслуживания пакета apt (lxrun.exe /update).
- Исправлено отсутствие выходных данных из процессов Windows в Node.js [GH 1840].
- Смягчены требования к соответствию в lxcore [GH 1794].
- Исправлена обработка флага AT_EMPTY_PATH в ряде системных вызовов.
- Исправлена проблема, из-за которой удаление файлов DrvFs с открытыми дескрипторами приводило к неопределенному поведению файла [GH 544, 966, 1357, 1535, 1615].
- Теперь /etc/hosts будет наследовать записи из файла hosts Windows (%windir%\System32\Drivers\Etc\hosts) [GH 1495].

</br>

## <a name="build-16179"></a>Сборка 16179

Общие сведения о сборке Windows 16179 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/04/19/announcing-windows-10-insider-preview-build-16179-pc-build-15205-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
- На этой неделе изменения в WSL отсутствуют.

</br>

## <a name="build-16176"></a>Сборка 16176

Общие сведения о сборке Windows 16176 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/04/14/announcing-windows-10-insider-preview-build-16176-pc-build-15204-mobile/).<br/>


### <a name="fixed"></a>Фиксированный

- [Включена поддержка последовательных устройств](https://blogs.msdn.microsoft.com/wsl/2017/04/14/serial-support-on-the-windows-subsystem-for-linux/).
- Добавлен параметр IP-сокета IP_OPTIONS [GH 1116].
- Реализована функция pwritev (при передаче файла в nginx/PHP-FPM) [GH 1506].
- Добавлены параметры IP-сокета IP_MULTICAST_IF и IPV6_MULTICAST_IF [GH 990].
- Поддержка параметров сокета IP_MULTICAST_LOOP и IPV6_MULTICAST_LOOP [GH 1678].
- Добавлен параметр сокета IP(V6)_MTU для приложений node, traceroute, dig, nslookup, host.
- Добавлен параметр IP-сокета IPV6_UNICAST_HOPS.
- [Улучшения файловой системы](https://blogs.msdn.microsoft.com/wsl/2017/04/18/file-system-improvements-to-the-windows-subsystem-for-linux/).
    * Разрешено подключение путей UNC.
    * Включена поддержка CDFS в DrvFs.
    * Правильная обработка разрешений для сетевых файловых систем в DrvFs.
    * Добавлена поддержка удаленных дисков в DrvFs.
    * Включена поддержка файловой системы FAT в DrvFs.
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP
Изменения с момента выпуска сборки 15042 отсутствуют.

</br>

## <a name="build-16170"></a>Сборка 16170

Общие сведения о сборке Windows 16170 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/04/07/announcing-windows-10-insider-preview-build-16170-pc/).<br/>

Мы опубликовали новую[запись блога](https://blogs.msdn.microsoft.com/wsl/2017/04/11/testing-the-windows-subsystem-for-linux/), в которой обсуждаем наши усилия по тестированию WSL.

### <a name="fixed"></a>Фиксированный

- Поддержка параметров сокета IP_ADD_MEMBERSHIP и IPV6_ADD_MEMBERSHIP [GH 1678].
- Добавлена поддержка PTRACE_OLDSETOPTIONS. [GH 1692]
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP
Изменения с момента выпуска сборки 15042 отсутствуют.

</br>

## <a name="build-15046-to-windows-10-creators-update"></a>Сборка 15046 для Windows 10 Creators Update
В обновление Creators Update для Windows 10 больше не планируется добавлять какие-либо исправления или функции WSL. Публикация заметок о выпуске WSL будет возобновлена в ближайшие недели, чтобы охватить дополнения, запланированные в следующих основных версиях в Центре обновления Windows. Общие сведения о сборке Windows 15046 и будущих выпусках для программы предварительной оценки доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/02/28/announcing-windows-10-insider-preview-build-15046-pc/). <br/><br/>
 <br/>

## <a name="build-15042"></a>Сборка 15042

Общие сведения о сборке Windows 15042 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/02/24/announcing-windows-10-insider-preview-build-15042-pc-build-15043-mobile/).<br/>


### <a name="fixed"></a>Фиксированный

- Устранена взаимоблокировка при удалении пути, завершающегося "..".
- Устранена проблема, из-за которой функция FIONBIO не возвращала 0 при успешном выполнении [GH 1683].
- Устранена проблема с чтением сокетов датаграмм INET нулевой длины.
- Устранена возможная взаимоблокировка из-за состояния состязания при поиске DrvFs в DrvFs [GH 1675].
- Расширена поддержка вспомогательных данных сокетов UNIX, SCM_CREDENTIALS и SCM_RIGHTS [GH 514, 613, 1326].
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 737.</br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 255.

</br>

## <a name="build-15031"></a>Сборка 15031

Общие сведения о сборке Windows 15031 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/02/08/announcing-windows-10-insider-preview-build-15031-pc/).<br/>


### <a name="fixed"></a>Фиксированный

- Исправлена ошибка, из-за которой поведение time(2) иногда было неправильным.
- Исправлена проблема, из-за которой системный вызов *SIGPROCMASK мог повредить маску сигнала.
- Теперь в уведомлении о создании процесса WSL возвращается полная длина командной строки. [GH 1632]
- Теперь WSL сообщает о выходе из потока посредством ptrace, если GDB перестает отвечать на запросы. [GH 1196]
- Исправлена ошибка, из-за которой устройства pty переставали отвечать на запросы после интенсивного ввода-вывода tmux. [GH 1358]
- Исправлена проверка времени ожидания во многих системных вызовах (futex, semtimedop, ppoll, sigtimedwait, itimer, timer_create).
- Добавлена поддержка eventfd EFD_SEMAPHORE [GH 452].
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 737.</br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 255. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15031)<br/>

<br/>

## <a name="build-15025"></a>Сборка 15025

Общие сведения о сборке Windows 15025 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/02/01/announcing-windows-10-insider-preview-build-15025-pc/).<br/>


### <a name="fixed"></a>Фиксированный

- Исправлена ошибка, которая нарушала работу grep 2.27 [GH 1578].
- Реализован флаг EFD_SEMAPHORE для системного вызова eventfd2 [GH 452].
- Реализован файл /proc/[pid]/net/ipv6_route [GH 1608].
- Поддержка управляемого сигналами ввода-вывода для сокетов потоков UNIX [GH 393, 68].
- Поддержка F_GETPIPE_SZ и F_SETPIPE_SZ [GH 1012].
- Реализация системного вызова recvmmsg() [GH 1531].
- Исправлена ошибка, из-за которой функция epoll_wait() не ожидала выполнения [GH 1609].
- Реализация /proc/version_signature.
- Теперь системный вызов Tee возвращает ошибку, если оба дескриптора файла ссылаются на один и тот же канал.
- Реализовано правильное поведение SO_PEERCRED для сокетов UNIX.
- Исправлена недопустимая обработка параметров системного вызова tkill.
- Внесены изменения для увеличения производительности DrvFs.
- Незначительное исправление блокировки ввода-вывода Ruby.
- Исправлена проблема, из-за которой функция recvmsg() возвращала EINVAL для флага MSG_DONTWAIT для сокетов INET [GH 1296].
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 732.</br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 255. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15025)<br/>

<br/>

## <a name="build-15019"></a>Сборка 15019

Общие сведения о сборке Windows 15019 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/01/27/announcing-windows-10-insider-preview-build-15019-pc/).<br/>


### <a name="fixed"></a>Фиксированный

- Исправлена ошибка, из-за которой отображались неправильные данные об использовании ЦП в procfs для таких инструментов, как htop [GH 823, 945, 971].
- Теперь при вызове Open() с O_TRUNC для существующего файла inotify теперь создает IN_MODIFY до IN_OPEN.
- Исправление getsockopt SO_ERROR в сокетах UNIX для включения возможностей postgress [GH 61, 1354].
- Реализация /proc/sys/net/core/somaxconn для языка GO.
- Теперь фоновая задача обновления пакета apt-get запускается из представления в скрытом режиме.
- Очищена область для IPv6-адреса localhost (сбой (Spring-Framework(Java)).
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 714. </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 249. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15019)<br/>

<br/>

## <a name="build-15014"></a>Сборка 15014

Общие сведения о сборке Windows 15014 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/01/19/announcing-windows-10-insider-preview-build-15014-for-pc-and-mobile-hello-windows-insiders-today-we-are-excited-to-be-releasing-windows-10-insider-preview-build-15014-for-pc-and-mobile).<br/>


### <a name="fixed"></a>Фиксированный

- Нажатие клавиш CTRL+C теперь работает ожидаемым образом.
- Теперь htop и ps auxw показывают правильные данные об использовании ресурсов (GH 516).
- Простое преобразование исключений NT в сигналы. (GH 513)
- Теперь при нехватке пространства fallocate завершается ошибкой ENOSPC вместо EINVAL (GH 1571).
- Добавлен /proc/sys/kernel/sem.
- Реализованы системные вызовы semop и semtimedop.
- Устранены ошибки nslookup, связанные с параметрами сокета IP_RECVTOS и IPV6_RECVTCLASS (GH 69).
- Поддержка параметров сокета IP_RECVTTL и IPV6_RECVHOPLIMIT.
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 709. </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 255. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15014)<br/>

### <a name="syscall-summary"></a>Сводка по системным вызовам
Всего системных вызовов: 384 </br>
Всего реализовано: 235. </br>
Всего заглушено: 22 </br>
Всего не реализовано: 127 </br>
[Подробная разбивка](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15014/Syscalls.txt)<br/>

<br/>

## <a name="build-15007"></a>Сборка 15007

Общие сведения о сборке Windows 15007 доступны в [блоге о Windows]( https://blogs.windows.com/windowsexperience/2017/01/12/announcing-windows-10-insider-preview-build-15007-pc-mobile).<br/>


### <a name="known-issue"></a>Известная проблема

- Существует известная ошибка, из-за которой консоль не распознает некоторые клавиши CTRL+<key>.  Например, это может быть сочетание CTRL+C, которое будет функционировать как обычное нажатие клавиши C.

  - Возможное решение. Сопоставьте альтернативную клавишу с клавишами CTRL+C. Например, чтобы сопоставить клавиши CTRL+K с CTRL+C, выполните следующее: `stty intr \^k`.  Это сопоставление действует в пределах терминала и должно выполняться *при каждом* запуске Bash. Пользователи могут изучить этот параметр, чтобы включить его в `.bashrc`.

### <a name="fixed"></a>Фиксированный

- Исправлена ошибка, из-за которой подсистема WSL потребляла 100 % ресурсов ядра ЦП.
- Теперь поддерживаются параметры сокета IP_PKTINFO и IPV6_RECVPKTINFO. (GH 851, 987)
- Усечение физического адреса сетевого интерфейса до 16 байтов в lxcore (GH #1452, 1414, 1343, 468, 308).
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 709. </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 255. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15007)<br/>

<br/>

## <a name="build-15002"></a>Сборка 15002

Общие сведения о сборке Windows 15002 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2017/01/09/announcing-windows-10-insider-preview-build-15002-pc/).<br/>


### <a name="known-issue"></a>Известная проблема

Две известные проблемы:
- Существует известная ошибка, из-за которой консоль не распознает некоторые клавиши CTRL+<key>.  Например, это может быть сочетание CTRL+C, которое будет функционировать как обычное нажатие клавиши C.

  - Возможное решение. Сопоставьте альтернативную клавишу с клавишами CTRL+C. Например, чтобы сопоставить клавиши CTRL+K с CTRL+C, выполните следующее: `stty intr \^k`.  Это сопоставление действует в пределах терминала и должно выполняться *при каждом* запуске Bash. Пользователи могут изучить этот параметр, чтобы включить его в `.bashrc`.

- Во время выполнения WSL системный поток потребляет 100 % ресурсов ядра ЦП.  Первопричина устранена и исправлена внутри компонента.

### <a name="fixed"></a>Фиксированный

- Все сеансы Bash теперь должны создаваться на одном уровне разрешений.  Попытка запустить сеанс на другом уровне будет заблокирована.  Это означает, что консоль администратора и консоль пользователя, не являющегося администратором, не могут работать одновременно. (GH 626)
<br/>
- Реализованы следующие сообщения NETLINK_ROUTE (требуются права администратора Windows):
     - RTM_NEWADDR (поддерживает `ip addr add`);
     - RTM_NEWROUTE (поддерживает `ip route add`);
     - RTM_DELADDR (поддерживает `ip addr del`);
     - RTM_DELROUTE (поддерживает `ip route del`).
- Проверка запланированных задач для пакетов, которые необходимо обновить, больше не будет выполняться при лимитном подключении (GH 1371).
- Исправлена ошибка, из-за которой канал переставал отвечать на запросы, например bash -c "ls -alR /" | bash -c "cat" (GH 1214).
- Реализован параметр сокета TCP_KEEPCNT (GH 843).
- Реализован параметр сокета INET IP_MTU_DISCOVER (GH 720, 717, 170, 69).
- Удалены устаревшие функции для запуска двоичных файлов NT из init с помощью поиска по пути NT. (GH 1325)
- Исправлен режим /dev/kmsg для разрешения группового и другого доступа на чтение (0644) (GH 1321).
- Реализован файл /proc/sys/kernel/random/uuid [GH 1092].
- Исправлена ошибка, из-за которой время начала процесса отображалось как 2432 год (GH 974).
- Переменная среды TERM по умолчанию заменена xterm-256color (GH 1446).
- Изменен способ вычисления фиксации процесса во время ветвления процесса. (GH 1286)
- Реализован файл /proc/sys/VM/overcommit_memory. (GH 1286)
- Реализован файл /proc/net/route (GH 69).
- Исправлена ошибка, из-за которой имя ярлыка было неправильно локализовано (GH 696).
- Исправлена логика анализа ELF, которая неправильно проверяла заголовки программ, которые должны быть меньше или равны PATH_MAX. (GH 1048)
- Реализован обратный вызов statfs для procfs, sysfs, cgroupfs и binfmtf (GH 1378).
- Исправлена проблема, из-за которой окна AptPackageIndexUpdate не закрывались (GH 1184, также обсуждается в GH 1193).
- Добавлена поддержка ADDR_NO_RANDOMIZE в ASLR personality. [GH 1148, 1128]
- Улучшена функция PTRACE_GETSIGINFO для SIGSEGV для обеспечения правильных трассировок стека GDB во время операций AV (GH 875).
- Анализ ELF больше не завершается ошибкой для двоичных файлов patchelf. (GH 471)
- DNS-сервер VPN добавлен в /etc/resolv.conf (GH 416, 1350).
- Улучшено закрытие TCP-подключений для более надежной передачи данных. (GH 610, 616, 1025, 1335)
- Теперь возвращается правильный код ошибки при открытии слишком большого числа файлов (EMFILE). [GH 1126, 2090]
- Журнал аудита Windows теперь отображает имя образа при аудите процесса создания.
- Теперь запуск bash.exe из окна Bash корректно завершается ошибкой.
- Добавлено сообщение об ошибке, когда служба взаимодействия не может получить доступ к рабочему каталогу в LxFs (например, notepad.exe. bashrc).
- Исправлена проблема, из-за которой путь Windows в WSL был усеченным.
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 690. </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 274. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15002)<br/>

<br/>

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`shmctl`<br/>
`shmget`<br/>
`shmdt`<br/>
`shmat`<br/>
<br/>

## <a name="build-14986"></a>Сборка 14986

Общие сведения о сборке Windows 14986 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/12/07/announcing-windows-10-insider-preview-build-14986-pc/).<br/>


### <a name="fixed"></a>Фиксированный

- Исправлены ошибки NETLINK и PTY IOCTL.
- Теперь отображается версия ядра 4.4.0-43 для обеспечения согласованности с Xenial.
- Теперь Bash.exe запускается, когда ввод направляется в "nul:" (GH 1259).
- Теперь идентификаторы потоков отображаются правильно в procfs (GH 967).
- Теперь в inotify_add_watch() поддерживаются флаги IN_UNMOUNT | IN_Q_OVERFLOW | IN_IGNORED | IN_ISDIR (GH 1280).
- Реализован timer_create и связанные системные вызовы.  Это обеспечивает поддержку GHC (GH 307).
- Исправлена проблема, из-за которой проверка связи возвращала время 0,000 мс (GH 1296).
- Возвращается правильный код ошибки при открытии слишком большого числа файлов.
- Исправлена проблема в WSL, из-за которой запрос NETLINK на данные сетевого интерфейса завершался ошибкой EINVAL, если аппаратный адрес интерфейса был 32-байтовым (например, интерфейс Teredo).
   - Обратите внимание на то, что служебная программа Linux "ip" содержит ошибку, из-за которой произойдет сбой, если WSL сообщит 32-байтовый адрес оборудования. Это ошибка в "ip", а не в WSL. В служебной программе ip прописана в коде длина строкового буфера, используемого для вывода аппаратного адреса, и этот буфер слишком мал для вывода 32-байтового аппаратного адреса.
- Дополнительные исправления и улучшения.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 669. </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 258 </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14986)<br/>

<br/>

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`timer_create`<br/>
`timer_delete`<br/>
`timer_gettime`<br/>
`timer_settime`<br/>
<br/>

## <a name="build-14971"></a>Сборка 14971

Общие сведения о сборке Windows 14971 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/11/17/announcing-windows-10-insider-preview-build-14971-for-pc/).<br/>


### <a name="fixed"></a>Фиксированный

 - Из-за независящих от нас обстоятельств в этой сборке не будет обновлений для подсистемы Windows для Linux.  Регулярный выпуск плановых обновлений будет возобновлен в следующем выпуске.

### <a name="ltp-results"></a>Результаты LTP:
без изменений с момента выпуска сборки 14965. </br>
Число пройденных тестов: 664 </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 263. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14965)<br/>

<br/>

## <a name="build-14965"></a>Сборка 14965

Общие сведения о сборке Windows 14965 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/11/09/announcing-windows-10-insider-preview-build-14965-for-mobile-and-pc/).<br/>


### <a name="fixed"></a>Фиксированный

- Поддержка RTM_GETLINK и RTM_GETADDR для NETLINK_ROUTE в сокетах NETLINK (GH 468).
  - Применение команд ifconfig и ip для перечисления сетей.
  - Дополнительные сведения см. в нашей [записи блога о сетях WSL](https://blogs.msdn.microsoft.com/wsl/2016/11/08/225/).

- Теперь /sbin добавляется в путь пользователя по умолчанию.
- Теперь путь пользователя NT по умолчанию добавляется к пути WSL (т. е. теперь можно ввести notepad.exe, не добавляя System32 в путь Linux).
- Добавлена поддержка /proc/sys/kernel/cap_last_cap.
- Теперь двоичные файлы NT можно запускать из WSL, если текущий рабочий каталог содержит знаки, отличные от ANSI (GH 1254).
- Разрешено завершение работы при отключении сокета потока UNIX.
- Добавлена поддержка PR_GET_PDEATHSIG.
- Добавлена поддержка CLONE_PARENT.
- Исправлена ошибка, из-за которой канал переставал отвечать на запросы, например bash -c "ls -alR /" | bash -c "cat" (GH 1214).
- Обработка запросов на подключение к текущему терминалу.
- Файл /proc/<pid>/oom_score_adj помечен как записываемый.
- Добавлена папку /sys/fs/cgroup.
- Функция sched_setaffinity должна возвращать значение маски битов сходства.
- Исправлена логика проверки ELF, которая неправильно предполагала, что пути интерпретатора должны содержать менее 64 знаков. (GH 743)
- Открытые дескрипторы файлов могут оставаться открытыми в окне консоли (GH 1187).
- Устранена ошибка, из-за которой происходил сбой rename(), если имя цели содержало конечную косую черту (GH 1008).
- Реализован файл /proc/net/dev.
- Исправлена ошибка, из-за которой при проверке связи возвращалось значение 0,000 мс из-за разрешения таймера.
- Реализован файл /proc/self/environ (GH 730).
- Дополнительные исправления ошибок и усовершенствования.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 664 </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 263. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14965)<br/>

<br/>

## <a name="build-14959"></a>Сборка 14959

Общие сведения о сборке Windows 14959 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/11/03/announcing-windows-10-insider-preview-build-14959-for-mobile-and-pc/#iI82GufJxMF3POU1.97).<br/>


### <a name="fixed"></a>Фиксированный

- Улучшены уведомления о процессе Pico для Windows.  Дополнительные сведения см. в [блоге о WSL](https://blogs.msdn.microsoft.com/wsl/2016/11/01/wsl-antivirus-and-firewall-compatibility/).
- Повышена стабильность взаимодействия с Windows.
- Устранена ошибка 0x80070057, возникавшая при запуске bash.exe при включенной защите корпоративных данных (EDP).
- Дополнительные исправления ошибок и усовершенствования.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 665 </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 263. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14959)<br/>

<br/>

## <a name="build-14955"></a>Сборка 14955

Общие сведения о сборке Windows 14955 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/10/25/announcing-windows-10-insider-preview-build-14955-for-mobile-and-pc/#guGXQzKVFrZIDUYR.97).<br/>


### <a name="fixed"></a>Фиксированный

 - Из-за независящих от нас обстоятельств в этой сборке не будет обновлений для подсистемы Windows для Linux.  Регулярный выпуск плановых обновлений будет возобновлен в следующем выпуске.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 665 </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 263. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14955)<br/>

<br/>

## <a name="build-14951"></a>Сборка 14951

Общие сведения о сборке Windows 14951 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/10/19/announcing-windows-10-insider-preview-build-14951-for-mobile-and-pc/).<br/>


### <a name="new-feature-windows--ubuntu-interoperability"></a>Новая функция: взаимодействие Ubuntu и Windows
Теперь двоичные файлы Windows можно вызывать непосредственно из командной строки WSL.  Это дает пользователям возможность взаимодействовать со средой и системой Windows способом, который ранее был невозможен.  Например, теперь пользователи могут выполнять следующие команды.

```bash
$ export PATH=$PATH:/mnt/c/Windows/System32
$ notepad.exe
$ ipconfig.exe | grep IPv4 | cut -d: -f2
$ ls -la | findstr.exe foo.txt
$ cmd.exe /c dir
```

Дополнительные сведения:

- [Блог команды WSL по взаимодействию](https://blogs.msdn.microsoft.com/wsl/2016/10/19/windows-and-ubuntu-interoperability/)<br/>
- [Документация по взаимодействию на сайте MSDN](https://msdn.microsoft.com/commandline/wsl/interop)<br/>

### <a name="fixed"></a>Фиксированный

- Ubuntu 16.04 (Xenial) теперь устанавливается для всех новых экземпляров WSL.  Существующие у пользователей экземпляры Ubuntu 14.04 (Trusty) не будут обновляться автоматически.
- Теперь отображается языковой стандарт, установленный во время установки.
- Улучшения в терминале, включая устранение ошибки, из-за которой перенаправление процесса WSL в файл не всегда работало.
- Время существования консоли должно быть связано со временем существования bash.exe.
- Размер окна консоли должен быть основан на видимом размере, а не размере буфера.
- Дополнительные исправления ошибок и усовершенствования.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 665 </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 263. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14951)<br/>

<br/>

## <a name="build-14946"></a>Сборка 14946

Общие сведения о сборке Windows 14946 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/10/13/announcing-windows-10-insider-preview-build-14946-for-pc-and-mobile/#xj8GdVooEqo4H7H7.97).<br/>


### <a name="fixed"></a>Фиксированный

- Устранена проблема, которая не позволила создавать учетные записи WSL для пользователей с именами пользователей NT, содержащими пробелы или кавычки. 
- Внесены изменения в VolFs и DrvFs, чтобы возвращалось значение 0 для количества ссылок каталога в stat.
- Поддержка параметра сокета IPV6_MULTICAST_HOPS.
- Ограничение в один цикл ввода-вывода консоли на tty. Например, можно выполнить следующую команду:
  - bash -c "echo data" | bash -c "ssh user@example.com 'cat > foo.txt'"

- Пробелы в /proc/cpuinfo заменены символами табуляции (GH 1115).
- DrvFs теперь отображается в mountinfo с именем, совпадающим с подключенным томом Windows.
- Теперь /home и /root отображаются в mountinfo с правильными именами.
- Дополнительные исправления ошибок и усовершенствования.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 665 </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 263. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14946)<br/>

<br/>

## <a name="build-14942"></a>Сборка 14942

Общие сведения о сборке Windows 14942 доступны в [блоге о Windows](https://aka.ms/onefourninefourtwoooooo).<br/>


### <a name="fixed"></a>Фиксированный

- Исправлен ряд ошибок, в том числе сбой сети ATTEMPTED EXECUTE OF NOEXECUTE MEMORY (Попытка выполнения в недоступной памяти), который блокировал SSH.
- Добавлена поддержка inotifiy для уведомлений, созданных в приложениях для Windows в DrvFs.
- Реализованы параметры TCP_KEEPIDLE и TCP_KEEPINTVL для mongod. (GH 695)
- Реализован системный вызов pivot_root.
- Реализован параметр сокета для SO_DONTROUTE.
- Дополнительные исправления ошибок и усовершенствования.


### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 665 </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 263. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14942)<br/>

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`pivot_root`<br/>
<br/>

## <a name="build-14936"></a>Сборка 14936

Общие сведения о сборке Windows 14936 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/09/28/announcing-windows-10-insider-preview-build-14936-for-pc/).<br/>


Примечание. В предстоящем выпуске WSL будет устанавливать версию Ubuntu 16.04 (Xenial) вместо Ubuntu 14.04 (Trusty).  Это изменение будет применено к участникам программы предварительной оценки, которые устанавливают новые экземпляры (lxrun.exe /install или первый запуск bash.exe).  Существующие экземпляры с версией Trusty не будут обновлены автоматически. Пользователи могут обновить свой образ Trusty до версии Xenial с помощью команды do-release-upgrade.

### <a name="known-issue"></a>Известная проблема
В WSL существует проблема с реализацией некоторых сокетов.  Ошибка проявляется как сбой с сообщением ATTEMPTED EXECUTE OF NOEXECUTE MEMORY (Попытка выполнения в недоступной памяти).  Чаще всего этот сбой происходит при использовании SSH.  Первопричина исправлена во внутренних сборках, и исправление будет добавлено в сборки для программы предварительной оценки при первой возможности.

### <a name="fixed"></a>Фиксированный

- Реализован системный вызов chroot.
- Улучшения в inotify, ~~включая поддержку уведомлений, созданных в приложениях для Windows в DrvFs~~.
  - Исправление: В настоящее время недоступна поддержка в inotify изменений, исходящих из приложений Windows.
- Привязка сокета к IPV6::<port n> теперь поддерживает IPV6_V6ONLY (GH 68, 157, 393, 460, 674, 740, 982, 996).
- Реализовано поведение WNOWAIT для системного вызова waitid (GH 638).
- Поддержка параметров IP-сокета IP_HDRINCL и IP_TTL.
- Результат read() нулевой длины должен возвращаться немедленно (GH 975).
- Правильная обработка имен файлов и префиксов имен файлов, которые не содержат терминатор NULL в TAR-файле.
- Поддержка epoll для /dev/null.
- Исправлен источник времени /dev/alarm.
- Теперь команда bash -c может выполнять перенаправление в файл.
- Дополнительные исправления ошибок и усовершенствования.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 664 </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 264. </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14936)<br/>

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`chroot`<br/>
<br/>

## <a name="build-14931"></a>Сборка 14931

Общие сведения о сборке Windows 14931 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/09/21/announcing-windows-10-insider-preview-build-14931-for-pc/).<br/>


### <a name="fixed"></a>Фиксированный

 - Из-за независящих от нас обстоятельств в этой сборке не будет обновлений для подсистемы Windows для Linux.  Регулярный выпуск плановых обновлений будет возобновлен в следующем выпуске.

<br/>

## <a name="build-14926"></a>Сборка 14926

Общие сведения о сборке Windows 14926 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/09/14/announcing-windows-10-insider-preview-build-14926-for-pc-and-mobile/).<br/>


### <a name="fixed"></a>Фиксированный

- Проверка связи теперь работает в консолях без привилегий администратора.
- Теперь поддерживается ping6, также без привилегий администратора.
- Поддержка в inotify файлов, измененных посредством WSL. (GH 216)
  - Поддерживаемые флаги:
    - inotify_init1: LX_O_CLOEXEC, LX_O_NONBLOCK
    - События inotify_add_watch: LX_IN_ACCESS, LX_IN_MODIFY, LX_IN_ATTRIB, LX_IN_CLOSE_WRITE, LX_IN_CLOSE_NOWRITE, LX_IN_OPEN, LX_IN_MOVED_FROM, LX_IN_MOVED_TO, LX_IN_CREATE, LX_IN_DELETE, LX_IN_DELETE_SELF, LX_IN_MOVE_SELF
    - Атрибуты inotify_add_watch: LX_IN_DONT_FOLLOW, LX_IN_EXCL_UNLINK, LX_IN_MASK_ADD, LX_IN_ONESHOT, LX_IN_ONLYDIR
    - Выходные данные чтения: LX_IN_ISDIR, LX_IN_IGNORED
  - Известная проблема: Изменение файлов из приложений Windows не приводит к созданию событий.
- Сокет UNIX теперь поддерживает SCM_CREDENTIALS.

### <a name="ltp-results"></a>Результаты LTP:
Число пройденных тестов: 651 </br>
Число непройденных тестов (неудачных, пропущенных и т. д.): 258 </br>
[Журналы выполнения тестов LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14926)<br/>

<br/>

## <a name="build-14915"></a>Сборка 14915

Общие сведения о сборке Windows 14915 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/08/31/announcing-windows-10-insider-preview-build-14915-for-pc-and-mobile).<br/>


### <a name="fixed"></a>Фиксированный
-  Socketpair для сокетов датаграмм UNIX (GH 262).
- Поддержка сокетов UNIX для SO_REUSEADDR.
- Поддержка сокетов UNIX для SO_BROADCAST (GH 568).
- Поддержка сокетов UNIX для SOCK_SEQPACKET (GH 758, 546).
- Добавлена поддержка send, recv и shutdown для сокетов датаграмм UNIX.
- Устранена ошибка из-за неправильной проверки параметров mmap для нефиксированных адресов. (GH 847)
- Поддержка приостановки и возобновления состояний терминала.
- Поддержка TIOCPKT ioctl для разблокировки служебной программы Screen (GH 774).
    - Известная проблема: Не работают функциональные клавиши.
- Исправлено состязание в TimerFd, которое могло привести к обращению LxpTimerFdWorkerRoutine к освобожденному элементу ReaderReady (GH 814).
- Включена поддержка перезапускаемых системных вызовов для futex, poll и clock_nanosleep.
- Добавлена поддержка подключения привязки.
- Поддержка отмены общего доступа для пространства имен подключения.
    - Известная проблема: При создании пространства имен подключения посредством `unshare(CLONE_NEWNS)` текущий рабочий каталог будет по-прежнему указывать на старое пространство имен.
- Дополнительные улучшения и исправления.

<br/>

## <a name="build-14905"></a>Сборка 14905

Общие сведения о сборке Windows 14905 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/08/17/announcing-windows-10-insider-preview-build-14905-for-pc-mobile/).<br/>


### <a name="fixed"></a>Фиксированный
- Теперь поддерживаются перезапускаемые системные вызовы (GH 349, GH 520).
- Теперь функционируют символические ссылки на каталоги, которые заканчиваются косой чертой "/" (GH 650).
- Реализован параметр RNDGETENTCNT ioctl для /dev/random.
- Реализованы файлы /proc/[pid]/mounts, /proc/[pid]/mountinfo и /proc/[pid]/mountstats.
- Дополнительные исправления ошибок и усовершенствования.

</br>

## <a name="build-14901"></a>Сборка 14901
Первая сборка для программы предварительной оценки для выпуска после юбилейного обновления Windows 10.

Общие сведения о сборке Windows 14901 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/08/11/announcing-windows-10-insider-preview-build-14901-for-pc/).<br/>


### <a name="fixed"></a>Фиксированный
- Исправлена проблема конечной косой черты.
    - Теперь работают такие команды, как `$ mv a/c/ a/b/`.
- Теперь при установке отображается запрос, позволяющий установить языковый стандарт Ubuntu, совпадающий с языковым стандартом Windows.
- Поддержка procfs для папки ns.
- Добавлены функции подключения и отключения для файловых систем tmpfs, procfs и sysfs.
- Исправлена 32-разрядная подпись ABI для mknod[at].
- Сокеты UNIX переведены на модель диспетчеризации.
- Размер буфера recv сокета INET, заданный с помощью setsockopt, должен учитываться.
- Реализован флаг получения сообщения MSG_CMSG_CLOEXEC для сокетов UNIX.
- Перенаправление канала stdin/stdout процесса Linux (GH 2).
    - Разрешена конвейерная передача команд bash -c в командную строку.  Пример:  >dir | bash -c "grep foo"
- Теперь Bash можно установить в системах с несколькими файлами подкачки (GH 538, 358).
- Размер буфера сокета INET по умолчанию должен соответствовать установке Ubuntu по умолчанию.
- Системные вызовы xattr согласованы с listxattr.
- SIOCGIFCONF возвращает только интерфейсы с допустимым IPv4-адресом.
- Исправлено действие по умолчанию для сигнала при внедрении с помощью ptrace.
- Реализован файл /proc/sys/vm/min_free_kbytes.
- Использование значений реестра для контекста компьютера при восстановлении контекста в sigreturn.
    - Это устраняет проблему, из-за которой у некоторых пользователей java и javac переставали отвечать на запросы.
- Реализован файл /proc/sys/kernel/hostname.

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`waitid`<br/>
`epoll_pwait`<br/>

<br/>

## <a name="build-14388-to-windows-10-anniversary-update"></a>Сборка 14388 для юбилейного обновления Windows 10
Общие сведения о сборке Windows 14388 доступны в [блоге о Windows](https://aka.ms/14388wip). <br/>

### <a name="fixed"></a>Фиксированный
- Исправления для подготовки к выпуску юбилейного обновления Windows 10 2-го августа.
  - Дополнительные сведения о компоненте WSL в юбилейном обновлении можно найти на нашем [блоге](https://blogs.msdn.microsoft.com/wsl/).

<br/>

## <a name="build-14376"></a>Сборка 14376
Общие сведения о сборке Windows 14376 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/06/28/announcing-windows-10-insider-preview-build-14376-for-pc-and-mobile/). <br/>

### <a name="fixed"></a>Фиксированный
- Удалены некоторые экземпляры, в которых функция apt-get переставала отвечать на запросы (GH 493).
- Исправлена проблема, из-за которой неправильно обрабатывались пустые подключения.
- Исправлена проблема, из-за которой неправильно подключались диски ramdisk.
- Изменена процедура принятия сокетов UNIX для поддержки флагов (частично GH 451).
- Исправлена распространенная проблема с сетью, вызывавшая ошибку "синий экран".
- Устранена ошибка "синий экран" при доступе к /proc/[pid]/task (GH 523).
- Исправлена высокая загрузка ЦП для некоторых сценариев использования pty (GH 488, 504).
- Дополнительные исправления ошибок и усовершенствования.

<br/>

## <a name="build-14371"></a>Сборка 14371
Общие сведения о сборке Windows 14371 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/06/22/announcing-windows-10-insider-preview-build-14371-for-pc/). <br/>

### <a name="fixed"></a>Фиксированный
- Исправлено состязание за синхронизацию SIGCHLD и wait() при использовании ptrace.
- Исправлена обработка путей, которые завершаются косой чертой "/" (GH 432).
- Устранен сбой при переименовании или отмене связи из-за открытых дескрипторов дочерних элементов.
- Дополнительные исправления ошибок и усовершенствования.

<br/>

## <a name="build-14366"></a>Сборка 14366
Общие сведения о сборке Windows 14366 доступны в [блоге о Windows](https://blogs.windows.com/windowsexperience/2016/06/14/announcing-windows-10-insider-preview-build-14366-mobile-build-14364/). <br/>

### <a name="fixed"></a>Фиксированный
- Исправлено создание файла с помощью символических ссылок.
-   Добавлена функция listxattr для Python (GH 385).
-   Дополнительные исправления ошибок и усовершенствования.

### <a name="syscall-support"></a>Поддержка системных вызовов
-   Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`listxattr`<br/>
<br/>

## <a name="build-14361"></a>Сборка 14361
Общие сведения о сборке Windows 14361 доступны в [блоге о Windows](https://aka.ms/wip14361). <br/>

### <a name="fixed"></a>Фиксированный
- Теперь в DrvFs учитывается регистр при выполнении в Bash для Ubuntu в Windows.
  - Пользователи могут хранить на дисках в /mnt/c и файл case.txt, и файл CASE.TXT.
  - Учет регистра поддерживается только в Bash для Ubuntu в Windows. За пределами Bash NTFS будет отображать сведения о файлах правильно, но при взаимодействии с этими файлами из Windows может наблюдаться непредвиденное поведение.
  - Корень каждого тома (т. е. /mnt/c) не учитывает регистр.
  - Дополнительные сведения об обработке этих файлов в Windows можно найти [здесь](https://support.microsoft.com/kb/100625).
- Значительно улучшена поддержка pty и tty.  Теперь поддерживаются такие приложения, как tmux (GH 40).
- Исправлена проблема с установкой, из-за которой учетные записи пользователей создавались не всегда.
- Оптимизирована структура аргументов командной строки, которая позволяет получить очень длинный список аргументов. (GH 153)
- Теперь можно выполнять операции delete и chmod с файлами только для чтения в DrvFs.
- Исправлены некоторые экземпляры, в которых терминал при отключении переставал отвечать на запросы (GH 43).
- Теперь на устройствах tty работает chmod и chown.
- Разрешено подключение к 0.0.0.0 и :: как localhost (GH 388).
- Теперь sendmsg и recvmsg обрабатывают векторы ввода-вывода длиной больше 1 (частично GH 376).
- Теперь пользователи могут отказаться от автоматически создаваемого файла hosts (GH 398).
- Автоматическое сопоставление языкового стандарта Linux с языковым стандартом NT во время установки (GH 11).
- Добавлен файл /proc/sys/vm/swappiness (GH #306).
- Теперь strace завершается правильно.
- Разрешено повторное открытие каналов через /proc/self/fd (GH 222).
- Скрытие каталогов в %LOCALAPPDATA%\lxss из DrvFs (GH 270).
- Улучшена обработка bash.exe ~.  Теперь поддерживаются такие команды, как bash ~ -c ls (GH 467).
- Сокеты теперь уведомляют epoll о доступе на чтение во время завершения (GH 271).
- Команда lxrun /uninstall лучше удаляет файлы и папки.
- Исправлена команда ps -f (GH 246).
- Улучшена поддержка приложений x11, таких как xEmacs (GH 481).
- Обновлен начальный размер стека потока в соответствии с параметром Ubuntu по умолчанию. Теперь при системном вызове get_rlimit размер отображается правильно (GH 172, 258).
- Улучшено отображение имен образов процессов Pico (например, для аудита).
- Реализован файл /proc/mountinfo для команды df.
- Исправлен код ошибки символической ссылки для дочернего имени. И еще:
- Дополнительные улучшения исправлений ошибок и усовершенствования.

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`GETTIMER`<br/>
`MKNODAT`<br/>
`RENAMEAT`<br/>
`SENDFILE`<br/>
`SENDFILE64`<br/>
`SYNC_FILE_RANGE`<br/>
<br/>

## <a name="build-14352"></a>Сборка 14352
Общие сведения о сборке Windows 14352 доступны в [блоге о Windows](https://aka.ms/wip14352).<br/>


### <a name="fixed"></a>Фиксированный
- Исправлена проблема, из-за которой большие файлы скачивались и создавались неправильно.  Это должно позволить использовать npm и реализовать другие сценарии (GH 3, GH 313).
- Удалены некоторые экземпляры, в которых сокеты переставали отвечать на запросы.
- Исправлены некоторые ошибки ptrace.
- Исправлена проблема с WSL, и теперь можно использовать имена файлов длиннее 255 знаков.
- Улучшена поддержка знаков языков, отличных от английского.
- Добавление данных о текущем часовом поясе Windows и назначение его используемым по умолчанию.
- Уникальный идентификатор устройства для каждой точки подключения (исправление JRE — GH 49).
- Устранена ошибка с путями, содержащими . и .. (одну и две точки).
- Добавлена поддержка FIFO (GH 71).
- Обновлен формат resolv.conf в соответствии с собственным форматом Ubuntu.
- Некоторая очистка procfs.
- Включена проверка связи для консолей администратора (GH 18).

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`FALLOCATE`<br/>
`EXECVE`<br/>
`LGETXATTR`<br/>
`FGETXATTR`<br/>
<br/>

## <a name="build-14342"></a>Сборка 14342
Общие сведения о сборке Windows 14342 доступны в [блоге о Windows](https://aka.ms/wip14342). <br/>

Сведения о VolFs и DriveFs можно найти в [блоге о WSL](https://blogs.msdn.microsoft.com/wsl). <br/>

### <a name="fixed"></a>Фиксированный
- Исправлена проблема с установкой, возникавшая, когда в имени пользователя Windows присутствовали знаки Юникода.
- Теперь обходное решение для обновления apt-get с помощью udev, приведенное в разделе часто задаваемых вопросов, предоставляется по умолчанию при первом запуске.
- Включены символические ссылки в каталогах DriveFs (/mnt/<drive>).
- Теперь работают символические ссылки между DriveFs и VolFs.
- Устранена проблема с анализом путей верхнего уровня. Теперь ls .// будет работать должным образом.
- Теперь работает установка npm в DriveFs и параметры -g.
- Исправлена проблема, препятствующая запуску сервера PHP.
- Обновлены значения среды по умолчанию, такие как $PATH, чтобы они больше соответствовали собственным переменным Ubuntu.
- Добавлена еженедельная задача обслуживания в Windows для обновления кэша пакетов apt.
- Исправлена проблема с проверкой заголовков ELF. Теперь WSL поддерживает все параметры Melkor.
- Оболочка Zsh работает.
- Теперь поддерживаются предварительно скомпилированные двоичные файлы Go.
- Теперь запросы при первом запуске bash.exe локализованы правильно.
- Теперь /proc/meminfo возвращает правильные сведения.
- Сокеты теперь поддерживаются в VFS.
- Теперь /dev подключен как tempfs.
- FIFO теперь поддерживается.
- Многоядерные системы теперь правильно отображаются в /proc/cpuinfo.
- Дополнительные улучшения и сообщения об ошибках при скачивании во время первого запуска.
- Усовершенствования и исправления системных вызовов. Список поддерживаемых системных вызовов приведен ниже.
- Дополнительные исправления ошибок и усовершенствования.

### <a name="known-issues"></a>Известные проблемы
- Неправильное разрешение .. (две точки). в DriveFs в некоторых случаях.

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список новых или улучшенных системных вызовов, которые реализованы в WSL. Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`FCHOWNAT`<br/>
`GETEUID`<br/>
`GETGID`<br/>
`GETRESUID`<br/>
`GETXATTR`<br/>
`PTRACE`<br/>
`SETGID`<br/>
`SETGROUPS`<br/>
`SETHOSTNAME`<br/>
`SETXATTR`<br/>
<br/>

## <a name="build-14332"></a>Сборка 14332

Общие сведения о сборке Windows 14332 доступны в [блоге о Windows](https://aka.ms/wip14332). <br/>


### <a name="fixed"></a>Фиксированный
- Улучшенное создание resolv.conf, включая определение приоритета записей DNS.
- Проблема с перемещением файлов и каталогов между дисками в /mnt и прочими дисками.
- Теперь можно создавать TAR-файлы с помощью символических ссылок.
- Добавлен каталог /run/lock по умолчанию, создаваемый при создании экземпляра.
- Обновлен файл /dev/null для возврата правильных сведений stat.
- Дополнительные ошибки при скачивании во время первого запуска.
- Усовершенствования и исправления системных вызовов. Список поддерживаемых системных вызовов приведен ниже.
- Дополнительные улучшения исправлений ошибок и усовершенствования.

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен новый системный вызов, реализованный в WSL. Системный вызов в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут поддерживаться не все параметры.

`READLINKAT`<br/>
<br/>

## <a name="build-14328"></a>Сборка 14328

Общие сведения о сборке Windows 14332 доступны в [блоге о Windows](https://aka.ms/wip14328). <br/>


### <a name="new-features"></a>Новые возможности
* Теперь поддерживаются пользователи Linux.  При установке Bash для Ubuntu в Windows будет предложено создать пользователя Linux.  Дополнительные сведения: https://aka.ms/wslusers
* В качестве имени узла теперь указывается имя компьютера Windows, а не @localhost.
* Дополнительные сведения о сборке 14328: https://aka.ms/wip14328

### <a name="fixed"></a>Фиксированный
* Улучшения символьных ссылок для файлов вне каталога /mnt/<drive>.
    * Теперь установка npm работает.
    * Теперь можно установить JDK или JRE с помощью [этих инструкций](https://xubuntugeek.blogspot.com/2012/09/how-to-install-oracle-jdk-7-manually-in.html).
    * Известная ошибка: символические ссылки не работали для подключений Windows.  Эта функция будет доступна в последующей сборке.
* Теперь отображаются top и htop.
* Дополнительные сообщения об ошибке для некоторых сбоев при установке.
* Усовершенствования и исправления системных вызовов.  Список поддерживаемых системных вызовов приведен ниже.
* Дополнительные улучшения исправлений ошибок и усовершенствования.

### <a name="syscall-support"></a>Поддержка системных вызовов
Ниже приведен список системных вызовов, которые реализованы в WSL.  Системные вызовы в этом списке поддерживается по крайней мере в одном сценарии, но в настоящее время могут не поддерживаться все параметры.

`ACCEPT`<br/>
`ACCEPT4`<br/>
`ACCESS`<br/>
`ALARM`<br/>
`ARCH_PRCTL`<br/>
`BIND`<br/>
`BRK`<br/>
`CAPGET`<br/>
`CAPSET`<br/>
`CHDIR`<br/>
`CHMOD`<br/>
`CHOWN`<br/>
`CLOCK_GETRES`<br/>
`CLOCK_GETTIME`<br/>
`CLOCK_NANOSLEEP`<br/>
`CLONE`<br/>
`CLOSE`<br/>
`CONNECT`<br/>
`CREAT`<br/>
`DUP`<br/>
`DUP2`<br/>
`DUP3`<br/>
`EPOLL_CREATE`<br/>
`EPOLL_CREATE1`<br/>
`EPOLL_CTL`<br/>
`EPOLL_WAIT`<br/>
`EVENTFD`<br/>
`EVENTFD2`<br/>
`EXECVE`<br/>
`EXIT`<br/>
`EXIT_GROUP`<br/>
`FACCESSAT`<br/>
`FADVISE64`<br/>
`FCHDIR`<br/>
`FCHMOD`<br/>
`FCHMODAT`<br/>
`FCHOWN`<br/>
`FCHOWNAT`<br/>
`FCNTL64`<br/>
`FDATASYNC`<br/>
`FLOCK`<br/>
`FORK`<br/>
`FSETXATTR`<br/>
`FSTAT64`<br/>
`FSTATAT64`<br/>
`FSTATFS64`<br/>
`FSYNC`<br/>
`FTRUNCATE`<br/>
`FTRUNCATE64`<br/>
`FUTEX`<br/>
`GETCPU`<br/>
`GETCWD`<br/>
`GETDENTS`<br/>
`GETDENTS64`<br/>
`GETEGID`<br/>
`GETEGID16`<br/>
`GETEUID`<br/>
`GETEUID16`<br/>
`GETGID`<br/>
`GETGID16`<br/>
`GETGROUPS`<br/>
`GETPEERNAME`<br/>
`GETPGID`<br/>
`GETPGRP`<br/>
`GETPID`<br/>
`GETPPID`<br/>
`GETPRIORITY`<br/>
`GETRESGID`<br/>
`GETRESGID16`<br/>
`GETRESUID`<br/>
`GETRESUID16`<br/>
`GETRLIMIT`<br/>
`GETRUSAGE`<br/>
`GETSID`<br/>
`GETSOCKNAME`<br/>
`GETSOCKOPT`<br/>
`GETTID`<br/>
`GETTIMEOFDAY`<br/>
`GETUID`<br/>
`GETUID16`<br/>
`GETXATTR`<br/>
`GET_ROBUST_LIST`<br/>
`GET_THREAD_AREA`<br/>
`INOTIFY_ADD_WATCH`<br/>
`INOTIFY_INIT`<br/>
`INOTIFY_RM_WATCH`<br/>
`IOCTL`<br/>
`IOPRIO_GET`<br/>
`IOPRIO_SET`<br/>
`KEYCTL`<br/>
`KILL`<br/>
`LCHOWN`<br/>
`LINK`<br/>
`LINKAT`<br/>
`LISTEN`<br/>
`LLSEEK`<br/>
`LSEEK`<br/>
`LSTAT64`<br/>
`MADVISE`<br/>
`MKDIR`<br/>
`MKDIRAT`<br/>
`MKNOD`<br/>
`MLOCK`<br/>
`MMAP`<br/>
`MMAP2`<br/>
`MOUNT`<br/>
`MPROTECT`<br/>
`MREMAP`<br/>
`MSYNC`<br/>
`MUNLOCK`<br/>
`MUNMAP`<br/>
`NANOSLEEP`<br/>
`NEWUNAME`<br/>
`OPEN`<br/>
`OPENAT`<br/>
`PAUSE`<br/>
`PERF_EVENT_OPEN`<br/>
`PERSONALITY`<br/>
`PIPE`<br/>
`PIPE2`<br/>
`POLL`<br/>
`PPOLL`<br/>
`PRCTL`<br/>
`PREAD64`<br/>
`PROCESS_VM_READV`<br/>
`PROCESS_VM_WRITEV`<br/>
`PSELECT6`<br/>
`PTRACE`<br/>
`PWRITE64`<br/>
`READ`<br/>
`READLINK`<br/>
`READV`<br/>
`REBOOT`<br/>
`RECV`<br/>
`RECVFROM`<br/>
`RECVMSG`<br/>
`RENAME`<br/>
`RMDIR`<br/>
`RT_SIGACTION`<br/>
`RT_SIGPENDING`<br/>
`RT_SIGPROCMASK`<br/>
`RT_SIGRETURN`<br/>
`RT_SIGSUSPEND`<br/>
`RT_SIGTIMEDWAIT`<br/>
`SCHED_GETAFFINITY`<br/>
`SCHED_GETPARAM`<br/>
`SCHED_GETSCHEDULER`<br/>
`SCHED_GET_PRIORITY_MAX`<br/>
`SCHED_GET_PRIORITY_MIN`<br/>
`SCHED_SETAFFINITY`<br/>
`SCHED_SETPARAM`<br/>
`SCHED_SETSCHEDULER`<br/>
`SCHED_YIELD`<br/>
`SELECT`<br/>
`SEND`<br/>
`SENDMMSG`<br/>
`SENDMSG`<br/>
`SENDTO`<br/>
`SETDOMAINNAME`<br/>
`SETGID`<br/>
`SETGROUPS`<br/>
`SETHOSTNAME`<br/>
`SETITIMER`<br/>
`SETPGID`<br/>
`SETPRIORITY`<br/>
`SETREGID`<br/>
`SETRESGID`<br/>
`SETRESUID`<br/>
`SETREUID`<br/>
`SETRLIMIT`<br/>
`SETSID`<br/>
`SETSOCKOPT`<br/>
`SETTIMEOFDAY`<br/>
`SETUID`<br/>
`SETXATTR`<br/>
`SET_ROBUST_LIST`<br/>
`SET_THREAD_AREA`<br/>
`SET_TID_ADDRESS`<br/>
`SHUTDOWN`<br/>
`SIGACTION`<br/>
`SIGALTSTACK`<br/>
`SIGPENDING`<br/>
`SIGPROCMASK`<br/>
`SIGRETURN`<br/>
`SIGSUSPEND`<br/>
`SOCKET`<br/>
`SOCKETCALL`<br/>
`SOCKETPAIR`<br/>
`SPLICE`<br/>
`STAT64`<br/>
`STATFS64`<br/>
`SYMLINK`<br/>
`SYMLINKAT`<br/>
`SYNC`<br/>
`SYSINFO`<br/>
`TEE`<br/>
`TGKILL`<br/>
`TIME`<br/>
`TIMERFD_CREATE`<br/>
`TIMERFD_GETTIME`<br/>
`TIMERFD_SETTIME`<br/>
`TIMES`<br/>
`TKILL`<br/>
`TRUNCATE`<br/>
`TRUNCATE64`<br/>
`UMASK`<br/>
`UMOUNT`<br/>
`UMOUNT2`<br/>
`UNLINK`<br/>
`UNLINKAT`<br/>
`UNSHARE`<br/>
`UTIME`<br/>
`UTIMENSAT`<br/>
`UTIMES`<br/>
`VFORK`<br/>
`WAIT4`<br/>
`WAITPID`<br/>
`WRITE`<br/>
`WRITEV`<br/>
