---
title: Установка подсистемы Windows для Linux (WSL) в Windows 10
description: Инструкции по установке подсистемы Windows для Linux в Windows 10.
keywords: BashOnWindows, bash, wsl, windows, подсистема windows для linux, windowssubsystem, ubuntu, debian, suse, windows 10, установка, включить, WSL2, версия 2
ms.date: 08/31/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: bab21722e77a0879db70e21003fb237491d99218
ms.sourcegitcommit: 90577817a9321949da2a3971b4c78bb00f6d977f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2020
ms.locfileid: "88039445"
---
# <a name="windows-subsystem-for-linux-installation-guide-for-windows-10"></a>Руководство по установке подсистемы Windows для Linux в Windows 10

## <a name="install-the-windows-subsystem-for-linux"></a>Установка подсистемы Windows для Linux

Перед установкой дистрибутивов Linux в Windows необходимо включить дополнительный компонент "Подсистема Windows для Linux".

Запустите PowerShell с правами администратора и выполните следующую команду.

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

Чтобы установить только WSL 1, необходимо перезагрузить компьютер и перейти к пункту [Install your Linux distribution of choice](./install-win10.md#install-your-linux-distribution-of-choice) (Установить дистрибутив Linux), в противном случае дождитесь перезапуска и переходите к обновлению до WSL 2. Узнайте больше о [сравнении WSL 2 и WSL 1](./compare-versions.md).

## <a name="update-to-wsl-2"></a>Обновление до WSL 2

Чтобы выполнить обновление до WSL 2, необходимо выполнить следующие условия:

- Использовать Windows 10 с [обновлением до версии 1903](ms-settings:windowsupdate), **сборкой 18362** или более поздней версии для 64-битных систем.
- Использовать Windows 10 с [обновлением до версии 2004](ms-settings:windowsupdate), **сборкой 19041** или более поздней версии для ARM64 систем.
- Обратите внимание: если вы используете Windows 10 версии 1093 или 1090, убедитесь, что у вас правильный патч для данной версии. Инструкции описаны [здесь](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/#how-do-i-get-it).

- Проверьте версию Windows, нажав **Windows + R**, введите **winver**, выберите **ОК**. (Или введите команду `ver` в командной строке Windows). [Обновите последнюю версию Windows](ms-settings:windowsupdate), если сборка ниже 18361. [Помощник по Центру обновления Windows](https://www.microsoft.com/software-download/windows10).

### <a name="enable-the-virtual-machine-platform-optional-component"></a>Включение дополнительного компонента "Virtual Machine Platform" (Платформа виртуальной машины)

Перед установкой WSL 2 необходимо включить дополнительный компонент "Virtual Machine Platform" (Платформа виртуальных машин).

Запустите PowerShell с правами администратора и выполните следующую команду.

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

**Перезапустите** компьютер, чтобы завершить установку и обновление WSL до WSL 2.

### <a name="set-wsl-2-as-your-default-version"></a>Установка WSL 2 в качестве версии по умолчанию

Откройте PowerShell от имени администратора и выполните следующую команду, чтобы задать WSL 2 в качестве версии по умолчанию при установке нового дистрибутива Linux:

```powershell
wsl --set-default-version 2
```

После выполнения этой команды может появиться следующее сообщение: `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`. Перейдите по ссылке ([https://aka.ms/wsl2kernel](https://aka.ms/wsl2kernel)) и установите MSI-файл с этой страницы документации, чтобы установить на компьютере ядро Linux для WSL 2. После установки ядра выполните команду еще раз. Она должна успешно завершиться без отображения сообщения.

> [!NOTE]
> Обновление с WSL 1 до WSL 2 может занять несколько минут в зависимости от размера целевого дистрибутива. Если вы используете устаревшую установку WSL 1 из Юбилейного обновления Windows 10 или обновления Creators Update, может возникнуть ошибка обновления. Выполните эти инструкции, чтобы [удалить устаревшие дистрибутивы](https://docs.microsoft.com/windows/wsl/install-legacy#uninstallingremoving-the-legacy-distro).
>
> Если `wsl --set-default-version` выполняется как недопустимая команда, введите `wsl --help`. Если `--set-default-version` нет в списке, это указывает на отсутствие поддержки в ОС. Вам нужно выполнить обновление до версии 1903, сборки 18362 или более поздней.

## <a name="install-your-linux-distribution-of-choice"></a>Установка дистрибутива Linux по выбору

1. Откройте [Microsoft Store](https://aka.ms/wslstore) и выберите предпочтительный дистрибутив Linux.

    ![Представление дистрибутивов Linux в Microsoft Store](media/store.png)

    Ниже приведены ссылки на страницы Microsoft Store для каждого дистрибутива:

    - [Ubuntu 16.04 LTS](https://www.microsoft.com/store/apps/9pjn388hp8c9)
    - [Ubuntu 18.04 LTS](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
    - [Ubuntu 20.04 LTS](https://www.microsoft.com/store/apps/9n6svws3rx71)
    - [openSUSE Leap 15.1](https://www.microsoft.com/store/apps/9NJFZK00FGKV)
    - [SUSE Linux Enterprise Server 12 SP5](https://www.microsoft.com/store/apps/9MZ3D1TRP8T1)
    - [SUSE Linux Enterprise Server 15 SP1](https://www.microsoft.com/store/apps/9PN498VPMF3Z)
    - [Kali Linux](https://www.microsoft.com/store/apps/9PKR34TNCV07)
    - [Debian GNU/Linux](https://www.microsoft.com/store/apps/9MSVKQC78PK6)
    - [Fedora Remix for WSL](https://www.microsoft.com/store/apps/9n6gdm4k2hnc)
    - [Pengwin](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
    - [Pengwin Enterprise](https://www.microsoft.com/store/apps/9N8LP0X93VCP)
    - [Alpine WSL](https://www.microsoft.com/store/apps/9p804crf0395)

2. На странице дистрибутива щелкните "Получить".

    ![Дистрибутивы Linux в Microsoft Store](media/UbuntuStore.png)

## <a name="set-up-a-new-distribution"></a>Настройка нового дистрибутива

При первом запуске недавно установленного дистрибутива Linux откроется окно консоли, и вам будет предложено подождать минуту или две, чтобы файлы распаковались и сохранились на компьютере. Все будущие запуски должны занимать меньше секунды.

Затем необходимо будет [создать учетную запись пользователя и пароль для нового дистрибутива Linux](./user-support.md).

![Распаковка Ubuntu в консоли Windows](media/UbuntuInstall.png)

## <a name="set-your-distribution-version-to-wsl-1-or-wsl-2"></a>Установите вашу версию дистрибутива на WSL 1 или WSL 2

Вы можете проверить версию WSL, назначенную каждому из установленных дистрибутивов Linux, открыв командную строку PowerShell и введя команду (доступна только в [сборке Windows 18362](ms-settings:windowsupdate) или более поздней версии): `wsl -l -v`.

```powershell
wsl --list --verbose
```

Чтобы настроить дистрибутив для одной из версий WSL, выполните:

```powershell
wsl --set-version <distribution name> <versionNumber>
```

Не забудьте заменить `<distribution name>` на фактическое имя дистрибутива и `<versionNumber>` на номер "1" или "2". Вы можете всегда вернуться к WSL версии 1, выполнив эту команду и заменив "2" на "1".

Кроме того, если вы хотите сделать WSL 2 архитектурой по умолчанию, выполните следующую команду:

```powershell
wsl --set-default-version 2
```

Будет установлена версия любого нового дистрибутива, установленного в WSL 2.

## <a name="troubleshooting-installation"></a>Устранение неполадок установки

Ниже перечислены возможные ошибки и способы их устранения. Другие распространенные ошибки и способы их устранения приведены в разделе [Устранение неполадок подсистемы Windows для Linux](troubleshooting.md).

- **Сбой установки с ошибкой 0x80070003**
  - Подсистема Windows для Linux работает только на системном диске (обычно это диск `C:`). Убедитесь, что дистрибутивы хранятся на системном диске.  
  - Выберите **Параметры** -> **Хранилище** -> **More Storage Settings: (Другие параметры хранилища:) Изменить место сохранения нового содержимого**.
    ![Изображение параметров системы для установки приложений на диске C:](media/AppStorage.png)

- **Сбой WslRegisterDistribution с ошибкой 0x8007019e**
  - Дополнительный компонент "Подсистема Windows для Linux" не включен.
  - Выберите **Панель управления** -> **Программы и компоненты** -> **Включение или отключение компонентов Windows** и установите флажок **Подсистема Windows для Linux** или используйте командлет PowerShell, упомянутый в начале этой статьи.

- **Сбой установки с ошибкой 0x80070003 или ошибкой 0x80370102**
  - Убедитесь, что в BIOS вашего компьютера включена виртуализация. Расположение этого параметра зависит от компьютера, но обычно он находится в разделе настроек ЦП.

- **При попытке обновления возникает ошибка `Invalid command line option: wsl --set-version Ubuntu 2`.**
  - Убедитесь, что у вас включена подсистема Windows для Linux и используется сборка Windows 18362 или более поздней версии. Чтобы включить WSL, выполните эту команду в командной строке PowerShell с правами администратора: `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`.

- **Запрошенную операцию не удалось выполнить из-за ограничения системы виртуального диска. Файлы виртуального жесткого диска должны быть распакованными, незашифрованными и не разреженными.**
  - Снимите флажок “Compress contents” (Сжимать содержимое) (а также флажок “Encrypt contents” (Шифровать содержимое), если он установлен), открыв папку профиля для дистрибутива Linux. Он должен находиться в подпапке файловой системы Windows, примерный путь: `USERPROFILE%\AppData\Local\Packages\CanonicalGroupLimited...`.
  - В этом профиле дистрибутива Linux должна находиться папка LocalState. Щелкните эту папку правой кнопкой мыши, чтобы отобразить меню параметров. Выберите Properties (Свойства) > Advanced (Дополнительно) и убедитесь, что флажки для “Compress contents to save disk space” (Сжимать содержимое для экономии места на диске) и “Encrypt contents to secure data” (Шифровать содержимое для защиты данных) не установлены. Если вы увидите запрос на применение параметров к текущей папке или ко всем вложенным папкам, подпапкам и файлам, выберите вариант “just this folder” (только для текущей папки), поскольку вы снимаете флажок для сжатия. После этого команда `wsl --set-version` должна работать правильно.

![Снимок экрана с параметрами свойств дистрибутива WSL](media/troubleshooting-virtualdisk-compress.png)

> [!NOTE]
> В этом примере папка LocalState для дистрибутива Ubuntu 18.04 расположена по адресу C:\Users\<my-user-name>\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc
>
> Чтобы получить обновленные сведения, проверьте [ветку № 4103 в документации GitHub WSL Docs](https://github.com/microsoft/WSL/issues/4103), где отслеживается эта проблема.

- **Термин WSL не распознан как имя командлета, функции, файла скрипта или действующей программы.**
  - Убедитесь, что установлен дополнительный компонент [Подсистема Windows для Linux](./install-win10.md#enable-the-virtual-machine-platform-optional-component). Кроме того, эта ошибка возникнет, если вы используете устройство на базе ARM64 и выполняете эту команду в PowerShell. Вместо этого запустите `wsl.exe` из [PowerShell Core](https://docs.microsoft.com/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-6) или командной строки.
