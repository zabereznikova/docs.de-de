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
# <a name="quickstart---use-net-to-drive-a-raspberry-pi-sense-hat"></a><span data-ttu-id="6b369-103">Schnellstart: Verwenden von .net zum Steuern eines Raspberry Pi-Sense</span><span class="sxs-lookup"><span data-stu-id="6b369-103">Quickstart - Use .NET to drive a Raspberry Pi Sense HAT</span></span>

<span data-ttu-id="6b369-104">Der Raspberry Pi [Sense hat](https://www.raspberrypi.org/products/sense-hat/) <span class="docon docon-navigate-external x-hidden-focus"></span> (**H** Hardware **A** ttached on **T** OP) ist ein Add-on-Board für Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="6b369-104">The Raspberry Pi [Sense HAT](https://www.raspberrypi.org/products/sense-hat/) <span class="docon docon-navigate-external x-hidden-focus"></span> (**H** ardware **A** ttached on **T** op) is an add-on board for Raspberry Pi.</span></span> <span data-ttu-id="6b369-105">Der Sense verfügt über eine 8 × 8-RGB-LED-Matrix, eine Schaltfläche mit fünf Schaltflächen und umfasst die folgenden Sensoren:</span><span class="sxs-lookup"><span data-stu-id="6b369-105">The Sense HAT is equipped with an 8×8 RGB LED matrix, a five-button joystick, and includes the following sensors:</span></span>

- <span data-ttu-id="6b369-106">Gyroskop</span><span class="sxs-lookup"><span data-stu-id="6b369-106">Gyroscope</span></span>
- <span data-ttu-id="6b369-107">Beschleunigungsmesser</span><span class="sxs-lookup"><span data-stu-id="6b369-107">Accelerometer</span></span>
- <span data-ttu-id="6b369-108">Magnetometer</span><span class="sxs-lookup"><span data-stu-id="6b369-108">Magnetometer</span></span>
- <span data-ttu-id="6b369-109">Temperatur</span><span class="sxs-lookup"><span data-stu-id="6b369-109">Temperature</span></span>
- <span data-ttu-id="6b369-110">Barometrischer Druck</span><span class="sxs-lookup"><span data-stu-id="6b369-110">Barometric pressure</span></span>
- <span data-ttu-id="6b369-111">Luftfeuchtigkeit</span><span class="sxs-lookup"><span data-stu-id="6b369-111">Humidity</span></span>

<span data-ttu-id="6b369-112">In dieser Schnellstartanleitung wird .NET verwendet, um Sensorwerte aus dem Sense-hat abzurufen, auf die Joystick Eingabe zu Antworten und die LED-Matrix zu steuern.</span><span class="sxs-lookup"><span data-stu-id="6b369-112">This quickstart uses .NET to retrieve sensor values from the Sense HAT, respond to joystick input, and drive the LED matrix.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b369-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6b369-113">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="6b369-114">Sense hat</span><span class="sxs-lookup"><span data-stu-id="6b369-114">Sense HAT</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="run-the-quickstart"></a><span data-ttu-id="6b369-115">Ausführen des Schnellstarts</span><span class="sxs-lookup"><span data-stu-id="6b369-115">Run the quickstart</span></span>

<span data-ttu-id="6b369-116">Fügen Sie die Sense-hat an Ihren Raspberry Pi an.</span><span class="sxs-lookup"><span data-stu-id="6b369-116">Attach the Sense HAT to your Raspberry Pi.</span></span> <span data-ttu-id="6b369-117">Führen Sie an einer bash-Eingabeaufforderung auf dem Raspberry PI (lokal oder Remote) den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6b369-117">From a Bash prompt on the Raspberry Pi (local or remote), run the following command:</span></span>

```bash
. <(wget -q -O - https://aka.ms/dotnet-iot-sensehat-quickstart)
```

<span data-ttu-id="6b369-118">Der Befehl lädt ein Skript herunter und führt es aus.</span><span class="sxs-lookup"><span data-stu-id="6b369-118">The command downloads and runs a script.</span></span> <span data-ttu-id="6b369-119">Mit dem Skript wird Folgendes durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="6b369-119">The script:</span></span>

- <span data-ttu-id="6b369-120">Installiert das .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="6b369-120">Installs the .NET SDK.</span></span>
- <span data-ttu-id="6b369-121">Klont ein GitHub-Repository, das das Sense hat-Schnellstart Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="6b369-121">Clones a GitHub repository that includes the Sense HAT quickstart project.</span></span>
- <span data-ttu-id="6b369-122">Erstellt das Projekt.</span><span class="sxs-lookup"><span data-stu-id="6b369-122">Builds the project.</span></span>
- <span data-ttu-id="6b369-123">Führt das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="6b369-123">Runs the project.</span></span>

<span data-ttu-id="6b369-124">Beachten Sie die Konsolenausgabe, wenn Sensordaten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6b369-124">Observe the console output as sensor data is displayed.</span></span> <span data-ttu-id="6b369-125">Die LED-Matrix zeigt ein gelbes Pixel in einem blauen Feld an.</span><span class="sxs-lookup"><span data-stu-id="6b369-125">The LED matrix displays a yellow pixel on a field of blue.</span></span> <span data-ttu-id="6b369-126">Wenn Sie den Joystick in beliebiger Richtung halten, wird das gelbe Pixel in diese Richtung verschoben.</span><span class="sxs-lookup"><span data-stu-id="6b369-126">Holding the joystick in any direction moves the yellow pixel in that direction.</span></span> <span data-ttu-id="6b369-127">Wenn Sie auf die Schaltfläche "Zentrieren" klicken, wechselt der Hintergrund von blau zu rot.</span><span class="sxs-lookup"><span data-stu-id="6b369-127">Clicking the center joystick button causes the background to switch from blue to red.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="6b369-128">Herunterladen des Quellcodes</span><span class="sxs-lookup"><span data-stu-id="6b369-128">Get the source code</span></span>

<span data-ttu-id="6b369-129">Die Quelle für diesen Schnellstart ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="6b369-129">The source for this quickstart is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/quickstarts/SenseHat.Quickstart) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6b369-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6b369-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6b369-131">Erfahren Sie, wie Sie mit universell Eingabe/Ausgabe eine LED blinken.</span><span class="sxs-lookup"><span data-stu-id="6b369-131">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
