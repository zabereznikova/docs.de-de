---
title: Lesen von Werten aus einem Analog-zu-Digital-Konverter
description: Erfahren Sie, wie Sie Variable Spannungswerte mithilfe eines Analog-zu-Digital Konverters lesen.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 7cf25f181997ed66639842727be57e7824ef5466
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739986"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="read-values-from-an-analog-to-digital-converter"></a>Lesen von Werten aus einem Analog-zu-Digital-Konverter

Ein "analog-zu-Digital Converter" (ADC) ist ein Gerät, das einen analogen Eingangs Spannungswert lesen und in einen digitalen Wert konvertieren kann. ADCs dient zum Lesen von Werten von Thermistoren, artefaktometern und anderen Geräten, die den Widerstand auf der Grundlage bestimmter Bedingungen ändern.

In diesem Thema verwenden Sie .net, um Werte aus einem ADC zu lesen, während Sie die Eingabe Spannung mit einem potenzimesser modulieren.

## <a name="prerequisites"></a>Voraussetzungen

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [MCP3008](https://www.microchip.com/wwwproducts/MCP3008) <span class="docon docon-navigate-external x-hidden-focus"></span> Analog zu Digital Converter
- Drei-Pin-potenzimesser
- Breadboard
- Jumperdrähte
- Raspberry Pi-GPIO-Breakout-Board (optional/empfohlen)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [prepare-pi-spi](../includes/prepare-pi-spi.md)]

## <a name="prepare-the-hardware"></a>Vorbereiten der Hardware

Verwenden Sie die Hardwarekomponenten, um die Verbindung zu erstellen, wie im folgenden Diagramm dargestellt:

:::image type="content" source="../media/rpi-trimpot_spi-thumb.png" alt-text="Ein fritzterdiagramm, das eine Verbindung mit einem MCP3008 ADC und einem potenzimesser anzeigt" lightbox="../media/rpi-trimpot_spi.png":::

Der MCP3008 verwendet die Serial Peripherie Interface (SPI) für die Kommunikation. Im folgenden finden Sie die Verbindungen zwischen MCP3008 und Raspberry Pi und dem-potenzimesser:

- V<sub>TT bis 3.3</sub> v (rot dargestellt)
- V<sub>ref</sub> zu 3.3 v (rot)
- Zu Boden (schwarz)
- CLK zu SCLK (Orange)
- D<sub>out</sub> an Miso (Orange)
- D<sub>in</sub> zu "Musi" (Orange)
- CS/SHDN in ce0 (grün)
- DGND bis Boden (schwarz)
- CH0-to-Variable (mittlere) Pin auf dem potenzierer (gelb)

Geben Sie 3.3 v und Boden für die äußeren Pins des potenzimessers an. Die Reihenfolge ist unwichtig.

Weitere Informationen finden Sie in den folgenden Pinout-Diagrammen:

| MCP3008  | Raspberry Pi-GPIO |
|----------|-------------------|
| :::image type="content" source="../media/mcp3008-diagram-thumb.png" alt-text="Ein Diagramm mit dem Pinout des MCP3008" lightbox="../media/mcp3008-diagram.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Ein Diagramm, das das Pinout des Raspberry Pi-GPIO-Headers anzeigt. Image-Höflichkeit Raspberry Pi Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br />[Image-Höflichkeit Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Erstellen der App

Führen Sie die folgenden Schritte in Ihrer bevorzugten Entwicklungsumgebung aus:

1. Erstellen Sie eine neue .net-Konsolen-APP, indem Sie entweder die [.net-CLI](../../core/tools/dotnet-new.md) oder [Visual Studio](../../core/tutorials/with-visual-studio.md)verwenden. Nennen Sie Sie " *adctutorial*".

    ```dotnetcli
    dotnet new console -o AdcTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Ersetzen Sie den Inhalt von *Program.cs* durch den folgenden Code:

    :::code language="csharp" source="~/iot-samples/tutorials/AdcTutorial/Program.cs" :::

    Für den Code oben gilt:

    - `hardwareSpiSettings` wird auf eine neue Instanz von festgelegt `SpiConnectionSettings` . Der-Konstruktor legt den `busId` -Parameter auf 0 und den- `chipSelectLine` Parameter auf 0 fest.
    - Eine [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) erstellt eine Instanz von, `SpiDevice` indem aufgerufen `SpiDevice.Create` und übergeben wird `hardwareSpiSettings` . Dies `SpiDevice` stellt den SPI-Bus dar. Die `using` -Deklaration stellt sicher, dass das Objekt verworfen und Hardware Ressourcen ordnungsgemäß freigegeben werden.
    - Eine andere `using` Deklaration erstellt eine Instanz von `Mcp3008` und übergibt die an `SpiDevice` den Konstruktor.
    - Eine- `while` Schleife wird unbegrenzt ausgeführt. Jede Iterationen:
        1. Liest den Wert von CH0 auf dem ADC durch Aufrufen von `mcp.Read(0)` .
        1. Dividiert den Wert durch 10,24. Der MCP3008 ist ein 10-Bit-ADC, d. h., es werden 1024 mögliche Werte im Bereich von 0-1023 zurückgegeben. Durch die Aufteilung des Werts durch 10,24 wird der Wert als Prozentsatz dargestellt.
        1. Rundet den Wert auf die nächste ganze Zahl.
        1. Schreibt den Wert in die Konsole, die als Prozentsatz formatiert ist.
        1. 500 ms wird nicht mehr angezeigt.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Führen Sie die APP auf dem Raspberry Pi aus, indem Sie zum Bereitstellungs Verzeichnis wechseln und die ausführbare Datei ausführen.

    ```bash
    ./AdcTutorial
    ```

    Sehen Sie sich die Ausgabe an, während Sie die Leistungs Messer-Wahl drehen. Dies ist darauf zurückzuführen, dass der Potentiometer die für CH0 auf dem ADC angegebene Spannung variiert. Der ADC vergleicht die Eingangsspannung auf CH0 mit der für V<sub>ref</sub> angegebenen Referenzspannung, um einen Wert zu generieren.

1. Beenden Sie das Programm, indem Sie <kbd>STRG + C</kbd>drücken.

Glückwunsch! Sie haben SPI zum Lesen von Werten aus einem analog-zu-Digital-Konverter verwendet.

## <a name="get-the-source-code"></a>Herunterladen des Quellcodes

Die Quelle für dieses Tutorial ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erfahren Sie, wie Sie mit universell Eingabe/Ausgabe eine LED blinken.](../tutorials/blink-led.md)
