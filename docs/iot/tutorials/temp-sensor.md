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
# <a name="read-environmental-conditions-from-a-sensor"></a><span data-ttu-id="e1d2e-103">Lesen von Umgebungsbedingungen aus einem Sensor</span><span class="sxs-lookup"><span data-stu-id="e1d2e-103">Read environmental conditions from a sensor</span></span>

<span data-ttu-id="e1d2e-104">Eines der gängigsten Szenarien für IOT-Geräte ist das Erkennen von Umgebungsbedingungen.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-104">One of the most common scenarios for IoT devices is detection of environmental conditions.</span></span> <span data-ttu-id="e1d2e-105">Es stehen eine Vielzahl von Sensoren zur Verfügung, um Temperatur, Luftfeuchtigkeit, den barometrischen Druck und mehr zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-105">A variety of sensors are available to monitor temperature, humidity, barometric pressure, and more.</span></span>

<span data-ttu-id="e1d2e-106">In diesem Thema verwenden Sie .net zum Lesen von Umgebungsbedingungen von einem Sensor.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-106">In this topic, you will use .NET to read environmental conditions from a sensor.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e1d2e-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e1d2e-107">Prerequisites</span></span>

- [!INCLUDE [prereq-rpi](../includes/prereq-rpi.md)]
- <span data-ttu-id="e1d2e-108">[BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) <span class="docon docon-navigate-external x-hidden-focus"></span> Luftfeuchtigkeit/der Druck/Temperatursensor-Breakout</span><span class="sxs-lookup"><span data-stu-id="e1d2e-108">[BME280](https://learn.adafruit.com/adafruit-bme280-humidity-barometric-pressure-temperature-sensor-breakout) <span class="docon docon-navigate-external x-hidden-focus"></span> humidity/barometric pressure/temperature sensor breakout</span></span>
- <span data-ttu-id="e1d2e-109">Jumperdrähte</span><span class="sxs-lookup"><span data-stu-id="e1d2e-109">Jumper wires</span></span>
- <span data-ttu-id="e1d2e-110">Breadboard (optional)</span><span class="sxs-lookup"><span data-stu-id="e1d2e-110">Breadboard (optional)</span></span>
- <span data-ttu-id="e1d2e-111">Raspberry Pi-GPIO-Breakout-Board (optional)</span><span class="sxs-lookup"><span data-stu-id="e1d2e-111">Raspberry Pi GPIO breakout board (optional)</span></span>
- [!INCLUDE [tutorial-prereq-dotnet](../includes/tutorial-prereq-dotnet.md)]

> [!IMPORTANT]
> <span data-ttu-id="e1d2e-112">Es gibt viele Hersteller von BME280 Breakouts.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-112">There are many manufacturers of BME280 breakouts.</span></span> <span data-ttu-id="e1d2e-113">Die meisten Entwürfe sind ähnlich, und der Hersteller sollte keinen Unterschied zu den Funktionen treffen.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-113">Most designs are similar, and the manufacturer shouldn't make any difference to the functionality.</span></span> <span data-ttu-id="e1d2e-114">In diesem Tutorial wird versucht, Variationen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-114">This tutorial attempts to account for variations.</span></span> <span data-ttu-id="e1d2e-115">Stellen Sie sicher, dass BME280 Breakout eine Schnittstelle für die Inter-Integrated Leitung (I2C) enthält.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-115">Ensure your BME280 breakout includes an Inter-Integrated Circuit (I2C) interface.</span></span>

[!INCLUDE [prepare-pi-i2c](../includes/prepare-pi-i2c.md)]

## <a name="prepare-the-hardware"></a><span data-ttu-id="e1d2e-116">Vorbereiten der Hardware</span><span class="sxs-lookup"><span data-stu-id="e1d2e-116">Prepare the hardware</span></span>

<span data-ttu-id="e1d2e-117">Verwenden Sie die Hardwarekomponenten, um die Verbindung zu erstellen, wie im folgenden Diagramm dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e1d2e-117">Use the hardware components to build the circuit as depicted in the following diagram:</span></span>

:::image type="content" source="../media/rpi-bmp280_i2c-thumb.png" alt-text="Ein Listen Diagramm, das die Verbindung zwischen Raspberry Pi und BME280 Breakout Board anzeigt." lightbox="../media/rpi-bmp280_i2c.png":::

<span data-ttu-id="e1d2e-119">Im folgenden sind die Verbindungen vom Raspberry Pi zum BME280-Breakout aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e1d2e-119">The following are the connections from the Raspberry Pi to the BME280 breakout:</span></span>

- <span data-ttu-id="e1d2e-120">3.3 v bis Vin *oder* 3v3 (rot dargestellt)</span><span class="sxs-lookup"><span data-stu-id="e1d2e-120">3.3V to VIN *OR* 3V3 (shown in red)</span></span>
- <span data-ttu-id="e1d2e-121">Zwischen Grund und GND (schwarz)</span><span class="sxs-lookup"><span data-stu-id="e1d2e-121">Ground to GND (black)</span></span>
- <span data-ttu-id="e1d2e-122">SDA (GPIO 2) mit SDI *oder* SDA (blau)</span><span class="sxs-lookup"><span data-stu-id="e1d2e-122">SDA (GPIO 2) to SDI *OR* SDA (blue)</span></span>
- <span data-ttu-id="e1d2e-123">SCL (GPIO 3) zu SCK *oder* SCL (Orange)</span><span class="sxs-lookup"><span data-stu-id="e1d2e-123">SCL (GPIO 3) to SCK *OR* SCL (orange)</span></span>

[!INCLUDE [tutorial-rpi-gpio](../includes/tutorial-rpi-gpio.md)]

[!INCLUDE [gpio-breakout](../includes/gpio-breakout.md)]

## <a name="create-the-app"></a><span data-ttu-id="e1d2e-124">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="e1d2e-124">Create the app</span></span>

<span data-ttu-id="e1d2e-125">Führen Sie die folgenden Schritte in Ihrer bevorzugten Entwicklungsumgebung aus:</span><span class="sxs-lookup"><span data-stu-id="e1d2e-125">Complete the following steps in your preferred development environment:</span></span>

1. <span data-ttu-id="e1d2e-126">Erstellen Sie eine neue .net-Konsolen-APP, indem Sie entweder die [.net-CLI](../../core/tools/dotnet-new.md) oder [Visual Studio](../../core/tutorials/with-visual-studio.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-126">Create a new .NET Console App using either the [.NET CLI](../../core/tools/dotnet-new.md) or [Visual Studio](../../core/tutorials/with-visual-studio.md).</span></span> <span data-ttu-id="e1d2e-127">Nennen Sie es *sensortutorial*.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-127">Name it *SensorTutorial*.</span></span>

    ```dotnetcli
    dotnet new console -o SensorTutorial
    ```

1. [!INCLUDE [tutorial-add-packages](../includes/tutorial-add-packages.md)]
1. <span data-ttu-id="e1d2e-128">Ersetzen Sie den Inhalt von *Program.cs* durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e1d2e-128">Replace the contents of *Program.cs* with the following code:</span></span>

    :::code language="csharp" source="~/iot-samples/tutorials/SensorTutorial/Program.cs" :::

    <span data-ttu-id="e1d2e-129">Im obigen Code:</span><span class="sxs-lookup"><span data-stu-id="e1d2e-129">In the preceding code:</span></span>

    - <span data-ttu-id="e1d2e-130">`i2cSettings` wird auf eine neue Instanz von festgelegt `I2cConnectionSettings` .</span><span class="sxs-lookup"><span data-stu-id="e1d2e-130">`i2cSettings` is set to a new instance of `I2cConnectionSettings`.</span></span> <span data-ttu-id="e1d2e-131">Der-Konstruktor legt den `busId` -Parameter auf 1 und den- `deviceAddress` Parameter auf fest `Bme280.DefaultI2cAddress` .</span><span class="sxs-lookup"><span data-stu-id="e1d2e-131">The constructor sets the `busId` parameter to 1 and the `deviceAddress` parameter to `Bme280.DefaultI2cAddress`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="e1d2e-132">Einige BME280-Breakout-Hersteller verwenden den sekundären Adress Wert.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-132">Some BME280 breakout manufacturers use the secondary address value.</span></span> <span data-ttu-id="e1d2e-133">Verwenden Sie für diese Geräte `Bme280.SecondaryI2cAddress` .</span><span class="sxs-lookup"><span data-stu-id="e1d2e-133">For those devices, use `Bme280.SecondaryI2cAddress`.</span></span>

    - <span data-ttu-id="e1d2e-134">Eine [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) erstellt eine Instanz von, `I2cDevice` indem aufgerufen `I2cDevice.Create` und übergeben wird `i2cSettings` .</span><span class="sxs-lookup"><span data-stu-id="e1d2e-134">A [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations) creates an instance of `I2cDevice` by calling `I2cDevice.Create` and passing in `i2cSettings`.</span></span> <span data-ttu-id="e1d2e-135">Dies `I2cDevice` stellt den I2C-Bus dar.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-135">This `I2cDevice` represents the I2C bus.</span></span> <span data-ttu-id="e1d2e-136">Die `using` -Deklaration stellt sicher, dass das Objekt verworfen und Hardware Ressourcen ordnungsgemäß freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-136">The `using` declaration ensures the object is disposed and hardware resources are released properly.</span></span>
    - <span data-ttu-id="e1d2e-137">Eine andere `using` Deklaration erstellt eine Instanz von `Bme280` , die den Sensor darstellt.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-137">Another `using` declaration creates an instance of `Bme280` to represent the sensor.</span></span> <span data-ttu-id="e1d2e-138">Das-Element `I2cDevice` wird im-Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-138">The `I2cDevice` is passed in the constructor.</span></span>
    - <span data-ttu-id="e1d2e-139">Die Zeit, die der Chip zum Übernehmen von Messungen mit den aktuellen (Standard-) Einstellungen des Chips benötigt, wird durch Aufrufen von abgerufen `GetMeasurementDuration` .</span><span class="sxs-lookup"><span data-stu-id="e1d2e-139">The time required for the chip to take measurements with the chip's current (default) settings is retrieved by calling `GetMeasurementDuration`.</span></span>
    - <span data-ttu-id="e1d2e-140">Eine- `while` Schleife wird unbegrenzt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-140">A `while` loop runs indefinitely.</span></span> <span data-ttu-id="e1d2e-141">Jede Iterationen:</span><span class="sxs-lookup"><span data-stu-id="e1d2e-141">Each iteration:</span></span>
        1. <span data-ttu-id="e1d2e-142">Löscht die Konsole.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-142">Clears the console.</span></span>
        1. <span data-ttu-id="e1d2e-143">Legt den Energie Modus auf fest `Bmx280PowerMode.Forced` .</span><span class="sxs-lookup"><span data-stu-id="e1d2e-143">Sets the power mode to `Bmx280PowerMode.Forced`.</span></span> <span data-ttu-id="e1d2e-144">Dies zwingt den Chip, eine Messung durchzuführen, die Ergebnisse zu speichern und dann in den Standbymodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-144">This forces the chip to perform one measurement, store the results, and then sleep.</span></span>
        1. <span data-ttu-id="e1d2e-145">Liest die Werte für Temperatur, Druck, Luftfeuchtigkeit und Höhe.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-145">Reads the values for temperature, pressure, humidity, and altitude.</span></span>

            > [!NOTE]
            > <span data-ttu-id="e1d2e-146">Die Höhe wird von der Geräte Bindung berechnet.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-146">Altitude is calculated by the device binding.</span></span> <span data-ttu-id="e1d2e-147">Diese Überladung von `TryReadAltitude` verwendet den Mittel sebene Druck, um eine Schätzung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-147">This overload of `TryReadAltitude` uses mean sea level pressure to generate an estimate.</span></span>

        1. <span data-ttu-id="e1d2e-148">Schreibt die aktuellen Umgebungsbedingungen in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-148">Writes the current environmental conditions to the console.</span></span>
        1. <span data-ttu-id="e1d2e-149">1000 ms wird nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-149">Sleeps 1000 ms.</span></span>

1. [!INCLUDE [tutorial-build](../includes/tutorial-build.md)]
1. [!INCLUDE [tutorial-deploy](../includes/tutorial-deploy.md)]
1. <span data-ttu-id="e1d2e-150">Führen Sie die APP auf dem Raspberry Pi aus, indem Sie zum Bereitstellungs Verzeichnis wechseln und die ausführbare Datei ausführen.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-150">Run the app on the Raspberry Pi by switching to the deployment directory and running the executable.</span></span>

    ```bash
    ./SensorTutorial
    ```

    <span data-ttu-id="e1d2e-151">Beachten Sie die sensorausgabe in der Konsole.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-151">Observe the sensor output in the console.</span></span>

1. <span data-ttu-id="e1d2e-152">Beenden Sie das Programm, indem Sie <kbd>STRG + C</kbd>drücken.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-152">Terminate the program by pressing <kbd>Ctrl+C</kbd>.</span></span>

<span data-ttu-id="e1d2e-153">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="e1d2e-153">Congratulations!</span></span> <span data-ttu-id="e1d2e-154">Sie haben I2C verwendet, um Werte von einem Temperatur-/Luftfeuchtigkeits-/barometrischen Drucksensor zu lesen.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-154">You've used I2C to read values from a temperature/humidity/barometric pressure sensor!</span></span>

## <a name="get-the-source-code"></a><span data-ttu-id="e1d2e-155">Herunterladen des Quellcodes</span><span class="sxs-lookup"><span data-stu-id="e1d2e-155">Get the source code</span></span>

<span data-ttu-id="e1d2e-156">Die Quelle für dieses Tutorial ist [auf GitHub verfügbar](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="e1d2e-156">The source for this tutorial is [available on GitHub](https://github.com/MicrosoftDocs/dotnet-iot-assets/tree/master/tutorials/SensorTutorial) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e1d2e-157">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e1d2e-157">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e1d2e-158">Erfahren Sie, wie Sie Text auf einem LCD anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e1d2e-158">Learn how to display text on an LCD</span></span>](../tutorials/lcd-display.md)
