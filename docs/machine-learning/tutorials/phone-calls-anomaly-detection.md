---
title: 'Tutorial: Erkennen von Anomalien bei Telefonanrufen'
description: Hier erfahren Sie, wie Sie eine Anwendung zur Erkennung von Anomalien bei Zeitreihendaten erstellen. Dieses Tutorial erstellt mithilfe von C# in Visual Studio 2019 eine .NET Core-Konsolenanwendung.
ms.date: 12/04/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 3451a44f8fa7ae85625687b7d52f120c411df1b6
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97634052"
---
# <a name="tutorial-detect-anomalies-in-time-series-with-mlnet"></a><span data-ttu-id="6ecad-104">Tutorial: Erkennen von Anomalien bei Zeitreihen mit ML.NET</span><span class="sxs-lookup"><span data-stu-id="6ecad-104">Tutorial: Detect anomalies in time series with ML.NET</span></span>

<span data-ttu-id="6ecad-105">Hier erfahren Sie, wie Sie eine Anwendung zur Erkennung von Anomalien bei Zeitreihendaten erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ecad-105">Learn how to build an anomaly detection application for time series data.</span></span> <span data-ttu-id="6ecad-106">Dieses Tutorial erstellt mithilfe von C# in Visual Studio 2019 eine .NET Core-Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="6ecad-106">This tutorial creates a .NET Core console application using C# in Visual Studio 2019.</span></span>

<span data-ttu-id="6ecad-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6ecad-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="6ecad-108">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="6ecad-108">Load the data</span></span>
> * <span data-ttu-id="6ecad-109">Erkennen eines Zeitraums für eine Zeitreihe</span><span class="sxs-lookup"><span data-stu-id="6ecad-109">Detect period for a time series</span></span>
> * <span data-ttu-id="6ecad-110">Erkennen von Anomalien bei einer periodischen Zeitreihe</span><span class="sxs-lookup"><span data-stu-id="6ecad-110">Detect anomaly for a periodical time series</span></span>

<span data-ttu-id="6ecad-111">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="6ecad-111">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6ecad-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6ecad-112">Prerequisites</span></span>

* <span data-ttu-id="6ecad-113">[Visual Studio 2019 Version 16.7.8 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="6ecad-113">[Visual Studio 2019 version 16.7.8 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="6ecad-114">Dataset „phone-calls.csv“</span><span class="sxs-lookup"><span data-stu-id="6ecad-114">The phone-calls.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv)

## <a name="create-a-console-application"></a><span data-ttu-id="6ecad-115">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="6ecad-115">Create a console application</span></span>

1. <span data-ttu-id="6ecad-116">Erstellen Sie eine **.NET Core-Konsolenanwendung in C#** mit dem Namen „ProductSalesAnomalyDetection“.</span><span class="sxs-lookup"><span data-stu-id="6ecad-116">Create a **C# .NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="6ecad-117">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6ecad-117">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="6ecad-118">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="6ecad-118">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="6ecad-119">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="6ecad-119">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="6ecad-120">Wählen Sie als Paketquelle „nuget.org“ aus. Klicken Sie dann auf die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und klicken Sie anschließend auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="6ecad-120">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="6ecad-121">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="6ecad-121">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="6ecad-122">Wiederholen Sie diese Schritte für **Microsoft.ML.TimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="6ecad-122">Repeat these steps for **Microsoft.ML.TimeSeries**.</span></span>

4. <span data-ttu-id="6ecad-123">Fügen Sie am Anfang der Datei *Program.cs* die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="6ecad-123">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="6ecad-124">Herunterladen der Daten</span><span class="sxs-lookup"><span data-stu-id="6ecad-124">Download your data</span></span>

1. <span data-ttu-id="6ecad-125">Laden Sie die das Dataset herunter, und speichern Sie es im Ordner *Data*, den Sie vorher erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="6ecad-125">Download the dataset and save it to the *Data* folder you previously created:</span></span>

    <span data-ttu-id="6ecad-126">Klicken Sie mit der rechten Maustaste auf [*phone-calls.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv) und anschließend auf „Link speichern unter“ oder „Ziel speichern unter“.</span><span class="sxs-lookup"><span data-stu-id="6ecad-126">Right click on [*phone-calls.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="6ecad-127">Achten Sie darauf, die \*CSV-Datei entweder im Ordner *Data* zu speichern oder sie in den Ordner *Data* zu verschieben, nachdem Sie die \*CSV-Datei an anderer Stelle gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="6ecad-127">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="6ecad-128">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*CSV Datei, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="6ecad-128">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="6ecad-129">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="6ecad-129">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="6ecad-130">Die folgende Tabelle enthält eine Datenvorschau aus Ihrem \*CSV-Datei:</span><span class="sxs-lookup"><span data-stu-id="6ecad-130">The following table is a data preview from your \*.csv file:</span></span>

| <span data-ttu-id="6ecad-131">timestamp</span><span class="sxs-lookup"><span data-stu-id="6ecad-131">timestamp</span></span>  | <span data-ttu-id="6ecad-132">value</span><span class="sxs-lookup"><span data-stu-id="6ecad-132">value</span></span> |
|--------|--------------|
| <span data-ttu-id="6ecad-133">2018/9/3</span><span class="sxs-lookup"><span data-stu-id="6ecad-133">2018/9/3</span></span>  | <span data-ttu-id="6ecad-134">36.69670857</span><span class="sxs-lookup"><span data-stu-id="6ecad-134">36.69670857</span></span>  |
| <span data-ttu-id="6ecad-135">2018/9/4</span><span class="sxs-lookup"><span data-stu-id="6ecad-135">2018/9/4</span></span>  | <span data-ttu-id="6ecad-136">35.74160571</span><span class="sxs-lookup"><span data-stu-id="6ecad-136">35.74160571</span></span>  |
| <span data-ttu-id="6ecad-137">.....</span><span class="sxs-lookup"><span data-stu-id="6ecad-137">.....</span></span>  | <span data-ttu-id="6ecad-138">.....</span><span class="sxs-lookup"><span data-stu-id="6ecad-138">.....</span></span>  |
| <span data-ttu-id="6ecad-139">2018/10/3</span><span class="sxs-lookup"><span data-stu-id="6ecad-139">2018/10/3</span></span>  | <span data-ttu-id="6ecad-140">34.49893429</span><span class="sxs-lookup"><span data-stu-id="6ecad-140">34.49893429</span></span>  |
| <span data-ttu-id="6ecad-141">...</span><span class="sxs-lookup"><span data-stu-id="6ecad-141">...</span></span>    | <span data-ttu-id="6ecad-142">....</span><span class="sxs-lookup"><span data-stu-id="6ecad-142">....</span></span>   |

<span data-ttu-id="6ecad-143">Diese Datei stellt eine Zeitreihe dar.</span><span class="sxs-lookup"><span data-stu-id="6ecad-143">This file represents a time-series.</span></span> <span data-ttu-id="6ecad-144">Jede Zeile in der Datei entspricht einem Datenpunkt.</span><span class="sxs-lookup"><span data-stu-id="6ecad-144">Each row in the file is a data point.</span></span> <span data-ttu-id="6ecad-145">Jeder Datenpunkt verfügt über die beiden Attribute `timestamp` und `value`, mit denen die Anzahl der Telefonanrufe für jeden Tag dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6ecad-145">Each data point has two attributes, namely, `timestamp` and `value`, to represent the number of phone calls at each day.</span></span> <span data-ttu-id="6ecad-146">Die Anzahl der Telefonanrufe wird zur Desensitivität transformiert.</span><span class="sxs-lookup"><span data-stu-id="6ecad-146">The number of phone calls is transformed to de-sensitivity.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="6ecad-147">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="6ecad-147">Create classes and define paths</span></span>

<span data-ttu-id="6ecad-148">Als Nächstes definieren Sie Ihre Datenstruktur der Eingabe- und Vorhersageklasse.</span><span class="sxs-lookup"><span data-stu-id="6ecad-148">Next, define your input and prediction class data structures.</span></span>

<span data-ttu-id="6ecad-149">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="6ecad-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="6ecad-150">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Hinzufügen > Neues Element**.</span><span class="sxs-lookup"><span data-stu-id="6ecad-150">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="6ecad-151">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *PhoneCallsData.cs*.</span><span class="sxs-lookup"><span data-stu-id="6ecad-151">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *PhoneCallsData.cs*.</span></span> <span data-ttu-id="6ecad-152">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6ecad-152">Then, select the **Add** button.</span></span>

   <span data-ttu-id="6ecad-153">Die Datei *PhoneCallsData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6ecad-153">The *PhoneCallsData.cs* file opens in the code editor.</span></span>

3. <span data-ttu-id="6ecad-154">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *PhoneCallsData.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="6ecad-154">Add the following `using` statement to the top of *PhoneCallsData.cs*:</span></span>

   ```csharp
   using Microsoft.ML.Data;
   ```

4. <span data-ttu-id="6ecad-155">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `PhoneCallsData` und `PhoneCallsPrediction` der Datei *PhoneCallsData.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="6ecad-155">Remove the existing class definition and add the following code, which has two classes `PhoneCallsData` and `PhoneCallsPrediction`, to the *PhoneCallsData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](./snippets/phone-calls-anomaly-detection/csharp/PhoneCallsData.cs#DeclareTypes "Declare data record types")]

    <span data-ttu-id="6ecad-156">`PhoneCallsData` ist eine Klasse für Eingabedaten.</span><span class="sxs-lookup"><span data-stu-id="6ecad-156">`PhoneCallsData` specifies an input data class.</span></span> <span data-ttu-id="6ecad-157">Das [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29)-Attribut legt fest, welche Spalten (durch Angabe des Spaltenindex) im Dataset geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6ecad-157">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="6ecad-158">Es verfügt über die beiden Attribute `timestamp` und `value`, die den jeweiligen Attributen in der Datendatei entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6ecad-158">It has two attributes `timestamp` and `value` that correspond to the same attributes in the data file.</span></span>

    <span data-ttu-id="6ecad-159">`PhoneCallsPrediction` gibt die Vorhersagedatenklasse an.</span><span class="sxs-lookup"><span data-stu-id="6ecad-159">`PhoneCallsPrediction` specifies the prediction data class.</span></span> <span data-ttu-id="6ecad-160">Bei der SR-CNN-Erkennung hängt die Vorhersage vom angegebenen [Erkennungsmodus](xref:Microsoft.ML.TimeSeries.SrCnnDetectMode) ab.</span><span class="sxs-lookup"><span data-stu-id="6ecad-160">For SR-CNN detector, the prediction depends on the [detect mode](xref:Microsoft.ML.TimeSeries.SrCnnDetectMode) specified.</span></span> <span data-ttu-id="6ecad-161">In diesem Beispiel wählen wir den Modus `AnomalyAndMargin` aus.</span><span class="sxs-lookup"><span data-stu-id="6ecad-161">In this sample, we select the `AnomalyAndMargin` mode.</span></span> <span data-ttu-id="6ecad-162">Die Ausgabe enthält sieben Spalten.</span><span class="sxs-lookup"><span data-stu-id="6ecad-162">The output contains seven columns.</span></span> <span data-ttu-id="6ecad-163">In der Regel sind `IsAnomaly`, `ExpectedValue`, `UpperBoundary` und `LowerBoundary` ausreichend informativ.</span><span class="sxs-lookup"><span data-stu-id="6ecad-163">In most cases, `IsAnomaly`, `ExpectedValue`, `UpperBoundary`, and `LowerBoundary` are informative enough.</span></span> <span data-ttu-id="6ecad-164">Anhand dieser Vektoren können Sie erkennen, ob es sich bei einem Punkt um eine Anomalie handelt. Zudem enthalten diese Vektoren Informationen zum erwarteten Wert des Punkts sowie zum unteren/oberen Grenzbereich des Punkts.</span><span class="sxs-lookup"><span data-stu-id="6ecad-164">They tell you if a point is an anomaly, the expected value of the point and the lower / upper boundary region of the point.</span></span>

5. <span data-ttu-id="6ecad-165">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um den Pfad zu Ihrer Datendatei anzugeben:</span><span class="sxs-lookup"><span data-stu-id="6ecad-165">Add the following code to the line right above the `Main` method to specify the path to your data file:</span></span>

    [!code-csharp[Declare global variables](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a><span data-ttu-id="6ecad-166">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="6ecad-166">Initialize variables in Main</span></span>

1. <span data-ttu-id="6ecad-167">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die Variable `mlContext` zu deklarieren und zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="6ecad-167">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

    [!code-csharp[CreateMLContext](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    <span data-ttu-id="6ecad-168">Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6ecad-168">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="6ecad-169">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="6ecad-169">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="load-the-data"></a><span data-ttu-id="6ecad-170">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="6ecad-170">Load the data</span></span>

<span data-ttu-id="6ecad-171">Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6ecad-171">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="6ecad-172">Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6ecad-172">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="6ecad-173">Daten können aus einer Textdatei oder aus anderen Ressourcen (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6ecad-173">Data can be loaded from a text file or from other sources (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="6ecad-174">Fügen Sie der `Main`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="6ecad-174">Add the following code as the next line of the `Main` method:</span></span>

    [!code-csharp[LoadData](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="6ecad-175">Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest die Datei ein.</span><span class="sxs-lookup"><span data-stu-id="6ecad-175">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="6ecad-176">Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="6ecad-176">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="time-series-anomaly-detection"></a><span data-ttu-id="6ecad-177">Anomalieerkennung in Zeitreihen</span><span class="sxs-lookup"><span data-stu-id="6ecad-177">Time series anomaly detection</span></span>

<span data-ttu-id="6ecad-178">Bei der Erkennung von Anomalien bei Zeitreihen handelt es sich um einen Prozess, bei dem Ausreißer in Zeitreihendaten ermittelt werden. Damit wird auf Eingabezeitreihen hingewiesen, bei denen nicht das erwartete oder ein ungewöhnliches Verhalten aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6ecad-178">Time series anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span> <span data-ttu-id="6ecad-179">Diese Anomalien sind in der Regel Hinweise auf einige relevante Ereignisse in der Problemdomäne: ein Cyberangriff auf Benutzerkonten, Stromausfälle, ein sprunghafter Anstieg von Anforderungen pro Sekunde auf einem Server, Arbeitsspeicherverlust usw.</span><span class="sxs-lookup"><span data-stu-id="6ecad-179">These anomalies are typically indicative of some events of interest in the problem domain: a cyber-attack on user accounts, power outage, bursting RPS on a server, memory leak, etc.</span></span>

<span data-ttu-id="6ecad-180">Zum Auffinden von Anomalien in Zeitreihen sollten Sie zunächst den Zeitraum der Reihe bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6ecad-180">To find anomaly on time series, you should first determine the period of the series.</span></span> <span data-ttu-id="6ecad-181">Anschließend kann die Zeitreihe in Form von `Y = T + S + R` in verschiedene Komponenten zerlegt werden, wobei `Y` der ursprünglichen Reihe, `T` der Trendkomponente, `S` der saisonalen Komponente und `R` der Restkomponente der Reihe entspricht.</span><span class="sxs-lookup"><span data-stu-id="6ecad-181">Then, the time series can be decomposed into several components as `Y = T + S + R`, where `Y` is the original series, `T` is the trend component, `S` is the seasonal component, and `R` is the residual component of the series.</span></span> <span data-ttu-id="6ecad-182">Dieser Schritt wird als [Zerlegung](https://en.wikipedia.org/wiki/Decomposition_of_time_series) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6ecad-182">This step is called [decomposition](https://en.wikipedia.org/wiki/Decomposition_of_time_series).</span></span> <span data-ttu-id="6ecad-183">Abschließend wird zum Auffinden der Anomalien für die Restkomponente eine Erkennung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6ecad-183">Finally, detection is performed on the residual component to find the anomalies.</span></span> <span data-ttu-id="6ecad-184">In ML.NET ist der SR-CNN-Algorithmus ein intelligenter und neuartiger Algorithmus, mit dem Anomalien bei Zeitreihen mittels SR-Methode (Spectral Residual) und Convolutional Neural Network (CNN) erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="6ecad-184">In ML.NET, The SR-CNN algorithm is an advanced and novel algorithm that is based on Spectral Residual (SR) and Convolutional Neural Network(CNN) to detect anomaly on time-series.</span></span> <span data-ttu-id="6ecad-185">Weitere Informationen zu diesem Algorithmus finden Sie unter [Time-Series Anomaly Detection Service at Microsoft](https://arxiv.org/pdf/1906.03821.pdf) (Dienst bei Microsoft zur Erkennung von Anomalien bei Zeitreihen).</span><span class="sxs-lookup"><span data-stu-id="6ecad-185">For more information on this algorithm, see [Time-Series Anomaly Detection Service at Microsoft](https://arxiv.org/pdf/1906.03821.pdf).</span></span>

<span data-ttu-id="6ecad-186">In diesem Tutorial werden Sie sehen, dass diese Verfahren mit zwei Funktionen durchgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="6ecad-186">In this tutorial, you will see that these procedures can be completed using two functions.</span></span>

## <a name="detect-period"></a><span data-ttu-id="6ecad-187">Erkennen eines Zeitraums</span><span class="sxs-lookup"><span data-stu-id="6ecad-187">Detect Period</span></span>

<span data-ttu-id="6ecad-188">Im ersten Schritt wird die Funktion `DetectSeasonality` aufgerufen, um den Zeitraum der Reihe zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6ecad-188">In the first step, we invoke the `DetectSeasonality` function to determine the period of the series.</span></span>

### <a name="create-the-detectperiod-method"></a><span data-ttu-id="6ecad-189">Erstellen der DetectPeriod-Methode</span><span class="sxs-lookup"><span data-stu-id="6ecad-189">Create the DetectPeriod method</span></span>

1. <span data-ttu-id="6ecad-190">Erstellen Sie mit dem folgenden Code die `DetectPeriod`-Methode direkt unterhalb der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="6ecad-190">Create the `DetectPeriod` method, just below the `Main` method, using the following code:</span></span>

    ```csharp
    static void DetectPeriod(MLContext mlContext, IDataView phoneCalls)
    {

    }
    ```

2. <span data-ttu-id="6ecad-191">Verwenden Sie die Funktion <xref:Microsoft.ML.TimeSeriesCatalog.DetectSeasonality%2A> zum Erkennen des Zeitraums.</span><span class="sxs-lookup"><span data-stu-id="6ecad-191">Use the <xref:Microsoft.ML.TimeSeriesCatalog.DetectSeasonality%2A> function to detect period.</span></span> <span data-ttu-id="6ecad-192">Fügen Sie ihn mit dem folgenden Code zur `DetectPeriod`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="6ecad-192">Add it to the `DetectPeriod` method with the following code:</span></span>

    [!code-csharp[DetectSeasonality](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectSeasonality)]

3. <span data-ttu-id="6ecad-193">Zeigen Sie den Wert für den Zeitraum an, indem Sie den unten aufgeführten Code als nächste Codezeile in der `DetectPeriod`-Methode hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="6ecad-193">Display the period value by adding the following as the next line of code in the `DetectPeriod` method:</span></span>

    [!code-csharp[DisplayPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayPeriod)]

4. <span data-ttu-id="6ecad-194">Fügen Sie der `DetectPeriod`-Methode in der `Main`-Methode den folgenden Aufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="6ecad-194">Add the following call to the `DetectPeriod` method in the `Main` method:</span></span>

    [!code-csharp[CallDetectPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectPeriod)]

### <a name="period-detection-results"></a><span data-ttu-id="6ecad-195">Ergebnisse der Zeitraumerkennung</span><span class="sxs-lookup"><span data-stu-id="6ecad-195">Period detection results</span></span>

<span data-ttu-id="6ecad-196">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="6ecad-196">Run the application.</span></span> <span data-ttu-id="6ecad-197">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="6ecad-197">Your results should be similar to the following.</span></span>

```console
Period of the series is: 7.
```

## <a name="detect-anomaly"></a><span data-ttu-id="6ecad-198">Erkennen von Anomalien</span><span class="sxs-lookup"><span data-stu-id="6ecad-198">Detect Anomaly</span></span>

<span data-ttu-id="6ecad-199">In diesem Schritt werden Anomalien mithilfe der <xref:Microsoft.ML.TimeSeriesCatalog.DetectEntireAnomalyBySrCnn%2A>-Methode erkannt.</span><span class="sxs-lookup"><span data-stu-id="6ecad-199">In this step, you use the <xref:Microsoft.ML.TimeSeriesCatalog.DetectEntireAnomalyBySrCnn%2A> method to find anomalies.</span></span>

### <a name="create-the-detectanomaly-method"></a><span data-ttu-id="6ecad-200">Erstellen der DetectAnomaly-Methode</span><span class="sxs-lookup"><span data-stu-id="6ecad-200">Create the DetectAnomaly method</span></span>

1. <span data-ttu-id="6ecad-201">Erstellen Sie mit dem folgenden Code die `DetectAnomaly`-Methode direkt unterhalb der `DetectPeriod`-Methode:</span><span class="sxs-lookup"><span data-stu-id="6ecad-201">Create the `DetectAnomaly` method, just below the `DetectPeriod` method, using the following code:</span></span>

    ```csharp
    static void DetectAnomaly(MLContext mlContext, IDataView phoneCalls, int period)
    {

    }
    ```

2. <span data-ttu-id="6ecad-202">Richten Sie <xref:Microsoft.ML.TimeSeries.SrCnnEntireAnomalyDetectorOptions> mit dem folgenden Code in der `DetectAnomaly`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="6ecad-202">Set up <xref:Microsoft.ML.TimeSeries.SrCnnEntireAnomalyDetectorOptions> in the `DetectAnomaly` method with the following code:</span></span>

    [!code-csharp[SetupSrCnnParameters](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#SetupSrCnnParameters)]

3. <span data-ttu-id="6ecad-203">Erkennen Sie Anomalien mithilfe des SR-CNN-Algorithmus, indem Sie in der `DetectAnomaly`-Methode die folgende Codezeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="6ecad-203">Detect anomaly by SR-CNN algorithm by adding the following line of code in the `DetectAnomaly` method:</span></span>

    [!code-csharp[DetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectAnomaly)]

4. <span data-ttu-id="6ecad-204">Konvertieren Sie die Ansicht der Ausgabedaten zur einfacheren Anzeige mit der [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A)-Methode mit dem folgenden Code in ein stark typisiertes `IEnumerable`-Element:</span><span class="sxs-lookup"><span data-stu-id="6ecad-204">Convert the output data view into a strongly typed `IEnumerable` for easier display using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

    [!code-csharp[CreateEnumerableForResult](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateEnumerableForResult)]

5. <span data-ttu-id="6ecad-205">Erstellen Sie mit dem folgenden Code als nächste Zeile in der `DetectAnomaly`-Methode einen Anzeigeheader:</span><span class="sxs-lookup"><span data-stu-id="6ecad-205">Create a display header with the following code as the next line in the `DetectAnomaly` method:</span></span>

    [!code-csharp[DisplayHeader](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayHeader)]

    <span data-ttu-id="6ecad-206">In den Ergebnissen der Änderungspunkterkennung werden folgende Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6ecad-206">You'll display the following information in your change point detection results:</span></span>

    * <span data-ttu-id="6ecad-207">`Index` entspricht dem Index des jeweiligen Datenpunkts.</span><span class="sxs-lookup"><span data-stu-id="6ecad-207">`Index` is the index of each point.</span></span>
    * <span data-ttu-id="6ecad-208">`Anomaly` entspricht dem Indikator, der angibt, ob der jeweilige Punkt als Anomalie erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="6ecad-208">`Anomaly` is the indicator of whether each point is detected as anomaly.</span></span>
    * <span data-ttu-id="6ecad-209">`ExpectedValue` entspricht dem Schätzwert des jeweiligen Punkts.</span><span class="sxs-lookup"><span data-stu-id="6ecad-209">`ExpectedValue` is the estimated value of each point.</span></span>
    * <span data-ttu-id="6ecad-210">`LowerBoundary` entspricht dem niedrigsten Wert, den ein Punkt annehmen kann, ohne als Anomalie zu gelten.</span><span class="sxs-lookup"><span data-stu-id="6ecad-210">`LowerBoundary` is the lowest value each point can be to be not anomaly.</span></span>
    * <span data-ttu-id="6ecad-211">`UpperBoundary` entspricht dem höchsten Wert, den ein Punkt annehmen kann, ohne als Anomalie zu gelten.</span><span class="sxs-lookup"><span data-stu-id="6ecad-211">`UpperBoundary` is the highest value each point can be to be not anomaly.</span></span>

6. <span data-ttu-id="6ecad-212">Mit dem folgenden Code können Sie `predictions` `IEnumerable` durchlaufen und die Ergebnisse anzeigen:</span><span class="sxs-lookup"><span data-stu-id="6ecad-212">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

    [!code-csharp[DisplayAnomalyDetectionResults](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayAnomalyDetectionResults)]

7. <span data-ttu-id="6ecad-213">Fügen Sie der `DetectAnomaly`-Methode in der `Main`-Methode den folgenden Aufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="6ecad-213">Add the following call to the `DetectAnomaly` method in the `Main` method:</span></span>

    [!code-csharp[CallDetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectAnomaly)]

## <a name="anomaly-detection-results"></a><span data-ttu-id="6ecad-214">Ergebnisse der Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="6ecad-214">Anomaly detection results</span></span>

<span data-ttu-id="6ecad-215">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="6ecad-215">Run the application.</span></span> <span data-ttu-id="6ecad-216">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="6ecad-216">Your results should be similar to the following.</span></span> <span data-ttu-id="6ecad-217">Während der Verarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ecad-217">During processing, messages are displayed.</span></span> <span data-ttu-id="6ecad-218">Möglicherweise werden Warnungen oder Verarbeitungsmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ecad-218">You may see warnings or processing messages.</span></span> <span data-ttu-id="6ecad-219">Einige der Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="6ecad-219">Some messages have been removed from the following results for clarity.</span></span>

```console
Detect period of the series
Period of the series is: 7.
Detect anomaly points in the series
Index   Data    Anomaly AnomalyScore    Mag     ExpectedValue   BoundaryUnit    UpperBoundary   LowerBoundary
0,0,36.841787256739266,41.14206982401966,32.541504689458876
1,0,35.67303618137362,39.97331874865401,31.372753614093227
2,0,34.710132999891826,39.029491313022824,30.390774686760828
3,0,33.44765248883495,37.786086547816545,29.10921842985335
4,0,28.937110922276364,33.25646923540736,24.61775260914537
5,0,5.143895892785781,9.444178460066171,0.843613325505391
6,0,5.163325228419392,9.463607795699783,0.8630426611390014
7,0,36.76414836240396,41.06443092968435,32.46386579512357
8,0,35.77908590657007,40.07936847385046,31.478803339289676
9,0,34.547259536635245,38.847542103915636,30.246976969354854
10,0,33.55193524820608,37.871293561337076,29.23257693507508
11,0,29.091800129624648,33.392082696905035,24.79151756234426
12,0,5.154836630338823,9.455119197619213,0.8545540630584334
13,0,5.234332502492464,9.534615069772855,0.934049935212073
14,0,36.54992549471526,40.85020806199565,32.24964292743487
15,0,35.79526470980883,40.095547277089224,31.494982142528443
16,0,34.34099013096804,38.64127269824843,30.040707563687647
17,0,33.61201516582131,37.9122977331017,29.31173259854092
18,0,29.223563320561812,33.5238458878422,24.923280753281425
19,0,5.170512168851533,9.470794736131923,0.8702296015711433
20,0,5.2614938889462834,9.561776456226674,0.9612113216658926
21,0,36.37103858487317,40.67132115215356,32.07075601759278
22,0,35.813544599026855,40.113827166307246,31.513262031746464
23,0,34.05600492733225,38.356287494612644,29.755722360051863
24,0,33.65828319077884,37.95856575805923,29.358000623498448
25,0,29.381125690882463,33.681408258162854,25.080843123602072
26,0,5.261543539820418,9.561826107100808,0.9612609725400283
27,0,5.4873712582971805,9.787653825577571,1.1870886910167897
28,1,36.504694001629254,40.804976568909645,32.20441143434886  <-- alert is on, detected anomaly
...
```

<span data-ttu-id="6ecad-220">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="6ecad-220">Congratulations!</span></span> <span data-ttu-id="6ecad-221">Sie haben Machine Learning-Modelle zur Erkennung von Zeiträumen und Anomalien in einer periodischen Zeitreihe erstellt.</span><span class="sxs-lookup"><span data-stu-id="6ecad-221">You've now successfully built machine learning models for detecting period and anomaly on a periodical series.</span></span>

<span data-ttu-id="6ecad-222">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="6ecad-222">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection) repository.</span></span>

<span data-ttu-id="6ecad-223">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6ecad-223">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="6ecad-224">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="6ecad-224">Load the data</span></span>
> * <span data-ttu-id="6ecad-225">Erkennen eines Zeitraums bei Zeitreihendaten</span><span class="sxs-lookup"><span data-stu-id="6ecad-225">Detect period on the time series data</span></span>
> * <span data-ttu-id="6ecad-226">Erkennen einer Anomalie bei Zeitreihendaten</span><span class="sxs-lookup"><span data-stu-id="6ecad-226">Detect anomaly on the time series data</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ecad-227">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6ecad-227">Next steps</span></span>

<span data-ttu-id="6ecad-228">Durchsuchen Sie das GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für die Erkennung von Stromverbrauchsanomalien, damit Sie es untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="6ecad-228">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="6ecad-229">dotnet/machinelearning-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="6ecad-229">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
