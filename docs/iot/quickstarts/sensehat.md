---
title: 'Schnellstart: Verwenden von .net zum Steuern eines Raspberry Pi-Sense'
description: Legen Sie in den ersten Schritten mit .net IOT-Bibliotheken in 5 Minuten mithilfe eines Sense-hat, einem Add-on-Board für Raspberry Pi, Los.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: quickstart
ms.prod: dotnet
ms.openlocfilehash: 2919db55304590f5557aa0cbda50cc4bd6640443
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739529"
---
# <a name="quickstart---use-net-to-drive-a-raspberry-pi-sense-hat"></a>Schnellstart: Verwenden von .net zum Steuern eines Raspberry Pi-Sense

Der Raspberry Pi [Sense hat](https://www.raspberrypi.org/products/sense-hat/) <span class="docon docon-navigate-external x-hidden-focus"></span> (**H** Hardware **A** ttached on **T** OP) ist ein Add-on-Board für Raspberry Pi. Der Sense verfügt über eine 8 × 8-RGB-LED-Matrix, eine Schaltfläche mit fünf Schaltflächen und umfasst die folgenden Sensoren:

- Gyroskop
- Beschleunigungsmesser
- Magnetometer
- Temperatur
- Barometrischer Druck
- Luftfeuchtigkeit

In dieser Schnellstartanleitung wird .NET verwendet, um Sensorwerte aus dem Sense-hat abzurufen, auf die Joystick Eingabe zu Antworten und die LED-Matrix zu steuern.

## <a name="prerequisites"></a>Voraussetzungen

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- Sense hat

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="run-the-quickstart"></a>Ausführen des Schnellstarts

Fügen Sie die Sense-hat an Ihren Raspberry Pi an. Führen Sie an einer bash-Eingabeaufforderung auf dem Raspberry PI (lokal oder Remote) den folgenden Befehl aus:

```bash
. <(wget -q -O - https://aka.ms/dotnet-iot-sensehat-quickstart)
```

Der Befehl lädt ein Skript herunter und führt es aus. Mit dem Skript wird Folgendes durchgeführt:

- Installiert das .NET SDK.
- Klont ein GitHub-Repository, das das Sense hat-Schnellstart Projekt enthält.
- Erstellt das Projekt.
- Führt das Projekt aus.

Beachten Sie die Konsolenausgabe, wenn Sensordaten angezeigt werden. Die LED-Matrix zeigt ein gelbes Pixel in einem blauen Feld an. Wenn Sie den Joystick in beliebiger Richtung halten, wird das gelbe Pixel in diese Richtung verschoben. Wenn Sie auf die Schaltfläche "Zentrieren" klicken, wechselt der Hintergrund von blau zu rot.

## <a name="get-the-source-code"></a>Herunterladen des Quellcodes

Die Quelle für diesen Schnellstart ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart) <span class="docon docon-navigate-external x-hidden-focus"></span> .

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erfahren Sie, wie Sie mit universell Eingabe/Ausgabe eine LED blinken.](../tutorials/blink-led.md)
