---
title: Lesen von Umgebungsbedingungen aus einem Sensor
description: Erfahren Sie, wie Sie mit den .net-IOT-Bibliotheken termperklsie, barometrischen Druck und Luftfeuchtigkeit lesen können.
author: camsoper
ms.author: casoper
ms.date: 11/14/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: 1270e7629e9afc12b1d76d260d4b8b51428f1040
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96592117"
---
# <a name="read-environmental-conditions-from-a-sensor"></a>Lesen von Umgebungsbedingungen aus einem Sensor

Eines der gängigsten Szenarien für IOT-Geräte ist das Erkennen von Umgebungsbedingungen. Es stehen eine Vielzahl von Sensoren zur Verfügung, um Temperatur, Luftfeuchtigkeit, den barometrischen Druck und mehr zu überwachen.

In diesem Thema verwenden Sie .net zum Lesen von Umgebungsbedingungen von einem Sensor.

## <a name="prerequisites"></a>Voraussetzungen

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- [BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) <span class="docon docon-navigate-external x-hidden-focus"></span> Luftfeuchtigkeit/der Druck/Temperatursensor-Breakout
- Jumperdrähte
- Breadboard (optional)
- Raspberry Pi-GPIO-Breakout-Board (optional)
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!IMPORTANT]
> Es gibt viele Hersteller von BME280 Breakouts. Die meisten Entwürfe sind ähnlich, und der Hersteller sollte keinen Unterschied zu den Funktionen treffen. In diesem Tutorial wird versucht, Variationen zu berücksichtigen. Stellen Sie sicher, dass BME280 Breakout eine Schnittstelle für die Inter-Integrated Leitung (I2C) enthält.

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a>Vorbereiten der Hardware

Verwenden Sie die Hardwarekomponenten, um die Verbindung zu erstellen, wie im folgenden Diagramm dargestellt:

:::image type="content" source="../media/rpi-bmp280_i2c-thumb.png" alt-text="Ein Listen Diagramm, das die Verbindung zwischen Raspberry Pi und BME280 Breakout Board anzeigt." lightbox="../media/rpi-bmp280_i2c.png":::

Im folgenden sind die Verbindungen vom Raspberry Pi zum BME280-Breakout aufgeführt:

- 3.3 v bis Vin *oder* 3v3 (rot dargestellt)
- Zwischen Grund und GND (schwarz)
- SDA (GPIO 2) mit SDI *oder* SDA (blau)
- SCL (GPIO 3) zu SCK *oder* SCL (Orange)

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a>Erstellen der App

Führen Sie die folgenden Schritte in Ihrer bevorzugten Entwicklungsumgebung aus:

1. Erstellen Sie eine neue .net-Konsolen-APP, indem Sie entweder die [.net-CLI](../../core/tools/dotnet-new.md) oder [Visual Studio](../../core/tutorials/with-visual-studio.md)verwenden. Nennen Sie es *sensortutorial*.

    ```dotnetcli
    dotnet new console -o SensorTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. Ersetzen Sie den Inhalt von *Program.cs* durch den folgenden Code:

    :::code language="csharp" source="~/iot-samples/tutorials/SensorTutorial/Program.cs" :::

    Im obigen Code:

    - `i2cSettings` wird auf eine neue Instanz von festgelegt `I2cConnectionSettings` . Der-Konstruktor legt den `busId` -Parameter auf 1 und den- `deviceAddress` Parameter auf fest `Bme280.DefaultI2cAddress` .

        > [!IMPORTANT]
        > Einige BME280-Breakout-Hersteller verwenden den sekundären Adress Wert. Verwenden Sie für diese Geräte `Bme280.SecondaryI2cAddress` .

    - Eine [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) erstellt eine Instanz von, `I2cDevice` indem aufgerufen `I2cDevice.Create` und übergeben wird `i2cSettings` . Dies `I2cDevice` stellt den I2C-Bus dar. Die `using` -Deklaration stellt sicher, dass das Objekt verworfen und Hardware Ressourcen ordnungsgemäß freigegeben werden.
    - Eine andere `using` Deklaration erstellt eine Instanz von `Bme280` , die den Sensor darstellt. Das-Element `I2cDevice` wird im-Konstruktor übergeben.
    - Die Zeit, die der Chip zum Übernehmen von Messungen mit den aktuellen (Standard-) Einstellungen des Chips benötigt, wird durch Aufrufen von abgerufen `GetMeasurementDuration` .
    - Eine- `while` Schleife wird unbegrenzt ausgeführt. Jede Iterationen:
        1. Löscht die Konsole.
        1. Legt den Energie Modus auf fest `Bmx280PowerMode.Forced` . Dies zwingt den Chip, eine Messung durchzuführen, die Ergebnisse zu speichern und dann in den Standbymodus zu versetzen.
        1. Liest die Werte für Temperatur, Druck, Luftfeuchtigkeit und Höhe.

            > [!NOTE]
            > Die Höhe wird von der Geräte Bindung berechnet. Diese Überladung von `TryReadAltitude` verwendet den Mittel sebene Druck, um eine Schätzung zu generieren.

        1. Schreibt die aktuellen Umgebungsbedingungen in die Konsole.
        1. 1000 ms wird nicht mehr angezeigt.

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. Führen Sie die APP auf dem Raspberry Pi aus, indem Sie zum Bereitstellungs Verzeichnis wechseln und die ausführbare Datei ausführen.

    ```bash
    ./SensorTutorial
    ```

    Beachten Sie die sensorausgabe in der Konsole.

1. Beenden Sie das Programm, indem Sie <kbd>STRG + C</kbd>drücken.

Herzlichen Glückwunsch! Sie haben I2C verwendet, um Werte von einem Temperatur-/Luftfeuchtigkeits-/barometrischen Drucksensor zu lesen.

## <a name="get-the-source-code"></a>Herunterladen des Quellcodes

Die Quelle für dieses Tutorial ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erfahren Sie, wie Sie Text auf einem LCD anzeigen.](../tutorials/lcd-display.md)
