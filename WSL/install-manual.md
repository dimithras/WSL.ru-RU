---
title: Скачивание дистрибутивов подсистемы Windows для Linux (WSL) вручную
description: Инструкции по скачиванию дистрибутивов подсистемы Windows для Linux вручную.
keywords: wsl, подсистема windows для linux, установка вручную, microsoft store, windows 10s, curl, add-appxpackage, long-term servicing, ltsc
ms.date: 05/28/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: d948ce9d304314bdd15b98136b8a99ca35723139
ms.sourcegitcommit: e67eb4aedff57a304188ca3360aba25605f8bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2020
ms.locfileid: "84746280"
---
# <a name="manually-download-windows-subsystem-for-linux-distro-packages"></a>Скачивание пакетов дистрибутива подсистемы Windows для Linux вручную

Существует несколько сценариев, в которых вы не сможете (или не захотите) устанавливать дистрибутивы WSL Linux с помощью Microsoft Store. В частности, вы можете использовать номер SKU классической ОС Windows Server или Long-Term Servicing (LTSC), который не поддерживает Microsoft Store, или политики корпоративной сети и административные параметры, запрещающие использовать Microsoft Store в вашей среде.

В таких случаях, когда подсистема WSL доступна, как скачать и установить дистрибутивы Linux в WSL, если нет доступа к магазину?

> Примечание. **Среды оболочки командной строки, в том числе дистрибутивы Linux/WSL, Cmd и PowerShell не могут выполняться в S-режиме Windows 10**. Это ограничение существует, чтобы обеспечить целостность и безопасность, которые предоставляет S-режим. Дополнительные сведения см. в [этой записи блога](https://blogs.msdn.microsoft.com/commandline/2017/05/18/will-linux-distros-run-on-windows-10-s/).

## <a name="downloading-distros"></a>Скачивание дистрибутивов

Если приложение Microsoft Store недоступно, вы можете скачать и вручную установить дистрибутивы Linux, щелкнув следующие ссылки:
* [Ubuntu 20.04](https://aka.ms/wslubuntu2004)
* [Ubuntu 20.04 ARM](https://aka.ms/wslubuntu2004arm)
* [Ubuntu 18.04](https://aka.ms/wsl-ubuntu-1804)
* [Ubuntu 18.04 ARM](https://aka.ms/wsl-ubuntu-1804-arm)
* [Ubuntu 16.04](https://aka.ms/wsl-ubuntu-1604)
* [Debian GNU/Linux](https://aka.ms/wsl-debian-gnulinux)
* [Kali Linux](https://aka.ms/wsl-kali-linux-new)
* [OpenSUSE Leap 42](https://aka.ms/wsl-opensuse-42)
* [SUSE Linux Enterprise Server 12](https://aka.ms/wsl-sles-12)
* [Fedora Remix for WSL](https://github.com/WhitewaterFoundry/WSLFedoraRemix/releases/)

Это приведет к скачиванию пакетов `<distro>.appx` в выбранную папку. Следуйте [инструкциям по установке](#installing-your-distro) скачанных дистрибутивов.

## <a name="downloading-distros-via-the-command-line"></a>Скачивание дистрибутивов с помощью командной строки
При желании вы также можете скачать предпочтительные дистрибутивы с помощью командной строки.

 ### <a name="download-using-powershell"></a>Скачивание с помощью PowerShell
 Чтобы скачать дистрибутивы с помощью PowerShell, используйте командлет [Invoke-WebRequest](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1). Ниже приведены инструкции по скачиванию Ubuntu 16.04.

```powershell
Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1604 -OutFile Ubuntu.appx -UseBasicParsing
```

> [!TIP]
> Если загрузка занимает много времени, выключите индикатор выполнения, задав `$ProgressPreference = 'SilentlyContinue'`.

### <a name="download-using-curl"></a>Скачивание с помощью cURL
Обновление Windows 10 Spring 2018 (или более поздней версии) содержит популярную [служебную программу командной строки cURL](https://curl.haxx.se/), с помощью которой можно вызывать веб-запросы (например, команды HTTP GET, POST, PUT и т. д.) из командной строки. Вы можете использовать `curl.exe`, чтобы скачать приведенные выше дистрибутивы:

```console
curl.exe -L -o ubuntu-1604.appx https://aka.ms/wsl-ubuntu-1604
```

В приведенном выше примере выполняется `curl.exe` (а не только `curl`), чтобы убедиться, что в PowerShell вызывается реальный исполняемый файл cURL, а не его псевдоним для [Invoke-WebRequest](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-6).

> Примечание. Использование `curl` может быть предпочтительным, если необходимо вызвать или создать сценарий для скачивания с помощью командлетов командной строки и сценариев `.bat` / `.cmd`.

## <a name="installing-your-distro"></a>Установка дистрибутива
Если вы используете Windows 10, вы можете установить дистрибутив с помощью PowerShell. Просто перейдите в папку, содержащую скачанный выше дистрибутив, и в этом каталоге выполните следующую команду, в которой `app_name` — это имя APPX-файла дистрибутива.  
```Powershell
Add-AppxPackage .\app_name.appx
```

Если вы используете сервер Windows, инструкции по установке можно найти на странице документации [Windows Server](install-on-server.md).

После установки дистрибутива следуйте обычным инструкциям по [обновлению до WSL 2](./install-win10.md#update-to-wsl-2) или [создайте новую учетную запись пользователя и пароль](./user-support.md).
