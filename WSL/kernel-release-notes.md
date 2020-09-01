---
title: Заметки о выпуске подсистемы Windows для ядра Linux
description: Заметки о выпуске подсистемы Windows для Linux.  Обновляется ежемесячно.
keywords: заметки о выпуске, wsl, windows, подсистема windows для linux, windowssubsystem, ubuntu, ядро
ms.date: 06/09/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: e2409fccada9077adbeac3843c31b8faa2c93208
ms.sourcegitcommit: f1b049a1276782d4f2754f46a8d2025b598a0784
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "85336057"
---
# <a name="release-notes-for-windows-subsystem-for-linux-kernel"></a>Заметки о выпуске подсистемы Windows для ядра Linux

Включена поддержка дистрибутивов WSL 2, [использующих полнофункциональное ядро Linux](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/). Это ядро Linux имеет открытый кодом. Исходный код доступен в репозитории [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel). Это ядро Linux доставляется на компьютер через Центр обновления Майкрософт в соответствии с отдельным графиком выпуска подсистемы Windows для Linux (поставляется в составе образа Windows).

## <a name="419128-microsoft-standard"></a>4.19.128-microsoft-standard
*Дата выпуска:* Предварительный выпуск

[Официальная ссылка на выпуск GitHub](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).

* Это стабильный выпуск 4.19.128
* Исправлена проблема в работе драйвера dxgkrnl приводившая к ошибке управления вводом-вывода памяти (IOCTL memory corruption).

## <a name="419121-microsoft-standard"></a>4.19.121-microsoft-standard
*Дата выпуска:* Предварительный выпуск

[Официальная ссылка на выпуск GitHub](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).

* Драйвера: hv: vmbus: hook up dxgkrnl
* Добавлена поддержка вычислений GPU

## <a name="419104-microsoft-standard"></a>4.19.104-microsoft-standard
*Дата выпуска:* 09.06.2020 

[Официальная ссылка на выпуск GitHub](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).

* Обновление конфигурации WSL для выпуска 4.19.104

## <a name="41984-microsoft-standard"></a>4.19.84-microsoft-standard
*Дата выпуска:* 12.11.2019 

[Официальная ссылка на выпуск GitHub](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).

* Это стабильный выпуск 4.19.84

