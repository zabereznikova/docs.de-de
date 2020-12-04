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
# <a name="blink-an-led"></a><span data-ttu-id="589c4-103">Blinken einer LED</span><span class="sxs-lookup"><span data-stu-id="589c4-103">Blink an LED</span></span>

<span data-ttu-id="589c4-104">Allgemeine e/a-Pins (GPIO) können einzeln gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="589c4-104">General-purpose I/O (GPIO) pins can be controlled individually.</span></span> <span data-ttu-id="589c4-105">Dies ist nützlich, um LEDs, Relays und andere Zustands behaftete Geräte zu steuern.</span><span class="sxs-lookup"><span data-stu-id="589c4-105">This is useful for controlling LEDs, relays, and other stateful devices.</span></span> <span data-ttu-id="589c4-106">In diesem Thema verwenden Sie .net und die GPIO-Pins Ihres Raspberry Pi zum Einschalten einer LED und zum wiederholten blinken.</span><span class="sxs-lookup"><span data-stu-id="589c4-106">In this topic, you will use .NET and your Raspberry Pi's GPIO pins to power an LED and blink it repeatedly.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="589c4-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="589c4-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="589c4-108">5-mm-LED</span><span class="sxs-lookup"><span data-stu-id="589c4-108">5 mm LED</span></span>
- <span data-ttu-id="589c4-109">330.</span><span class="sxs-lookup"><span data-stu-id="589c4-109">330 Ω resistor</span></span>
- <span data-ttu-id="589c4-110">Breadboard</span><span class="sxs-lookup"><span data-stu-id="589c4-110">Breadboard</span></span>
- <span data-ttu-id="589c4-111">Jumperdrähte</span><span class="sxs-lookup"><span data-stu-id="589c4-111">Jumper wires</span></span>
- <span data-ttu-id="589c4-112">Raspberry Pi-GPIO-Breakout-Board (optional/empfohlen)</span><span class="sxs-lookup"><span data-stu-id="589c4-112">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [ensure-ssh](../includes/ensure-ssh.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="589c4-113">Vorbereiten der Hardware</span><span class="sxs-lookup"><span data-stu-id="589c4-113">Prepare the hardware</span></span>

<span data-ttu-id="589c4-114">Verwenden Sie die Hardwarekomponenten, um die Verbindung zu erstellen, wie im folgenden Diagramm dargestellt:</span><span class="sxs-lookup"><span data-stu-id="589c4-114">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-led_bb-thumb.png" alt-text="Ein fritzingdiagramm, das eine Verbindung mit einer LED und einem Gegenstand anzeigt" lightbox="../media/rpi-led_bb.png":::

<span data-ttu-id="589c4-116">Die obige Abbildung zeigt die folgenden Verbindungen:</span><span class="sxs-lookup"><span data-stu-id="589c4-116">The image above depicts the following connections:</span></span>

- <span data-ttu-id="589c4-117">GPIO 18 bis LED-Anoden (länger, positiver Lead)</span><span class="sxs-lookup"><span data-stu-id="589c4-117">GPIO 18 to LED anode (longer, positive lead)</span></span>
- <span data-ttu-id="589c4-118">LED-Kathode (kürzer, negativer Lead) zu 330. Gegenstand (beide Enden)</span><span class="sxs-lookup"><span data-stu-id="589c4-118">LED cathode (shorter, negative lead) to 330 Ω resistor (either end)</span></span>
- <span data-ttu-id="589c4-119">330. Gegenstand (anderes Ende) bis zum Grund</span><span class="sxs-lookup"><span data-stu-id="589c4-119">330 Ω resistor (other end) to ground</span></span>

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="589c4-120">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="589c4-120">Create the app</span></span>

<span data-ttu-id="589c4-121">Führen Sie die folgenden Schritte in Ihrer bevorzugten Entwicklungsumgebung aus:</span><span class="sxs-lookup"><span data-stu-id="589c4-121">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="589c4-122">Erstellen Sie eine neue .net-Konsolen-APP, indem Sie entweder die [.net-CLI](../../core/tools/dotnet-new.md) oder [Visual Studio](../../core/tutorials/with-visual-studio.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="589c4-122">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="589c4-123">Nennen Sie es *blinktutorial*.</span><span class="sxs-lookup"><span data-stu-id="589c4-123">Name it *BlinkTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o BlinkTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="589c4-124">Ersetzen Sie den Inhalt von *Program.cs* durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="589c4-124">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/BlinkTutorial/Program.cs" :::

    <span data-ttu-id="589c4-125">Im obigen Code:</span><span class="sxs-lookup"><span data-stu-id="589c4-125">In the preceding code:</span></span>

    - <span data-ttu-id="589c4-126">Eine [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) erstellt eine Instanz von `GpioController` .</span><span class="sxs-lookup"><span data-stu-id="589c4-126">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `GpioController`.</span></span> <span data-ttu-id="589c4-127">Die `using` -Deklaration stellt sicher, dass das Objekt verworfen und Hardware Ressourcen ordnungsgemäß freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="589c4-127">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="589c4-128">GPIO Pin 18 ist für die Ausgabe geöffnet</span><span class="sxs-lookup"><span data-stu-id="589c4-128">GPIO pin 18 is opened for output</span></span>
    - <span data-ttu-id="589c4-129">Eine- `while` Schleife wird unbegrenzt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="589c4-129">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="589c4-130">Jede Iterationen:</span><span class="sxs-lookup"><span data-stu-id="589c4-130">Each iteration:</span></span>
        1. <span data-ttu-id="589c4-131">Schreibt einen Wert in GPIO Pin 18.</span><span class="sxs-lookup"><span data-stu-id="589c4-131">Writes a value to GPIO pin 18.</span></span> <span data-ttu-id="589c4-132">Wenn `ledOn` den Wert true hat, schreibt er `PinValue.High` (on).</span><span class="sxs-lookup"><span data-stu-id="589c4-132">If `ledOn` is true, it writes `PinValue.High` (on).</span></span> <span data-ttu-id="589c4-133">Andernfalls wird geschrieben `PinValue.Low` .</span><span class="sxs-lookup"><span data-stu-id="589c4-133">Otherwise, it writes `PinValue.Low`.</span></span>
        1. <span data-ttu-id="589c4-134">1000 ms wird nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="589c4-134">Sleeps 1000 ms.</span></span>
        1. <span data-ttu-id="589c4-135">Schaltet den Wert von um `ledOn` .</span><span class="sxs-lookup"><span data-stu-id="589c4-135">Toggles the value of `ledOn`.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="589c4-136">Führen Sie die APP auf dem Raspberry Pi aus, indem Sie zum Bereitstellungs Verzeichnis wechseln und die ausführbare Datei ausführen.</span><span class="sxs-lookup"><span data-stu-id="589c4-136">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./BlinkTutorial
    ```

    <span data-ttu-id="589c4-137">Die LED gibt eine Verknüpfung von und auf jeder Sekunde aus.</span><span class="sxs-lookup"><span data-stu-id="589c4-137">The LED blinks off and on every second.</span></span>

1. <span data-ttu-id="589c4-138">Beenden Sie das Programm, indem Sie <kbd>STRG + C</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="589c4-138">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="589c4-139">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="589c4-139">Congratulations!</span></span> <span data-ttu-id="589c4-140">Sie haben GPIO verwendet, um eine LED zu blinken.</span><span class="sxs-lookup"><span data-stu-id="589c4-140">You've used GPIO to blink an LED.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="589c4-141">Herunterladen des Quellcodes</span><span class="sxs-lookup"><span data-stu-id="589c4-141">Get the source code</span></span>

<span data-ttu-id="589c4-142">Die Quelle für dieses Tutorial ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="589c4-142">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/BlinkTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="589c4-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="589c4-143">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="589c4-144">Erfahren Sie, wie Sie Umgebungsbedingungen von einem Sensor aus lesen.</span><span class="sxs-lookup"><span data-stu-id="589c4-144">Learn how to read environmental conditions from a sensor</span></span>](../tutorials/temp-sensor.md)
