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
# <a name="display-text-on-an-lcd"></a><span data-ttu-id="be06b-103">Anzeigen von Text in einem LC-Display</span><span class="sxs-lookup"><span data-stu-id="be06b-103">Display text on an LCD</span></span>

<span data-ttu-id="be06b-104">LCD-Zeichen werden zum Anzeigen von Informationen nützlich, ohne dass ein externer Monitor erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="be06b-104">LCD character displays are useful for displaying information without the need for an external monitor.</span></span> <span data-ttu-id="be06b-105">Gängige LCD-Zeichen können direkt mit den GPIO-Pins verbunden werden. ein solcher Ansatz erfordert jedoch die Verwendung von bis zu 10 GPIO Pins.</span><span class="sxs-lookup"><span data-stu-id="be06b-105">Common LCD character displays can be connected directly to the GPIO pins, but such an approach requires the use of up to 10 GPIO pins.</span></span> <span data-ttu-id="be06b-106">Szenarios, die eine Verbindung mit einer Kombination von Geräten erfordern, sind häufig nicht praktikabel.</span><span class="sxs-lookup"><span data-stu-id="be06b-106">For scenarios that require connecting to a combination of devices, devoting so much of the GPIO header to a character display is often impractical.</span></span>

<span data-ttu-id="be06b-107">Viele Hersteller verkaufen 20 x 4 LCD-Zeichen anzeigen mit einem integrierten GPIO-Expander.</span><span class="sxs-lookup"><span data-stu-id="be06b-107">Many manufacturers sell 20x4 LCD character displays with an integrated GPIO expander.</span></span> <span data-ttu-id="be06b-108">Die Zeichen Anzeige stellt eine direkte Verbindung mit dem GPIO-Expander her, der dann über das serielle Protokoll der Inter-Integrated Leitung (I2C) eine Verbindung mit dem Raspberry Pi herstellt.</span><span class="sxs-lookup"><span data-stu-id="be06b-108">The character display connects directly to the GPIO expander, which then connects to the Raspberry Pi via the Inter-Integrated Circuit (I2C) serial protocol.</span></span>

<span data-ttu-id="be06b-109">In diesem Thema verwenden Sie .net zum Anzeigen von Text auf einer LCD-Zeichen Anzeige mithilfe eines I2C-GPIO-Expander.</span><span class="sxs-lookup"><span data-stu-id="be06b-109">In this topic, you will use .NET to display text on an LCD character display using an I2C GPIO expander.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be06b-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="be06b-110">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="be06b-111">[20 x 4-LCD-Zeichen Anzeige mit der I2C-Schnittstelle](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="be06b-111">[20x4 LCD Character Display with I2C interface](https://www.bing.com/images/search?q=20x4+lcd+display+with+i2c) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>
- <span data-ttu-id="be06b-112">Jumperdrähte</span><span class="sxs-lookup"><span data-stu-id="be06b-112">Jumper wires</span></span>
- <span data-ttu-id="be06b-113">Breadboard (optional/empfohlen)</span><span class="sxs-lookup"><span data-stu-id="be06b-113">Breadboard (optional/recommended)</span></span>
- <span data-ttu-id="be06b-114">Raspberry Pi-GPIO-Breakout-Board (optional/empfohlen)</span><span class="sxs-lookup"><span data-stu-id="be06b-114">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!NOTE]
> <span data-ttu-id="be06b-115">Viele Hersteller von LCD-Zeichen werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be06b-115">There are many manufacturers of LCD character displays.</span></span> <span data-ttu-id="be06b-116">Die meisten Entwürfe sind identisch, und der Hersteller sollte keinen Unterschied zu den Funktionen treffen.</span><span class="sxs-lookup"><span data-stu-id="be06b-116">Most designs are identical, and the manufacturer shouldn't make any difference to the functionality.</span></span> <span data-ttu-id="be06b-117">Als Referenz wurde dieses Lernprogramm mit dem [sungründer-LCD2004](https://www.sunfounder.com/lcd2004-module.html) entwickelt <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="be06b-117">For reference, this tutorial was developed with the [SunFounder LCD2004](https://www.sunfounder.com/lcd2004-module.html) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="be06b-118">Vorbereiten der Hardware</span><span class="sxs-lookup"><span data-stu-id="be06b-118">Prepare the hardware</span></span>

<span data-ttu-id="be06b-119">Verbinden Sie die vier Pins auf dem I2C-GPIO-Expander mithilfe von Jumper-Drähten wie folgt mit dem Raspberry PI:</span><span class="sxs-lookup"><span data-stu-id="be06b-119">Use jumper wires to connect the four pins on the I2C GPIO expander to the Raspberry Pi as follows:</span></span>

- <span data-ttu-id="be06b-120">GND zu Boden</span><span class="sxs-lookup"><span data-stu-id="be06b-120">GND to ground</span></span>
- <span data-ttu-id="be06b-121">VCC zu 5V</span><span class="sxs-lookup"><span data-stu-id="be06b-121">VCC to 5V</span></span>
- <span data-ttu-id="be06b-122">SDA zu SDA (GPIO 2)</span><span class="sxs-lookup"><span data-stu-id="be06b-122">SDA to SDA (GPIO 2)</span></span>
- <span data-ttu-id="be06b-123">SCL zu SCL (GPIO 3)</span><span class="sxs-lookup"><span data-stu-id="be06b-123">SCL to SCL (GPIO 3)</span></span>

<span data-ttu-id="be06b-124">Weitere Informationen finden Sie in den folgenden Abbildungen:</span><span class="sxs-lookup"><span data-stu-id="be06b-124">Refer to the following figures as needed:</span></span>

| <span data-ttu-id="be06b-125">I2C-Schnittstelle (Rückseite der Anzeige)</span><span class="sxs-lookup"><span data-stu-id="be06b-125">I2C interface (back of display)</span></span> | <span data-ttu-id="be06b-126">Raspberry Pi-GPIO</span><span class="sxs-lookup"><span data-stu-id="be06b-126">Raspberry Pi GPIO</span></span> |
|---------------------------------|-------------------|
| :::image type="content" source="../media/character-display-i2c-thumb.png" alt-text="Ein Bild der Rückseite der Zeichen Anzeige, die den I2C-GPIO-Expander anzeigt." lightbox="../media/character-display-i2c.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Ein Diagramm, das das Pinout des Raspberry Pi-GPIO-Headers anzeigt. Image-Höflichkeit Raspberry Pi Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br /><span data-ttu-id="be06b-129">[Image-Höflichkeit Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="be06b-129">[Image courtesy Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="be06b-130">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="be06b-130">Create the app</span></span>

<span data-ttu-id="be06b-131">Führen Sie die folgenden Schritte in Ihrer bevorzugten Entwicklungsumgebung aus:</span><span class="sxs-lookup"><span data-stu-id="be06b-131">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="be06b-132">Erstellen Sie eine neue .net-Konsolen-APP, indem Sie entweder die [.net-CLI](../../core/tools/dotnet-new.md) oder [Visual Studio](../../core/tutorials/with-visual-studio.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="be06b-132">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="be06b-133">Nennen Sie es *lcdtutorial*.</span><span class="sxs-lookup"><span data-stu-id="be06b-133">Name it *LcdTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o LcdTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="be06b-134">Ersetzen Sie den Inhalt von *Program.cs* durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="be06b-134">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/LcdTutorial/Program.cs" :::

    <span data-ttu-id="be06b-135">Im obigen Code:</span><span class="sxs-lookup"><span data-stu-id="be06b-135">In the preceding code:</span></span>

    - <span data-ttu-id="be06b-136">Eine [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) erstellt eine Instanz von, `I2cDevice` indem aufgerufen `I2cDevice.Create` und ein neues `I2cConnectionSettings` mit `busId` den `deviceAddress` Parametern und übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="be06b-136">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `I2cDevice` by calling `I2cDevice.Create` and passing in a new `I2cConnectionSettings` with the `busId` and `deviceAddress` parameters.</span></span> <span data-ttu-id="be06b-137">Dies `I2cDevice` stellt den I2C-Bus dar.</span><span class="sxs-lookup"><span data-stu-id="be06b-137">This `I2cDevice` represents the I2C bus.</span></span> <span data-ttu-id="be06b-138">Die `using` -Deklaration stellt sicher, dass das Objekt verworfen und Hardware Ressourcen ordnungsgemäß freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be06b-138">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>

        > [!WARNING]
        > <span data-ttu-id="be06b-139">Die Geräteadresse für den GPIO-Expander hängt von dem vom Hersteller verwendeten Chip ab.</span><span class="sxs-lookup"><span data-stu-id="be06b-139">The device address for the GPIO expander depends on the chip used by the manufacturer.</span></span> <span data-ttu-id="be06b-140">Bei GPIO-Expander, die mit einem PCF8574 ausgestattet sind, wird die-Adresse verwendet, bei der Verwendung von `0x27` PCF8574A-Chips `0x3F`</span><span class="sxs-lookup"><span data-stu-id="be06b-140">GPIO expanders equipped with a PCF8574 use the address `0x27`, while those using PCF8574A chips use `0x3F`.</span></span> <span data-ttu-id="be06b-141">Weitere Informationen finden Sie in der Dokumentation des LCD.</span><span class="sxs-lookup"><span data-stu-id="be06b-141">Consult your LCD's documentation.</span></span>

    - <span data-ttu-id="be06b-142">Eine andere `using` Deklaration erstellt eine Instanz von `Pcf8574` und übergibt die an `I2cDevice` den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="be06b-142">Another `using` declaration creates an instance of `Pcf8574` and passes the `I2cDevice` into the constructor.</span></span> <span data-ttu-id="be06b-143">Diese Instanz stellt den GPIO-Expander dar.</span><span class="sxs-lookup"><span data-stu-id="be06b-143">This instance represents the GPIO expander.</span></span>
    - <span data-ttu-id="be06b-144">Eine andere `using` Deklaration erstellt eine Instanz von `Lcd2004` zur Darstellung der Anzeige.</span><span class="sxs-lookup"><span data-stu-id="be06b-144">Another `using` declaration creates an instance of `Lcd2004` to represent the display.</span></span> <span data-ttu-id="be06b-145">Es werden mehrere Parameter an den Konstruktor übergeben, die die Einstellungen beschreiben, die für die Kommunikation mit dem GPIO-Expander verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be06b-145">Several parameters are passed to the constructor describing the settings to use to communicate with the GPIO expander.</span></span> <span data-ttu-id="be06b-146">Der GPIO-Expander wird als- `controller` Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="be06b-146">The GPIO expander is passed as the `controller` parameter.</span></span>
    - <span data-ttu-id="be06b-147">Eine- `while` Schleife wird unbegrenzt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="be06b-147">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="be06b-148">Jede Iterationen:</span><span class="sxs-lookup"><span data-stu-id="be06b-148">Each iteration:</span></span>
        1. <span data-ttu-id="be06b-149">Löscht die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="be06b-149">Clears the display.</span></span>
        1. <span data-ttu-id="be06b-150">Legt die Cursorposition auf die erste Position in der aktuellen Zeile fest.</span><span class="sxs-lookup"><span data-stu-id="be06b-150">Sets the cursor position to the first position on the current line.</span></span>
        1. <span data-ttu-id="be06b-151">Schreibt die aktuelle Uhrzeit an der aktuellen Cursorposition in die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="be06b-151">Writes the current time to the display at the current cursor position.</span></span>
        1. <span data-ttu-id="be06b-152">Iteriert den aktuellen Zeilen Zählers.</span><span class="sxs-lookup"><span data-stu-id="be06b-152">Iterates the current line counter.</span></span>
        1. <span data-ttu-id="be06b-153">1000 ms wird nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be06b-153">Sleeps 1000 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="be06b-154">Führen Sie die APP auf dem Raspberry Pi aus, indem Sie zum Bereitstellungs Verzeichnis wechseln und die ausführbare Datei ausführen.</span><span class="sxs-lookup"><span data-stu-id="be06b-154">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./LcdTutorial
    ```

    <span data-ttu-id="be06b-155">Sehen Sie sich die Bildschirm Anzeige an, wenn die aktuelle Uhrzeit in jeder Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="be06b-155">Observe the LCD character display as the current time displays on each line.</span></span>

    > [!TIP]
    > <span data-ttu-id="be06b-156">Wenn die Anzeige beleuchtet ist, aber kein Text angezeigt wird, versuchen Sie, die Kontrast-Wähl Option auf der Rückseite der Anzeige anzupassen.</span><span class="sxs-lookup"><span data-stu-id="be06b-156">If the display is lit but you don't see any text, try adjusting the contrast dial on the back of the display.</span></span>

1. <span data-ttu-id="be06b-157">Beenden Sie das Programm, indem Sie <kbd>STRG + C</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="be06b-157">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="be06b-158">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="be06b-158">Congratulations!</span></span> <span data-ttu-id="be06b-159">Sie haben Text auf einem LCD mit einem I2C und einem GPIO-Expander angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be06b-159">You've displayed text on an LCD using a I2C and a GPIO expander!</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="be06b-160">Herunterladen des Quellcodes</span><span class="sxs-lookup"><span data-stu-id="be06b-160">Get the source code</span></span>

<span data-ttu-id="be06b-161">Die Quelle für dieses Tutorial ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="be06b-161">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/LcdTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="be06b-162">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="be06b-162">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="be06b-163">Erfahren Sie, wie Sie mit universell Eingabe/Ausgabe eine LED blinken.</span><span class="sxs-lookup"><span data-stu-id="be06b-163">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
