---
title: Blinken einer LED
description: Erfahren Sie, wie Sie eine LED mit den .net IOT-Bibliotheken blinken.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 07a050c0655f9cae3d7f2b924c0dd07ac1c6c0b9
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96592116"
---
# <a name="blink-an-led"></a>Blinken einer LED

Allgemeine e/a-Pins (GPIO) können einzeln gesteuert werden. Dies ist nützlich, um LEDs, Relays und andere Zustands behaftete Geräte zu steuern. In diesem Thema verwenden Sie .net und die GPIO-Pins Ihres Raspberry Pi zum Einschalten einer LED und zum wiederholten blinken.

## <a name="prerequisites"></a>Voraussetzungen

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- 5-mm-LED
- 330.
- Breadboard
- Jumperdrähte
- Raspberry Pi-GPIO-Breakout-Board (optional/empfohlen)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [ensure-ssh](../includes/ensure-ssh.md)]

## <a name="prepare-the-hardware"></a>Vorbereiten der Hardware

Verwenden Sie die Hardwarekomponenten, um die Verbindung zu erstellen, wie im folgenden Diagramm dargestellt:

:::image type="content" source="../media/rpi-led_bb-thumb.png" alt-text="Ein fritzingdiagramm, das eine Verbindung mit einer LED und einem Gegenstand anzeigt" lightbox="../media/rpi-led_bb.png":::

Die obige Abbildung zeigt die folgenden Verbindungen:

- GPIO 18 bis LED-Anoden (länger, positiver Lead)
- LED-Kathode (kürzer, negativer Lead) zu 330. Gegenstand (beide Enden)
- 330. Gegenstand (anderes Ende) bis zum Grund

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Erstellen der App

Führen Sie die folgenden Schritte in Ihrer bevorzugten Entwicklungsumgebung aus:

1. Erstellen Sie eine neue .net-Konsolen-APP, indem Sie entweder die [.net-CLI](../../core/tools/dotnet-new.md) oder [Visual Studio](../../core/tutorials/with-visual-studio.md)verwenden. Nennen Sie es *blinktutorial*.

    ```dotnetcli
    dotnet new console -o BlinkTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Ersetzen Sie den Inhalt von *Program.cs* durch den folgenden Code:

    :::code language="csharp" source="~/iot-samples/tutorials/BlinkTutorial/Program.cs" :::

    Im obigen Code:

    - Eine [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) erstellt eine Instanz von `GpioController` . Die `using` -Deklaration stellt sicher, dass das Objekt verworfen und Hardware Ressourcen ordnungsgemäß freigegeben werden.
    - GPIO Pin 18 ist für die Ausgabe geöffnet
    - Eine- `while` Schleife wird unbegrenzt ausgeführt. Jede Iterationen:
        1. Schreibt einen Wert in GPIO Pin 18. Wenn `ledOn` den Wert true hat, schreibt er `PinValue.High` (on). Andernfalls wird geschrieben `PinValue.Low` .
        1. 1000 ms wird nicht mehr angezeigt.
        1. Schaltet den Wert von um `ledOn` .

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Führen Sie die APP auf dem Raspberry Pi aus, indem Sie zum Bereitstellungs Verzeichnis wechseln und die ausführbare Datei ausführen.

    ```bash
    ./BlinkTutorial
    ```

    Die LED gibt eine Verknüpfung von und auf jeder Sekunde aus.

1. Beenden Sie das Programm, indem Sie <kbd>STRG + C</kbd>drücken.

Herzlichen Glückwunsch! Sie haben GPIO verwendet, um eine LED zu blinken.

## <a name="get-the-source-code"></a>Herunterladen des Quellcodes

Die Quelle für dieses Tutorial ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erfahren Sie, wie Sie Umgebungsbedingungen von einem Sensor aus lesen.](../tutorials/temp-sensor.md)
