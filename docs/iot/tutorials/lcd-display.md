---
title: Anzeigen von Text in einem LC-Display
description: Erfahren Sie, wie Sie Zeichen auf einem Liquid-Crystal-Display mit den .net IOT-Bibliotheken anzeigen.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: d4c3e373207e23877903491871f4d09e11000c1a
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96592111"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="display-text-on-an-lcd"></a>Anzeigen von Text in einem LC-Display

LCD-Zeichen werden zum Anzeigen von Informationen nützlich, ohne dass ein externer Monitor erforderlich ist. Gängige LCD-Zeichen können direkt mit den GPIO-Pins verbunden werden. ein solcher Ansatz erfordert jedoch die Verwendung von bis zu 10 GPIO Pins. Szenarios, die eine Verbindung mit einer Kombination von Geräten erfordern, sind häufig nicht praktikabel.

Viele Hersteller verkaufen 20 x 4 LCD-Zeichen anzeigen mit einem integrierten GPIO-Expander. Die Zeichen Anzeige stellt eine direkte Verbindung mit dem GPIO-Expander her, der dann über das serielle Protokoll der Inter-Integrated Leitung (I2C) eine Verbindung mit dem Raspberry Pi herstellt.

In diesem Thema verwenden Sie .net zum Anzeigen von Text auf einer LCD-Zeichen Anzeige mithilfe eines I2C-GPIO-Expander.

## <a name="prerequisites"></a>Voraussetzungen

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [20 x 4-LCD-Zeichen Anzeige mit der I2C-Schnittstelle](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c)<span class="docon docon-navigate-external x-hidden-focus"></span>
- Jumperdrähte
- Breadboard (optional/empfohlen)
- Raspberry Pi-GPIO-Breakout-Board (optional/empfohlen)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!NOTE]
> Viele Hersteller von LCD-Zeichen werden angezeigt. Die meisten Entwürfe sind identisch, und der Hersteller sollte keinen Unterschied zu den Funktionen treffen. Als Referenz wurde dieses Lernprogramm mit dem [sungründer-LCD2004](https://www.sunfounder.com/lcd2004-module.html) entwickelt <span class="docon docon-navigate-external x-hidden-focus"></span> .

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a>Vorbereiten der Hardware

Verbinden Sie die vier Pins auf dem I2C-GPIO-Expander mithilfe von Jumper-Drähten wie folgt mit dem Raspberry PI:

- GND zu Boden
- VCC zu 5V
- SDA zu SDA (GPIO 2)
- SCL zu SCL (GPIO 3)

Weitere Informationen finden Sie in den folgenden Abbildungen:

| I2C-Schnittstelle (Rückseite der Anzeige) | Raspberry Pi-GPIO |
|---------------------------------|-------------------|
| :::image type="content" source="../media/character-display-i2c-thumb.png" alt-text="Ein Bild der Rückseite der Zeichen Anzeige, die den I2C-GPIO-Expander anzeigt." lightbox="../media/character-display-i2c.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Ein Diagramm, das das Pinout des Raspberry Pi-GPIO-Headers anzeigt. Image-Höflichkeit Raspberry Pi Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br />[Image-Höflichkeit Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span> .
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Erstellen der App

Führen Sie die folgenden Schritte in Ihrer bevorzugten Entwicklungsumgebung aus:

1. Erstellen Sie eine neue .net-Konsolen-APP, indem Sie entweder die [.net-CLI](../../core/tools/dotnet-new.md) oder [Visual Studio](../../core/tutorials/with-visual-studio.md)verwenden. Nennen Sie es *lcdtutorial*.

    ```dotnetcli
    dotnet new console -o LcdTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Ersetzen Sie den Inhalt von *Program.cs* durch den folgenden Code:

    :::code language="csharp" source="~/iot-samples/tutorials/LcdTutorial/Program.cs" :::

    Im obigen Code:

    - Eine [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) erstellt eine Instanz von, `I2cDevice` indem aufgerufen `I2cDevice.Create` und ein neues `I2cConnectionSettings` mit `busId` den `deviceAddress` Parametern und übergeben wird. Dies `I2cDevice` stellt den I2C-Bus dar. Die `using` -Deklaration stellt sicher, dass das Objekt verworfen und Hardware Ressourcen ordnungsgemäß freigegeben werden.

        > [!WARNING]
        > Die Geräteadresse für den GPIO-Expander hängt von dem vom Hersteller verwendeten Chip ab. Bei GPIO-Expander, die mit einem PCF8574 ausgestattet sind, wird die-Adresse verwendet, bei der Verwendung von `0x27` PCF8574A-Chips `0x3F` Weitere Informationen finden Sie in der Dokumentation des LCD.

    - Eine andere `using` Deklaration erstellt eine Instanz von `Pcf8574` und übergibt die an `I2cDevice` den Konstruktor. Diese Instanz stellt den GPIO-Expander dar.
    - Eine andere `using` Deklaration erstellt eine Instanz von `Lcd2004` zur Darstellung der Anzeige. Es werden mehrere Parameter an den Konstruktor übergeben, die die Einstellungen beschreiben, die für die Kommunikation mit dem GPIO-Expander verwendet werden sollen. Der GPIO-Expander wird als- `controller` Parameter übergeben.
    - Eine- `while` Schleife wird unbegrenzt ausgeführt. Jede Iterationen:
        1. Löscht die Anzeige.
        1. Legt die Cursorposition auf die erste Position in der aktuellen Zeile fest.
        1. Schreibt die aktuelle Uhrzeit an der aktuellen Cursorposition in die Anzeige.
        1. Iteriert den aktuellen Zeilen Zählers.
        1. 1000 ms wird nicht mehr angezeigt.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Führen Sie die APP auf dem Raspberry Pi aus, indem Sie zum Bereitstellungs Verzeichnis wechseln und die ausführbare Datei ausführen.

    ```bash
    ./LcdTutorial
    ```

    Sehen Sie sich die Bildschirm Anzeige an, wenn die aktuelle Uhrzeit in jeder Zeile angezeigt wird.

    > [!TIP]
    > Wenn die Anzeige beleuchtet ist, aber kein Text angezeigt wird, versuchen Sie, die Kontrast-Wähl Option auf der Rückseite der Anzeige anzupassen.

1. Beenden Sie das Programm, indem Sie <kbd>STRG + C</kbd>drücken.

Herzlichen Glückwunsch! Sie haben Text auf einem LCD mit einem I2C und einem GPIO-Expander angezeigt.

## <a name="get-the-source-code"></a>Herunterladen des Quellcodes

Die Quelle für dieses Tutorial ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erfahren Sie, wie Sie mit universell Eingabe/Ausgabe eine LED blinken.](../tutorials/blink-led.md)
