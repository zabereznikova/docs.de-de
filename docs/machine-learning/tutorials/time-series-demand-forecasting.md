---
title: 'Tutorial: Vorhersage des Bedarfs für Fahrradvermietungen – Zeitreihe'
description: Dieses Tutorial zeigt Ihnen, wie Sie den Bedarf für einen Fahrradverleih mithilfe einer univariaten Zeitreihenanalyse und ML.NET prognostizieren können.
ms.date: 11/07/2019
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 026421d7b1b2a0e39118ae712780ca7fc8f6e444
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921253"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a><span data-ttu-id="169a8-103">Tutorial: Prognose des Bedarfs eines Fahrradverleihs mit Zeitreihenanalyse und ML.NET</span><span class="sxs-lookup"><span data-stu-id="169a8-103">Tutorial: Forecast bike rental service demand with time series analysis and ML.NET</span></span>

<span data-ttu-id="169a8-104">Erfahren Sie, wie Sie den Bedarf für einen Fahrradverleih mithilfe einer univariaten Zeitreihenanalyse für in einer SQL Server-Datenbank gespeicherte Daten mit ML.NET prognostizieren können.</span><span class="sxs-lookup"><span data-stu-id="169a8-104">Learn how to forecast demand for a bike rental service using univariate time series analysis on data stored in a SQL Server database with ML.NET.</span></span>

<span data-ttu-id="169a8-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="169a8-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="169a8-106">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="169a8-106">Understand the problem</span></span>
> * <span data-ttu-id="169a8-107">Laden von Daten aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="169a8-107">Load data from a database</span></span>
> * <span data-ttu-id="169a8-108">Erstellen eines Vorhersagemodells</span><span class="sxs-lookup"><span data-stu-id="169a8-108">Create a forecasting model</span></span>
> * <span data-ttu-id="169a8-109">Auswerten eines Vorhersagemodells</span><span class="sxs-lookup"><span data-stu-id="169a8-109">Evaluate forecasting model</span></span>
> * <span data-ttu-id="169a8-110">Speichern eines Vorhersagemodells</span><span class="sxs-lookup"><span data-stu-id="169a8-110">Save a forecasting model</span></span>
> * <span data-ttu-id="169a8-111">Verwenden eines Vorhersagemodells</span><span class="sxs-lookup"><span data-stu-id="169a8-111">Use a forecasting model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="169a8-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="169a8-112">Prerequisites</span></span>

- <span data-ttu-id="169a8-113">[Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="169a8-113">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="time-series-forecasting-sample-overview"></a><span data-ttu-id="169a8-114">Übersicht über das Beispiel zur Zeitreihenvorhersage</span><span class="sxs-lookup"><span data-stu-id="169a8-114">Time series forecasting sample overview</span></span>

<span data-ttu-id="169a8-115">Bei diesem Beispiel handelt es sich um eine **C#.NET Core-Konsolenanwendung**, die den Bedarf für einen Fahrradverleih mithilfe eines univariaten Zeitreihenanalyse-Algorithmus prognostiziert, der unter dem Namen „singuläre Spektralanalyse“ bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="169a8-115">This sample is a **C# .NET Core console application** that forecasts demand for bike rentals using a univariate time series analysis algorithm known as Single Spectrum Analysis.</span></span> <span data-ttu-id="169a8-116">Den Code für dieses Beispiel finden Sie im Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="169a8-116">The code for this sample can be found on the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository on GitHub.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="169a8-117">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="169a8-117">Understand the problem</span></span>

<span data-ttu-id="169a8-118">Um einen effizienten Betrieb zu gewährleisten, spielt die Inventarverwaltung eine wichtige Rolle.</span><span class="sxs-lookup"><span data-stu-id="169a8-118">In order to run an efficient operation, inventory management plays a key role.</span></span> <span data-ttu-id="169a8-119">Zu viel von einem Produkt auf Lager zu haben, bedeutet, dass unverkaufte Produkte in den Regalen stehen und keine Umsätze generieren.</span><span class="sxs-lookup"><span data-stu-id="169a8-119">Having too much of a product in stock means unsold products sitting on the shelves not generating any revenue.</span></span> <span data-ttu-id="169a8-120">Zu wenig Produktvorrat führt zu Umsatzeinbußen und Kunden, die von Wettbewerbern kaufen.</span><span class="sxs-lookup"><span data-stu-id="169a8-120">Having too little product leads to lost sales and customers purchasing from competitors.</span></span> <span data-ttu-id="169a8-121">Daher stellt sich immer wieder die folgende Frage: Wie hoch ist die optimale Menge an Lagerbestand, die vorgehalten werden sollte?</span><span class="sxs-lookup"><span data-stu-id="169a8-121">Therefore, the constant question is, what is the optimal amount of inventory to keep on hand?</span></span> <span data-ttu-id="169a8-122">Die Zeitreihenanalyse hilft, eine Antwort auf diese Fragen zu geben, indem sie historische Daten untersucht, Muster identifiziert und diese Informationen verwendet, um Werte irgendwann in der Zukunft vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="169a8-122">Time-series analysis helps provide an answer to these questions by looking at historical data, identifying patterns, and using this information to forecast values some time in the future.</span></span>

<span data-ttu-id="169a8-123">Das Verfahren zum Analysieren von Daten, das in diesem Tutorial verwendet wird, ist die univariate Zeitreihenanalyse.</span><span class="sxs-lookup"><span data-stu-id="169a8-123">The technique for analyzing data used in this tutorial is univariate time-series analysis.</span></span> <span data-ttu-id="169a8-124">Die univariate Zeitreihenanalyse untersucht eine einzelne numerische Beobachtung über einen bestimmten Zeitraum in bestimmten Intervallen, z.B. die monatlichen Umsätze.</span><span class="sxs-lookup"><span data-stu-id="169a8-124">Univariate time-series analysis takes a look at a single numerical observation over a period of time at specific intervals such as monthly sales.</span></span>

<span data-ttu-id="169a8-125">Der in diesem Tutorial verwendete Algorithmus ist [singuläre Spektralanalyse (Singular Spectrum Analysis, SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span><span class="sxs-lookup"><span data-stu-id="169a8-125">The algorithm used in this tutorial is [Single Spectrum Analysis(SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span></span> <span data-ttu-id="169a8-126">SSA zerlegt eine Zeitreihe in ihre Hauptkomponenten.</span><span class="sxs-lookup"><span data-stu-id="169a8-126">SSA works by decomposing a time-series into a set of principal components.</span></span> <span data-ttu-id="169a8-127">Diese Komponenten können als Teile eines Signals interpretiert werden, das Trends, Rauschen, Saisonalität und vielen anderen Faktoren entspricht.</span><span class="sxs-lookup"><span data-stu-id="169a8-127">These components can be interpreted as the parts of a signal that correspond to trends, noise, seasonality, and many other factors.</span></span> <span data-ttu-id="169a8-128">Anschließend werden diese Komponenten rekonstruiert und verwendet, um Werte in der Zukunft vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="169a8-128">Then, these components are reconstructed and used to forecast values some time in the future.</span></span>

## <a name="create-console-application"></a><span data-ttu-id="169a8-129">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="169a8-129">Create console application</span></span>

1. <span data-ttu-id="169a8-130">Erstellen Sie eine neue **C# .NET Core-Konsolenanwendung** mit dem Namen „BikeDemandForecasting“.</span><span class="sxs-lookup"><span data-stu-id="169a8-130">Create a new **C# .NET Core console application** called "BikeDemandForecasting".</span></span>
1. <span data-ttu-id="169a8-131">Installieren des NuGet-Pakets **Microsoft.ML** Version **1.4.0**</span><span class="sxs-lookup"><span data-stu-id="169a8-131">Install **Microsoft.ML** version **1.4.0** NuGet package</span></span>
    1. <span data-ttu-id="169a8-132">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="169a8-132">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="169a8-133">Wählen Sie „nuget.org“ als Paketquelle aus, wählen Sie die Registerkarte **Durchsuchen** aus, und suchen Sie nach **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="169a8-133">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="169a8-134">Aktivieren Sie das Kontrollkästchen **Vorabversion einbeziehen**.</span><span class="sxs-lookup"><span data-stu-id="169a8-134">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="169a8-135">Wählen Sie die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="169a8-135">Select the **Install** button.</span></span>
    1. <span data-ttu-id="169a8-136">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="169a8-136">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="169a8-137">Wiederholen Sie diese Schritte für **System.Data.SqlClient** Version **4.7.0** und **Microsoft.ML.TimeSeries** Version **1.4.0**.</span><span class="sxs-lookup"><span data-stu-id="169a8-137">Repeat these steps for **System.Data.SqlClient** version **4.7.0** and **Microsoft.ML.TimeSeries** version **1.4.0**.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="169a8-138">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="169a8-138">Prepare and understand the data</span></span>

1. <span data-ttu-id="169a8-139">Erstellen Sie ein Verzeichnis namens *Data*.</span><span class="sxs-lookup"><span data-stu-id="169a8-139">Create a directory called *Data*.</span></span>
1. <span data-ttu-id="169a8-140">Laden Sie die [Datenbankdatei *DailyDemand.mdf*](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) herunter, und speichern Sie sie im Verzeichnis *Data*.</span><span class="sxs-lookup"><span data-stu-id="169a8-140">Download the [*DailyDemand.mdf* database file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) and save it to the *Data* directory.</span></span>

> [!NOTE]
> <span data-ttu-id="169a8-141">Die in diesem Tutorial verwendeten Daten stammen aus dem [UCI Bike Sharing-Dataset](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span><span class="sxs-lookup"><span data-stu-id="169a8-141">The data used in this tutorial comes from the [UCI Bike Sharing Dataset](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span></span> <span data-ttu-id="169a8-142">Fanaee-T, Hadi und Gama, Joao, „Event labeling combining ensemble detectors and background knowledge“, Progress in Artificial Intelligence (2013): S. 1-15, Springer Berlin Heidelberg, [Weblink](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span><span class="sxs-lookup"><span data-stu-id="169a8-142">Fanaee-T, Hadi, and Gama, Joao, 'Event labeling combining ensemble detectors and background knowledge', Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [Web Link](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span></span>

<span data-ttu-id="169a8-143">Das ursprüngliche Dataset enthält mehrere Spalten, die der Saisonalität und dem Wetter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="169a8-143">The original dataset contains several columns corresponding to seasonality and weather.</span></span> <span data-ttu-id="169a8-144">Aus Gründen der Kürze und weil der in diesem Tutorial verwendete Algorithmus nur die Werte einer einzigen numerischen Spalte benötigt, wurde das ursprüngliche Dataset so zusammengefasst, dass es nur die folgenden Spalten enthält:</span><span class="sxs-lookup"><span data-stu-id="169a8-144">For brevity and because the algorithm used in this tutorial only requires the values from a single numerical column, the original dataset has been condensed to include only the following columns:</span></span>

- <span data-ttu-id="169a8-145">**dteday**: Das Datum der Beobachtung.</span><span class="sxs-lookup"><span data-stu-id="169a8-145">**dteday**: The date of the observation.</span></span>
- <span data-ttu-id="169a8-146">**year**: Das codierte Jahr der Beobachtung (0 = 2011, 1 = 2012).</span><span class="sxs-lookup"><span data-stu-id="169a8-146">**year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
- <span data-ttu-id="169a8-147">**cnt**: Die Gesamtzahl der Fahrradvermietungen für diesen Tag.</span><span class="sxs-lookup"><span data-stu-id="169a8-147">**cnt**: The total number of bike rentals for that day.</span></span>

<span data-ttu-id="169a8-148">Das ursprüngliche Dataset wird einer Datenbanktabelle mit dem folgenden Schema in einer SQL Server Datenbank zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="169a8-148">The original dataset is mapped to a database table with the following schema in a SQL Server database.</span></span>

```SQL
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

<span data-ttu-id="169a8-149">Im Folgenden finden Sie ein Beispiel für die Daten:</span><span class="sxs-lookup"><span data-stu-id="169a8-149">The following is a sample of the data:</span></span>

| <span data-ttu-id="169a8-150">RentalDate</span><span class="sxs-lookup"><span data-stu-id="169a8-150">RentalDate</span></span> | <span data-ttu-id="169a8-151">Jahr</span><span class="sxs-lookup"><span data-stu-id="169a8-151">Year</span></span> | <span data-ttu-id="169a8-152">TotalRentals</span><span class="sxs-lookup"><span data-stu-id="169a8-152">TotalRentals</span></span> |
| --- | --- | --- |
|<span data-ttu-id="169a8-153">1/1/2011</span><span class="sxs-lookup"><span data-stu-id="169a8-153">1/1/2011</span></span>|<span data-ttu-id="169a8-154">0</span><span class="sxs-lookup"><span data-stu-id="169a8-154">0</span></span>|<span data-ttu-id="169a8-155">985</span><span class="sxs-lookup"><span data-stu-id="169a8-155">985</span></span>|
|<span data-ttu-id="169a8-156">1/2/2011</span><span class="sxs-lookup"><span data-stu-id="169a8-156">1/2/2011</span></span>|<span data-ttu-id="169a8-157">0</span><span class="sxs-lookup"><span data-stu-id="169a8-157">0</span></span>|<span data-ttu-id="169a8-158">801</span><span class="sxs-lookup"><span data-stu-id="169a8-158">801</span></span>|
|<span data-ttu-id="169a8-159">1/3/2011</span><span class="sxs-lookup"><span data-stu-id="169a8-159">1/3/2011</span></span>|<span data-ttu-id="169a8-160">0</span><span class="sxs-lookup"><span data-stu-id="169a8-160">0</span></span>|<span data-ttu-id="169a8-161">1349</span><span class="sxs-lookup"><span data-stu-id="169a8-161">1349</span></span>|

### <a name="create-input-and-output-classes"></a><span data-ttu-id="169a8-162">Erstellen von Eingabe- und Ausgabeklassen</span><span class="sxs-lookup"><span data-stu-id="169a8-162">Create input and output classes</span></span>

1. <span data-ttu-id="169a8-163">Ersetzen Sie in *Program.cs* die vorhandenen `using`-Anweisungen durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="169a8-163">Open *Program.cs* file and replace the existing `using` statements with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. <span data-ttu-id="169a8-164">Erstellen Sie die `ModelInput`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="169a8-164">Create `ModelInput` class.</span></span> <span data-ttu-id="169a8-165">Fügen Sie unter der `Program`-Klasse den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="169a8-165">Below the `Program` class, add the following code.</span></span>

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    <span data-ttu-id="169a8-166">Die `ModelInput`-Klasse enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="169a8-166">The `ModelInput` class contains the following columns:</span></span>

    - <span data-ttu-id="169a8-167">**RentalDate**: Das Datum der Beobachtung.</span><span class="sxs-lookup"><span data-stu-id="169a8-167">**RentalDate**: The date of the observation.</span></span>
    - <span data-ttu-id="169a8-168">**Year**: Das codierte Jahr der Beobachtung (0 = 2011, 1 = 2012).</span><span class="sxs-lookup"><span data-stu-id="169a8-168">**Year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
    - <span data-ttu-id="169a8-169">**TotalRentals**: Die Gesamtzahl der Fahrradvermietungen für diesen Tag.</span><span class="sxs-lookup"><span data-stu-id="169a8-169">**TotalRentals**: The total number of bike rentals for that day.</span></span>

1. <span data-ttu-id="169a8-170">Erstellen Sie die `ModelOutput`-Klasse unterhalb der neu erstellten `ModelInput`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="169a8-170">Create `ModelOutput` class below the newly created `ModelInput` class.</span></span>

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    <span data-ttu-id="169a8-171">Die `ModelOutput`-Klasse enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="169a8-171">The `ModelOutput` class contains the following columns:</span></span>

    - <span data-ttu-id="169a8-172">**ForecastedRentals**: Die vorhergesagten Werte für den Vorhersagezeitraum.</span><span class="sxs-lookup"><span data-stu-id="169a8-172">**ForecastedRentals**: The predicted values for the forecasted period.</span></span>
    - <span data-ttu-id="169a8-173">**LowerBoundRentals**: Die vorhergesagten Mindestwerte für den Vorhersagezeitraum.</span><span class="sxs-lookup"><span data-stu-id="169a8-173">**LowerBoundRentals**: The predicted minimum values for the forecasted period.</span></span>
    - <span data-ttu-id="169a8-174">**UpperBoundRentals**: Die vorhergesagten Maximalwerte für den Vorhersagezeitraum.</span><span class="sxs-lookup"><span data-stu-id="169a8-174">**UpperBoundRentals**: The predicted maximum values for the forecasted period.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="169a8-175">Definieren von Pfaden und Initialisieren von Variablen</span><span class="sxs-lookup"><span data-stu-id="169a8-175">Define paths and initialize variables</span></span>

1. <span data-ttu-id="169a8-176">Definieren Sie innerhalb der `Main`-Methode Variablen, um den Speicherort der Daten, die Verbindungszeichenfolge und den Speicherort für das trainierte Modell zu speichern.</span><span class="sxs-lookup"><span data-stu-id="169a8-176">Inside the `Main` method, define variables to store the location of your data, connection string, and where to save the trained model.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. <span data-ttu-id="169a8-177">Initialisieren Sie die `mlContext`-Variable mit einer neuen Instanz von [`MLContext`](xref:Microsoft.ML.MLContext), indem Sie der `Main`-Methode die folgende Zeile hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="169a8-177">Initialize the `mlContext` variable with a new instance of [`MLContext`](xref:Microsoft.ML.MLContext) by adding the following line to the `Main` method.</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    <span data-ttu-id="169a8-178">Die [`MLContext`](xref:Microsoft.ML.MLContext)-Klasse ist der Ausgangspunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von mlContext wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="169a8-178">The [`MLContext`](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="169a8-179">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="169a8-179">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="169a8-180">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="169a8-180">Load the data</span></span>

1. <span data-ttu-id="169a8-181">Erstellen Sie das `DatabaseLoader`-Element, mit dem Datensätze des Typs `ModelInput` geladen werden.</span><span class="sxs-lookup"><span data-stu-id="169a8-181">Create `DatabaseLoader` that loads records of type `ModelInput`.</span></span>

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. <span data-ttu-id="169a8-182">Definieren Sie die Abfrage, um die Daten aus der Datenbank zu laden.</span><span class="sxs-lookup"><span data-stu-id="169a8-182">Define the query to load the data from the database.</span></span>

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    <span data-ttu-id="169a8-183">ML.NET-Algorithmen erwarten, dass Daten vom Typ [`Single`](xref:System.Single) sind.</span><span class="sxs-lookup"><span data-stu-id="169a8-183">ML.NET algorithms expect data to be of type [`Single`](xref:System.Single).</span></span> <span data-ttu-id="169a8-184">Daher müssen numerische Werte aus der Datenbank, die nicht vom Typ [`Real`](xref:System.Data.SqlDbType) (ein Gleitkommawert mit einfacher Genauigkeit) sind, in [`Real`](xref:System.Data.SqlDbType) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="169a8-184">Therefore, numerical values coming from the database that are not of type [`Real`](xref:System.Data.SqlDbType), a single-precision floating-point value, have to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span>

    <span data-ttu-id="169a8-185">Die Spalten `Year` und `TotalRental` sind Integertypen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="169a8-185">The `Year` and `TotalRental` columns are both integer types in the database.</span></span> <span data-ttu-id="169a8-186">Mithilfe der integrierten Funktion `CAST` werden beide Werte in `Real` umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="169a8-186">Using the `CAST` built-in function, they are both cast to `Real`.</span></span>

1. <span data-ttu-id="169a8-187">Erstellen Sie eine `DatabaseSource`, um eine Verbindung mit der Datenbank herzustellen und die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="169a8-187">Create a `DatabaseSource` to connect to the database and execute the query.</span></span>

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. <span data-ttu-id="169a8-188">Laden Sie die Daten in eine `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="169a8-188">Load the data into an `IDataView`.</span></span>

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. <span data-ttu-id="169a8-189">Das Dataset enthält Daten aus zwei Jahren.</span><span class="sxs-lookup"><span data-stu-id="169a8-189">The dataset contains two years worth of data.</span></span> <span data-ttu-id="169a8-190">Nur Daten aus dem ersten Jahr werden für das Training verwendet, das zweite Jahr wird zum Vergleichen der tatsächlichen Werte mit der vom Modell generierten Vorhersage verwendet.</span><span class="sxs-lookup"><span data-stu-id="169a8-190">Only data from the first year is used for training, the second year is held out to compare the actual values against the forecast produced by the model.</span></span> <span data-ttu-id="169a8-191">Filtern Sie die Daten mithilfe der [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*)-Transformation.</span><span class="sxs-lookup"><span data-stu-id="169a8-191">Filter the data using the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) transform.</span></span>

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    <span data-ttu-id="169a8-192">Für das erste Jahr werden nur die Werte in der Spalte `Year`, die kleiner als 1 ist, durch Festlegen des `upperBound`-Parameters auf 1 ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="169a8-192">For the first year, only the values in the `Year` column less than 1 are selected by setting the `upperBound` parameter to 1.</span></span> <span data-ttu-id="169a8-193">Umgekehrt werden für das zweite Jahr Werte größer oder gleich 1 ausgewählt, indem der `lowerBound`-Parameter auf 1 festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="169a8-193">Conversely, for the second year, values greater than or equal to 1 are selected by setting the `lowerBound` parameter to 1.</span></span>

## <a name="define-time-series-analysis-pipeline"></a><span data-ttu-id="169a8-194">Definieren einer Zeitreihenanalyse-Pipeline</span><span class="sxs-lookup"><span data-stu-id="169a8-194">Define time series analysis pipeline</span></span>

1. <span data-ttu-id="169a8-195">Definieren Sie eine Pipeline, die [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) verwendet, um Werte in einem Zeitreihendataset vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="169a8-195">Define a pipeline that uses the [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) to forecast values in a time-series dataset.</span></span>

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    <span data-ttu-id="169a8-196">Die `forecastingPipeline` nimmt für das erste Jahr 365 Datenpunkte an und teilt ein Zeitreihendataset in Stichproben von jeweils 30 Tagen (monatlich) auf, wie vom `seriesLength`-Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="169a8-196">The `forecastingPipeline` takes 365 data points for the first year and samples or splits the time-series dataset into 30-day (monthly) intervals as specified by the `seriesLength` parameter.</span></span> <span data-ttu-id="169a8-197">Jede dieser Stichproben wird anhand eines wöchentlichen oder ein 7-tägigen Fensters analysiert.</span><span class="sxs-lookup"><span data-stu-id="169a8-197">Each of these samples is analyzed through weekly or a 7-day window.</span></span> <span data-ttu-id="169a8-198">Bei der Ermittlung des prognostizierten Werts für die nächste(n) Zeitspanne(n) werden die Werte der letzten sieben Tage verwendet, um eine Prognose zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="169a8-198">When determining what the forecasted value for the next period(s) is, the values from previous seven days are used to make a prediction.</span></span> <span data-ttu-id="169a8-199">Das Modell wird so festgelegt, dass sieben Zeitspannen in der Zukunft vorhergesagt werden, wie durch den `horizon`-Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="169a8-199">The model is set to forecast seven periods into the future as defined by the `horizon` parameter.</span></span> <span data-ttu-id="169a8-200">Da eine Vorhersage eine fundierte Vermutung ist, ist sie nicht immer zu 100 % genau.</span><span class="sxs-lookup"><span data-stu-id="169a8-200">Because a forecast is an informed guess, it's not always 100% accurate.</span></span> <span data-ttu-id="169a8-201">Daher ist es gut, den Wertebereich in den besten und schlechtesten Szenarien zu kennen, wie durch die oberen und unteren Grenzen definiert.</span><span class="sxs-lookup"><span data-stu-id="169a8-201">Therefore, it's good to know the range of values in the best and worst-case scenarios as defined by the upper and lower bounds.</span></span> <span data-ttu-id="169a8-202">In diesem Fall wird der Vertrauensgrad für die untere und obere Grenze auf 95 % festgelegt.</span><span class="sxs-lookup"><span data-stu-id="169a8-202">In this case, the level of confidence for the lower and upper bounds is set to 95%.</span></span> <span data-ttu-id="169a8-203">Der Vertrauensgrad kann entsprechend angehoben oder gesenkt werden.</span><span class="sxs-lookup"><span data-stu-id="169a8-203">The confidence level can be increased or decreased accordingly.</span></span> <span data-ttu-id="169a8-204">Je höher der Wert, desto größer ist der Bereich zwischen der oberen und unteren Grenze, um das gewünschte Maß an Vertrauen zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="169a8-204">The higher the value, the wider the range is between the upper and lower bounds to achieve the desired level of confidence.</span></span>

1. <span data-ttu-id="169a8-205">Verwenden Sie die [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*)-Methode, um das Modell zu trainieren und die Daten an die zuvor definierte `forecastingPipeline` anzupassen.</span><span class="sxs-lookup"><span data-stu-id="169a8-205">Use the [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*) method to train the model and fit the data to the previously defined `forecastingPipeline`.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a><span data-ttu-id="169a8-206">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="169a8-206">Evaluate the model</span></span>

<span data-ttu-id="169a8-207">Bewerten Sie die Leistungsfähigkeit des Modells, indem Sie die Daten des nächsten Jahrs prognostizieren und mit den tatsächlichen Werten vergleichen.</span><span class="sxs-lookup"><span data-stu-id="169a8-207">Evaluate how well the model performs by forecasting next year's data and comparing it against the actual values.</span></span>

1. <span data-ttu-id="169a8-208">Erstellen Sie unter der `Main`-Methode eine neue Hilfsmethode namens `Evaluate`.</span><span class="sxs-lookup"><span data-stu-id="169a8-208">Below the `Main` method, create a new utility method called `Evaluate`.</span></span>

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="169a8-209">Prognostizieren Sie in der `Evaluate`-Methode die Daten des zweiten Jahrs mithilfe der [`Transform`](xref:Microsoft.ML.ITransformer.Transform*)-Methode mit dem trainierten Modell.</span><span class="sxs-lookup"><span data-stu-id="169a8-209">Inside the `Evaluate` method, forecast the second year's data by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method with the trained model.</span></span>

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. <span data-ttu-id="169a8-210">Verwenden Sie die [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode, um die tatsächlichen Werte aus den Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="169a8-210">Get the actual values from the data by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. <span data-ttu-id="169a8-211">Verwenden Sie die [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode, um die Vorhersagewerte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="169a8-211">Get the forecast values by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. <span data-ttu-id="169a8-212">Berechnen Sie die Differenz zwischen den tatsächlichen Werten und den Vorhersagewerten, die im Allgemeinen als „Fehler“ bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="169a8-212">Calculate the difference between the actual and forecast values, commonly referred to as the error.</span></span>

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. <span data-ttu-id="169a8-213">Messen Sie die Leistung, indem Sie die Werte Mean Absolute Error (Mittlerer absoluter Fehler) und Root Mean Squared Error (Mittlerer quadratischer Fehler) berechnen.</span><span class="sxs-lookup"><span data-stu-id="169a8-213">Measure performance by computing the Mean Absolute Error and Root Mean Squared Error values.</span></span>

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    <span data-ttu-id="169a8-214">Die folgenden Metriken werden verwendet, um die Leistung auszuwerten:</span><span class="sxs-lookup"><span data-stu-id="169a8-214">To evaluate performance, the following metrics are used:</span></span>

    - <span data-ttu-id="169a8-215">**Mean Absolute Error** (Mittlerer absoluter Fehler): Misst, wie nahe Vorhersagen am tatsächlichen Wert liegen.</span><span class="sxs-lookup"><span data-stu-id="169a8-215">**Mean Absolute Error**: Measures how close predictions are to the actual value.</span></span> <span data-ttu-id="169a8-216">Dieser Wert liegt zwischen 0 und unendlich.</span><span class="sxs-lookup"><span data-stu-id="169a8-216">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="169a8-217">Je näher der Wert an 0 ist, desto besser ist die Qualität des Modells.</span><span class="sxs-lookup"><span data-stu-id="169a8-217">The closer to 0, the better the quality of the model.</span></span>
    - <span data-ttu-id="169a8-218">**Root Mean Squared Error** (Mittlerer quadratischer Fehler): Fasst den Fehler im Modell zusammen.</span><span class="sxs-lookup"><span data-stu-id="169a8-218">**Root Mean Squared Error**: Summarizes the error in the model.</span></span> <span data-ttu-id="169a8-219">Dieser Wert liegt zwischen 0 und unendlich.</span><span class="sxs-lookup"><span data-stu-id="169a8-219">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="169a8-220">Je näher der Wert an 0 ist, desto besser ist die Qualität des Modells.</span><span class="sxs-lookup"><span data-stu-id="169a8-220">The closer to 0, the better the quality of the model.</span></span>

1. <span data-ttu-id="169a8-221">Geben Sie die Metriken an die Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="169a8-221">Output the metrics to the console.</span></span>

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. <span data-ttu-id="169a8-222">Verwenden Sie die `Evaluate`-Methode in der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="169a8-222">Use the `Evaluate` method inside the `Main` method.</span></span>

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a><span data-ttu-id="169a8-223">Speichern des Modells</span><span class="sxs-lookup"><span data-stu-id="169a8-223">Save the model</span></span>

<span data-ttu-id="169a8-224">Wenn Sie mit Ihrem Modell zufrieden sind, speichern Sie es zur späteren Verwendung in anderen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="169a8-224">If you're satisfied with your model, save it for later use in other applications.</span></span>

1. <span data-ttu-id="169a8-225">Erstellen Sie in der `Main`-Methode eine [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="169a8-225">In the `Main` method, create a [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602).</span></span> <span data-ttu-id="169a8-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) ist eine bequeme Methode, um einzelne Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="169a8-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) is a convenience method to make single predictions.</span></span>

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. <span data-ttu-id="169a8-227">Speichern Sie das Modell in einer Datei namens `MLModel.zip`, wie durch die zuvor definierten `modelPath`-Variable angegeben.</span><span class="sxs-lookup"><span data-stu-id="169a8-227">Save the model to a file called `MLModel.zip` as specified by the previously defined `modelPath` variable.</span></span> <span data-ttu-id="169a8-228">Verwenden Sie die [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*)-Methode, um das Modell zu speichern.</span><span class="sxs-lookup"><span data-stu-id="169a8-228">Use the [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*) method to save the model.</span></span>

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a><span data-ttu-id="169a8-229">Verwenden des Modells zum Vorhersagen des Bedarfs</span><span class="sxs-lookup"><span data-stu-id="169a8-229">Use the model to forecast demand</span></span>

1. <span data-ttu-id="169a8-230">Erstellen Sie unter der `Evaluate`-Methode eine neue Hilfsmethode namens `Forecast`.</span><span class="sxs-lookup"><span data-stu-id="169a8-230">Below the `Evaluate` method, create a new utility method called `Forecast`.</span></span>

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="169a8-231">Verwenden Sie innerhalb der `Forecast`-Methode die [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*)-Methode, um die Vermietungen der nächsten sieben Tage vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="169a8-231">Inside the `Forecast` method, use the [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*) method to forecast rentals for the next seven days.</span></span>

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. <span data-ttu-id="169a8-232">Bringen Sie die tatsächlichen und die vorhergesagten Werte für sieben Zeiträume in Einklang.</span><span class="sxs-lookup"><span data-stu-id="169a8-232">Align the actual and forecast values for seven periods.</span></span>

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. <span data-ttu-id="169a8-233">Iterieren Sie durch die Vorhersageausgabe, und zeigen Sie diese in der Konsole an.</span><span class="sxs-lookup"><span data-stu-id="169a8-233">Iterate through the forecast output and display it on the console.</span></span>

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a><span data-ttu-id="169a8-234">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="169a8-234">Run the application</span></span>

1. <span data-ttu-id="169a8-235">Rufen Sie in der `Main`-Methode die `Forecast`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="169a8-235">Inside the `Main` method, call the `Forecast` method.</span></span>

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. <span data-ttu-id="169a8-236">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="169a8-236">Run the application.</span></span> <span data-ttu-id="169a8-237">Eine ähnliche Ausgabe wie die folgende sollte in der Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="169a8-237">Output similar to that below should appear on the console.</span></span> <span data-ttu-id="169a8-238">Aus Gründen der Kürze wurde die Ausgabe komprimiert.</span><span class="sxs-lookup"><span data-stu-id="169a8-238">For brevity, the output has been condensed.</span></span>

    ```text
    Evaluation Metrics
    ---------------------
    Mean Absolute Error: 726.416
    Root Mean Squared Error: 987.658

    Rental Forecast
    ---------------------
    Date: 1/1/2012
    Actual Rentals: 2294
    Lower Estimate: 1197.842
    Forecast: 2334.443
    Upper Estimate: 3471.044

    Date: 1/2/2012
    Actual Rentals: 1951
    Lower Estimate: 1148.412
    Forecast: 2360.861
    Upper Estimate: 3573.309
    ```

<span data-ttu-id="169a8-239">Bei der Untersuchung der tatsächlichen und der vorhergesagten Werte werden die folgenden Beziehungen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="169a8-239">Inspection of the actual and forecasted values shows the following relationships:</span></span>

![Vergleich der tatsächlichen und der vorhergesagten Werte](./media/time-series-demand-forecasting/forecast.png)

<span data-ttu-id="169a8-241">Obwohl die vorhergesagten Werte nicht die genaue Anzahl von Vermietungen vorhersagen, stellen sie einen engeren Bereich von Werten bereit, der es im Betrieb ermöglicht, die Verwendung von Ressourcen zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="169a8-241">While the forecasted values are not predicting the exact number of rentals, they provide a more narrow range of values that allows an operation to optimize their use of resources.</span></span>

<span data-ttu-id="169a8-242">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="169a8-242">Congratulations!</span></span> <span data-ttu-id="169a8-243">Sie haben nun erfolgreich ein Machine Learning-Zeitreihenmodell erstellt, um den Bedarf für die Fahrradvermietung zu prognostizieren.</span><span class="sxs-lookup"><span data-stu-id="169a8-243">You've now successfully built a time series machine learning model to forecast bike rental demand.</span></span>

<span data-ttu-id="169a8-244">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand).</span><span class="sxs-lookup"><span data-stu-id="169a8-244">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="169a8-245">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="169a8-245">Next steps</span></span>

- [<span data-ttu-id="169a8-246">Machine Learning-Aufgaben in ML.NET</span><span class="sxs-lookup"><span data-stu-id="169a8-246">Machine learning tasks in ML.NET</span></span>](../resources/tasks.md)
- [<span data-ttu-id="169a8-247">Verbessern der Modellgenauigkeit</span><span class="sxs-lookup"><span data-stu-id="169a8-247">Improve model accuracy</span></span>](../resources/improve-machine-learning-model-ml-net.md)
