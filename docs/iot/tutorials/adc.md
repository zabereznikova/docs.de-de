---
title: Lesen von Werten aus einem Analog-zu-Digital-Konverter
description: Erfahren Sie, wie Sie Variable Spannungswerte mithilfe eines Analog-zu-Digital Konverters lesen.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: tutorial
ms.prod: dotnet
ms.openlocfilehash: eda6d8980d256c8063f2bfe1e051b0cb90b587ad
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96592114"
---
<!--markdownlint-disable DOCSMD011 -->
# <a name="read-values-from-an-analog-to-digital-converter"></a><span data-ttu-id="d3f96-103">Lesen von Werten aus einem Analog-zu-Digital-Konverter</span><span class="sxs-lookup"><span data-stu-id="d3f96-103">Read values from an analog-to-digital converter</span></span>

<span data-ttu-id="d3f96-104">Ein "analog-zu-Digital Converter" (ADC) ist ein Gerät, das einen analogen Eingangs Spannungswert lesen und in einen digitalen Wert konvertieren kann.</span><span class="sxs-lookup"><span data-stu-id="d3f96-104">An analog-to-digital converter (ADC) is a device that can read an analog input voltage value and convert it into a digital value.</span></span> <span data-ttu-id="d3f96-105">ADCs dient zum Lesen von Werten von Thermistoren, artefaktometern und anderen Geräten, die den Widerstand auf der Grundlage bestimmter Bedingungen ändern.</span><span class="sxs-lookup"><span data-stu-id="d3f96-105">ADCs are used for reading values from thermistors, potentiometers, and other devices that change resistance based on certain conditions.</span></span>

<span data-ttu-id="d3f96-106">In diesem Thema verwenden Sie .net, um Werte aus einem ADC zu lesen, während Sie die Eingabe Spannung mit einem potenzimesser modulieren.</span><span class="sxs-lookup"><span data-stu-id="d3f96-106">In this topic, you will use .NET to read values from an ADC as you modulate the input voltage with a potentiometer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3f96-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d3f96-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="d3f96-108">[MCP3008](https://www.microchip.com/wwwproducts/MCP3008) <span class="docon docon-navigate-external x-hidden-focus"></span> Analog zu Digital Converter</span><span class="sxs-lookup"><span data-stu-id="d3f96-108">[MCP3008](https://www.microchip.com/wwwproducts/MCP3008) <span class="docon docon-navigate-external x-hidden-focus"></span> analog-to-digital converter</span></span>
- <span data-ttu-id="d3f96-109">Drei-Pin-potenzimesser</span><span class="sxs-lookup"><span data-stu-id="d3f96-109">Three-pin potentiometer</span></span>
- <span data-ttu-id="d3f96-110">Breadboard</span><span class="sxs-lookup"><span data-stu-id="d3f96-110">Breadboard</span></span>
- <span data-ttu-id="d3f96-111">Jumperdrähte</span><span class="sxs-lookup"><span data-stu-id="d3f96-111">Jumper wires</span></span>
- <span data-ttu-id="d3f96-112">Raspberry Pi-GPIO-Breakout-Board (optional/empfohlen)</span><span class="sxs-lookup"><span data-stu-id="d3f96-112">Raspberry Pi GPIO breakout board (optional/recommended)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

[!INCLUDE [prepare-pi-spi](../includes/prepare-pi-spi.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="d3f96-113">Vorbereiten der Hardware</span><span class="sxs-lookup"><span data-stu-id="d3f96-113">Prepare the hardware</span></span>

<span data-ttu-id="d3f96-114">Verwenden Sie die Hardwarekomponenten, um die Verbindung zu erstellen, wie im folgenden Diagramm dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d3f96-114">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-trimpot_spi-thumb.png" alt-text="Ein fritzterdiagramm, das eine Verbindung mit einem MCP3008 ADC und einem potenzimesser anzeigt" lightbox="../media/rpi-trimpot_spi.png":::

<span data-ttu-id="d3f96-116">Der MCP3008 verwendet die Serial Peripherie Interface (SPI) für die Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="d3f96-116">The MCP3008 uses Serial Peripheral Interface (SPI) to communicate.</span></span> <span data-ttu-id="d3f96-117">Im folgenden finden Sie die Verbindungen zwischen MCP3008 und Raspberry Pi und dem-potenzimesser:</span><span class="sxs-lookup"><span data-stu-id="d3f96-117">The following are the connections from the MCP3008 to the Raspberry Pi and potentiometer:</span></span>

- <span data-ttu-id="d3f96-118">V<sub>TT bis 3.3</sub> v (rot dargestellt)</span><span class="sxs-lookup"><span data-stu-id="d3f96-118">V<sub>DD</sub> to 3.3V (shown in red)</span></span>
- <span data-ttu-id="d3f96-119">V<sub>ref</sub> zu 3.3 v (rot)</span><span class="sxs-lookup"><span data-stu-id="d3f96-119">V<sub>REF</sub> to 3.3V (red)</span></span>
- <span data-ttu-id="d3f96-120">Zu Boden (schwarz)</span><span class="sxs-lookup"><span data-stu-id="d3f96-120">AGND to ground (black)</span></span>
- <span data-ttu-id="d3f96-121">CLK zu SCLK (Orange)</span><span class="sxs-lookup"><span data-stu-id="d3f96-121">CLK to SCLK (orange)</span></span>
- <span data-ttu-id="d3f96-122">D<sub>out</sub> an Miso (Orange)</span><span class="sxs-lookup"><span data-stu-id="d3f96-122">D<sub>OUT</sub> to MISO (orange)</span></span>
- <span data-ttu-id="d3f96-123">D<sub>in</sub> zu "Musi" (Orange)</span><span class="sxs-lookup"><span data-stu-id="d3f96-123">D<sub>IN</sub> to MOSI (orange)</span></span>
- <span data-ttu-id="d3f96-124">CS/SHDN in ce0 (grün)</span><span class="sxs-lookup"><span data-stu-id="d3f96-124">CS/SHDN to CE0 (green)</span></span>
- <span data-ttu-id="d3f96-125">DGND bis Boden (schwarz)</span><span class="sxs-lookup"><span data-stu-id="d3f96-125">DGND to ground (black)</span></span>
- <span data-ttu-id="d3f96-126">CH0-to-Variable (mittlere) Pin auf dem potenzierer (gelb)</span><span class="sxs-lookup"><span data-stu-id="d3f96-126">CH0 to variable (middle) pin on potentiometer (yellow)</span></span>

<span data-ttu-id="d3f96-127">Geben Sie 3.3 v und Boden für die äußeren Pins des potenzimessers an.</span><span class="sxs-lookup"><span data-stu-id="d3f96-127">Supply 3.3V and ground to the outer pins on the potentiometer.</span></span> <span data-ttu-id="d3f96-128">Die Reihenfolge ist unwichtig.</span><span class="sxs-lookup"><span data-stu-id="d3f96-128">Order is unimportant.</span></span>

<span data-ttu-id="d3f96-129">Weitere Informationen finden Sie in den folgenden Pinout-Diagrammen:</span><span class="sxs-lookup"><span data-stu-id="d3f96-129">Refer to the following pinout diagrams as needed:</span></span>

| <span data-ttu-id="d3f96-130">MCP3008</span><span class="sxs-lookup"><span data-stu-id="d3f96-130">MCP3008</span></span>  | <span data-ttu-id="d3f96-131">Raspberry Pi-GPIO</span><span class="sxs-lookup"><span data-stu-id="d3f96-131">Raspberry Pi GPIO</span></span> |
|----------|-------------------|
| :::image type="content" source="../media/mcp3008-diagram-thumb.png" alt-text="Ein Diagramm mit dem Pinout des MCP3008" lightbox="../media/mcp3008-diagram.png"::: | :::image type="content" source="../media/gpio-pinout-diagram-thumb.png" alt-text="Ein Diagramm, das das Pinout des Raspberry Pi-GPIO-Headers anzeigt. Image-Höflichkeit Raspberry Pi Foundation." lightbox="../media/gpio-pinout-diagram.png":::<br /><span data-ttu-id="d3f96-134">[Image-Höflichkeit Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span><span class="sxs-lookup"><span data-stu-id="d3f96-134">[Image courtesy Raspberry Pi Foundation](https://www.raspberrypi.org/documentation/usage/gpio/).</span></span>
 |

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="d3f96-135">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="d3f96-135">Create the app</span></span>

<span data-ttu-id="d3f96-136">Führen Sie die folgenden Schritte in Ihrer bevorzugten Entwicklungsumgebung aus:</span><span class="sxs-lookup"><span data-stu-id="d3f96-136">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="d3f96-137">Erstellen Sie eine neue .net-Konsolen-APP, indem Sie entweder die [.net-CLI](../../core/tools/dotnet-new.md) oder [Visual Studio](../../core/tutorials/with-visual-studio.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3f96-137">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="d3f96-138">Nennen Sie Sie " *adctutorial*".</span><span class="sxs-lookup"><span data-stu-id="d3f96-138">Name it *AdcTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o AdcTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="d3f96-139">Ersetzen Sie den Inhalt von *Program.cs* durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="d3f96-139">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/AdcTutorial/Program.cs" :::

    <span data-ttu-id="d3f96-140">Im obigen Code:</span><span class="sxs-lookup"><span data-stu-id="d3f96-140">In the preceding code:</span></span>

    - <span data-ttu-id="d3f96-141">`hardwareSpiSettings` wird auf eine neue Instanz von festgelegt `SpiConnectionSettings` .</span><span class="sxs-lookup"><span data-stu-id="d3f96-141">`hardwareSpiSettings` is set to a new instance of `SpiConnectionSettings`.</span></span> <span data-ttu-id="d3f96-142">Der-Konstruktor legt den `busId` -Parameter auf 0 und den- `chipSelectLine` Parameter auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="d3f96-142">The constructor sets the `busId` parameter to 0 and the `chipSelectLine` parameter to 0.</span></span>
    - <span data-ttu-id="d3f96-143">Eine [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) erstellt eine Instanz von, `SpiDevice` indem aufgerufen `SpiDevice.Create` und übergeben wird `hardwareSpiSettings` .</span><span class="sxs-lookup"><span data-stu-id="d3f96-143">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `SpiDevice` by calling `SpiDevice.Create` and passing in `hardwareSpiSettings`.</span></span> <span data-ttu-id="d3f96-144">Dies `SpiDevice` stellt den SPI-Bus dar.</span><span class="sxs-lookup"><span data-stu-id="d3f96-144">This `SpiDevice` represents the SPI bus.</span></span> <span data-ttu-id="d3f96-145">Die `using` -Deklaration stellt sicher, dass das Objekt verworfen und Hardware Ressourcen ordnungsgemäß freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d3f96-145">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="d3f96-146">Eine andere `using` Deklaration erstellt eine Instanz von `Mcp3008` und übergibt die an `SpiDevice` den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="d3f96-146">Another `using` declaration creates an instance of `Mcp3008` and passes the `SpiDevice` into the constructor.</span></span>
    - <span data-ttu-id="d3f96-147">Eine- `while` Schleife wird unbegrenzt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d3f96-147">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="d3f96-148">Jede Iterationen:</span><span class="sxs-lookup"><span data-stu-id="d3f96-148">Each iteration:</span></span>
        1. <span data-ttu-id="d3f96-149">Liest den Wert von CH0 auf dem ADC durch Aufrufen von `mcp.Read(0)` .</span><span class="sxs-lookup"><span data-stu-id="d3f96-149">Reads the value of CH0 on the ADC by calling `mcp.Read(0)`.</span></span>
        1. <span data-ttu-id="d3f96-150">Dividiert den Wert durch 10,24.</span><span class="sxs-lookup"><span data-stu-id="d3f96-150">Divides the value by 10.24.</span></span> <span data-ttu-id="d3f96-151">Der MCP3008 ist ein 10-Bit-ADC, d. h., es werden 1024 mögliche Werte im Bereich von 0-1023 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d3f96-151">The MCP3008 is a 10-bit ADC, which means it returns 1024 possible values ranging 0-1023.</span></span> <span data-ttu-id="d3f96-152">Durch die Aufteilung des Werts durch 10,24 wird der Wert als Prozentsatz dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d3f96-152">Dividing the value by 10.24 represents the value as a percentage.</span></span>
        1. <span data-ttu-id="d3f96-153">Rundet den Wert auf die nächste ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="d3f96-153">Rounds the value to the nearest integer.</span></span>
        1. <span data-ttu-id="d3f96-154">Schreibt den Wert in die Konsole, die als Prozentsatz formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="d3f96-154">Writes the value to the console formatted as a percentage.</span></span>
        1. <span data-ttu-id="d3f96-155">500 ms wird nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3f96-155">Sleeps 500 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="d3f96-156">Führen Sie die APP auf dem Raspberry Pi aus, indem Sie zum Bereitstellungs Verzeichnis wechseln und die ausführbare Datei ausführen.</span><span class="sxs-lookup"><span data-stu-id="d3f96-156">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./AdcTutorial
    ```

    <span data-ttu-id="d3f96-157">Sehen Sie sich die Ausgabe an, während Sie die Leistungs Messer-Wahl drehen.</span><span class="sxs-lookup"><span data-stu-id="d3f96-157">Observe the output as you rotate the potentiometer dial.</span></span> <span data-ttu-id="d3f96-158">Dies ist darauf zurückzuführen, dass der Potentiometer die für CH0 auf dem ADC angegebene Spannung variiert.</span><span class="sxs-lookup"><span data-stu-id="d3f96-158">This is due to the potentiometer varying the voltage supplied to CH0 on the ADC.</span></span> <span data-ttu-id="d3f96-159">Der ADC vergleicht die Eingangsspannung auf CH0 mit der für V<sub>ref</sub> angegebenen Referenzspannung, um einen Wert zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d3f96-159">The ADC compares the input voltage on CH0 to the reference voltage supplied to V<sub>REF</sub> to generate a value.</span></span>

1. <span data-ttu-id="d3f96-160">Beenden Sie das Programm, indem Sie <kbd>STRG + C</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="d3f96-160">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="d3f96-161">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="d3f96-161">Congratulations!</span></span> <span data-ttu-id="d3f96-162">Sie haben SPI zum Lesen von Werten aus einem analog-zu-Digital-Konverter verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3f96-162">You've used SPI to read values from an analog-to-digital converter.</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="d3f96-163">Herunterladen des Quellcodes</span><span class="sxs-lookup"><span data-stu-id="d3f96-163">Get the source code</span></span>

<span data-ttu-id="d3f96-164">Die Quelle für dieses Tutorial ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial).</span><span class="sxs-lookup"><span data-stu-id="d3f96-164">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/AdcTutorial).</span></span> <span class="docon docon-navigate-external x-hidden-focus"></span>

## <a name="next-steps"></a><span data-ttu-id="d3f96-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d3f96-165">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3f96-166">Erfahren Sie, wie Sie mit universell Eingabe/Ausgabe eine LED blinken.</span><span class="sxs-lookup"><span data-stu-id="d3f96-166">Learn to use General Purpose Input/Output to blink an LED</span></span>](../tutorials/blink-led.md)
