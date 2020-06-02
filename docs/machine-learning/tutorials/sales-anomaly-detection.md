---
title: 'Tutorial: Erkennen von Anomalien bei Produktverkäufen'
description: Erfahren Sie, wie Sie eine Anwendung zur Anomalieerkennung bei Produktvertriebsdaten erstellen. Dieses Tutorial erstellt mithilfe von C# in Visual Studio 2019 eine .NET Core-Konsolenanwendung.
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 2fc9c552f5a00d59ea2fddcbcfcbd240cf2fc83c
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201992"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a><span data-ttu-id="1d965-104">Tutorial: Erkennen von Anomalien in Produktverkäufen mit ML.NET</span><span class="sxs-lookup"><span data-stu-id="1d965-104">Tutorial: Detect anomalies in product sales with ML.NET</span></span>

<span data-ttu-id="1d965-105">Erfahren Sie, wie Sie eine Anwendung zur Anomalieerkennung bei Produktvertriebsdaten erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d965-105">Learn how to build an anomaly detection application for product sales data.</span></span> <span data-ttu-id="1d965-106">Dieses Tutorial erstellt mithilfe von C# in Visual Studio eine .NET Core-Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="1d965-106">This tutorial creates a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="1d965-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="1d965-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="1d965-108">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="1d965-108">Load the data</span></span>
> * <span data-ttu-id="1d965-109">Erstellen einer Transformation zur Erkennung von Anomaliespitzen</span><span class="sxs-lookup"><span data-stu-id="1d965-109">Create a transform for spike anomaly detection</span></span>
> * <span data-ttu-id="1d965-110">Erkennen von Anomaliespitzen mit der Transformation</span><span class="sxs-lookup"><span data-stu-id="1d965-110">Detect spike anomalies with the transform</span></span>
> * <span data-ttu-id="1d965-111">Erstellen einer Transformation für die Anomalieerkennung bei Änderungspunkten</span><span class="sxs-lookup"><span data-stu-id="1d965-111">Create a transform for change point anomaly detection</span></span>
> * <span data-ttu-id="1d965-112">Erkennen von Änderungspunktanomalien mit der Transformation</span><span class="sxs-lookup"><span data-stu-id="1d965-112">Detect change point anomalies with the transform</span></span>

<span data-ttu-id="1d965-113">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="1d965-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d965-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1d965-114">Prerequisites</span></span>

* <span data-ttu-id="1d965-115">[Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="1d965-115">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="1d965-116">Das Dataset „product-sales.csv“</span><span class="sxs-lookup"><span data-stu-id="1d965-116">The product-sales.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> <span data-ttu-id="1d965-117">Das Datenformat in `product-sales.csv` basiert auf dem Dataset „Shampoo Sales Over a Three Year Period“ von Rob Hyndman, ursprünglich aus dem DataMarket und von der Time Series Data Library (TSDL) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1d965-117">The data format in `product-sales.csv` is based on the dataset “Shampoo Sales Over a Three Year Period” originally sourced from DataMarket and provided by Time Series Data Library (TSDL), created by Rob Hyndman.</span></span>
> <span data-ttu-id="1d965-118">Das Dataset „Shampoo Sales Over a Three Year Period“ ist im Rahmen der DataMarket Default Open License lizenziert.</span><span class="sxs-lookup"><span data-stu-id="1d965-118">“Shampoo Sales Over a Three Year Period” Dataset Licensed Under the DataMarket Default Open License.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="1d965-119">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="1d965-119">Create a console application</span></span>

1. <span data-ttu-id="1d965-120">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „ProductSalesAnomalyDetection“.</span><span class="sxs-lookup"><span data-stu-id="1d965-120">Create a **.NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="1d965-121">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1d965-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="1d965-122">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="1d965-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="1d965-123">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="1d965-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="1d965-124">Wählen Sie als Paketquelle „nuget.org“ aus. Klicken Sie dann auf die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und klicken Sie anschließend auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="1d965-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="1d965-125">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="1d965-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="1d965-126">Wiederholen Sie diese Schritte für **Microsoft.ML.TimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="1d965-126">Repeat these steps for **Microsoft.ML.TimeSeries**.</span></span>

4. <span data-ttu-id="1d965-127">Fügen Sie am Anfang der Datei *Program.cs* die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d965-127">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="1d965-128">Herunterladen der Daten</span><span class="sxs-lookup"><span data-stu-id="1d965-128">Download your data</span></span>

1. <span data-ttu-id="1d965-129">Laden Sie die das Dataset herunter, und speichern Sie es im Ordner *Data*, den Sie vorher erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="1d965-129">Download the dataset and save it to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="1d965-130">Klicken Sie mit der rechten Maustaste auf [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) und anschließend auf „Link speichern unter“ oder „Ziel speichern unter“.</span><span class="sxs-lookup"><span data-stu-id="1d965-130">Right click on [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="1d965-131">Achten Sie darauf, die \*CSV-Datei entweder im Ordner *Data* zu speichern oder sie in den Ordner *Data* zu verschieben, nachdem Sie die \*CSV-Datei an anderer Stelle gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="1d965-131">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="1d965-132">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*CSV Datei, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="1d965-132">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="1d965-133">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="1d965-133">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="1d965-134">Die folgende Tabelle enthält eine Datenvorschau aus Ihrem \*CSV-Datei:</span><span class="sxs-lookup"><span data-stu-id="1d965-134">The following table is a data preview from your \*.csv file:</span></span>

|<span data-ttu-id="1d965-135">Monat</span><span class="sxs-lookup"><span data-stu-id="1d965-135">Month</span></span>  |<span data-ttu-id="1d965-136">ProductSales</span><span class="sxs-lookup"><span data-stu-id="1d965-136">ProductSales</span></span> |
|-------|-------------|
|<span data-ttu-id="1d965-137">1-Jan</span><span class="sxs-lookup"><span data-stu-id="1d965-137">1-Jan</span></span>  |    <span data-ttu-id="1d965-138">271</span><span class="sxs-lookup"><span data-stu-id="1d965-138">271</span></span>      |
|<span data-ttu-id="1d965-139">2-Jan</span><span class="sxs-lookup"><span data-stu-id="1d965-139">2-Jan</span></span>  |    <span data-ttu-id="1d965-140">150,9</span><span class="sxs-lookup"><span data-stu-id="1d965-140">150.9</span></span>    |
|<span data-ttu-id="1d965-141">.....</span><span class="sxs-lookup"><span data-stu-id="1d965-141">.....</span></span>  |    <span data-ttu-id="1d965-142">.....</span><span class="sxs-lookup"><span data-stu-id="1d965-142">.....</span></span>    |
|<span data-ttu-id="1d965-143">1-Feb</span><span class="sxs-lookup"><span data-stu-id="1d965-143">1-Feb</span></span>  |    <span data-ttu-id="1d965-144">199,3</span><span class="sxs-lookup"><span data-stu-id="1d965-144">199.3</span></span>    |
|<span data-ttu-id="1d965-145">.....</span><span class="sxs-lookup"><span data-stu-id="1d965-145">.....</span></span>  |    <span data-ttu-id="1d965-146">.....</span><span class="sxs-lookup"><span data-stu-id="1d965-146">.....</span></span>    |

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="1d965-147">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="1d965-147">Create classes and define paths</span></span>

<span data-ttu-id="1d965-148">Als Nächstes definieren Sie Ihre Datenstruktur der Eingabe- und Vorhersageklasse.</span><span class="sxs-lookup"><span data-stu-id="1d965-148">Next, define your input and prediction class data structures.</span></span>

<span data-ttu-id="1d965-149">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d965-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="1d965-150">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Hinzufügen > Neues Element**.</span><span class="sxs-lookup"><span data-stu-id="1d965-150">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="1d965-151">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in*ProductSalesData.cs*.</span><span class="sxs-lookup"><span data-stu-id="1d965-151">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *ProductSalesData.cs*.</span></span> <span data-ttu-id="1d965-152">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1d965-152">Then, select the **Add** button.</span></span>

   <span data-ttu-id="1d965-153">Die Datei *ProductSalesData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1d965-153">The *ProductSalesData.cs* file opens in the code editor.</span></span>

3. <span data-ttu-id="1d965-154">Fügen Sie die folgende `using`-Anweisung am Anfang der *ProductSalesData.cs*-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d965-154">Add the following `using` statement to the top of *ProductSalesData.cs*:</span></span>

   ```csharp
   using Microsoft.ML.Data;
   ```

4. <span data-ttu-id="1d965-155">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *ProductSalesData.cs* den folgenden Code mit den beiden Klassen `ProductSalesData` und `ProductSalesPrediction` hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d965-155">Remove the existing class definition and add the following code, which has two classes `ProductSalesData` and `ProductSalesPrediction`, to the *ProductSalesData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/ProductSalesData.cs#DeclareTypes "Declare data record types")]

    <span data-ttu-id="1d965-156">`ProductSalesData` ist eine Klasse für Eingabedaten.</span><span class="sxs-lookup"><span data-stu-id="1d965-156">`ProductSalesData` specifies an input data class.</span></span> <span data-ttu-id="1d965-157">Das [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29)-Attribut legt fest, welche Spalten (durch Angabe des Spaltenindex) im Dataset geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1d965-157">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span>

    <span data-ttu-id="1d965-158">`ProductSalesPrediction` gibt die Vorhersagedatenklasse an.</span><span class="sxs-lookup"><span data-stu-id="1d965-158">`ProductSalesPrediction` specifies the prediction data class.</span></span> <span data-ttu-id="1d965-159">Zur Anomalieerkennung besteht die Vorhersage aus einer Warnung, die angibt, ob eine Anomalie, eine Rohbewertung und ein Signifikanzwert (p-value; P-Wert) vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1d965-159">For anomaly detection, the prediction consists of an alert to indicate whether there is an anomaly, a raw score, and p-value.</span></span> <span data-ttu-id="1d965-160">Je näher der Signifikanzwert an 0 ist, desto größer ist die Wahrscheinlichkeit einer Anomalie.</span><span class="sxs-lookup"><span data-stu-id="1d965-160">The closer the p-value is to 0, the more likely an anomaly has occurred.</span></span>

5. <span data-ttu-id="1d965-161">Erstellen Sie zwei globale Felder zum Speichern des gerade heruntergeladenen Datasetdateipfads und des gespeicherten Modelldateipfads:</span><span class="sxs-lookup"><span data-stu-id="1d965-161">Create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

    * <span data-ttu-id="1d965-162">`_dataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1d965-162">`_dataPath` has the path to the dataset used to train the model.</span></span>
    * <span data-ttu-id="1d965-163">`_docsize` enthält die Anzahl der Datensätze in der Datendatei.</span><span class="sxs-lookup"><span data-stu-id="1d965-163">`_docsize` has the number of records in dataset file.</span></span> <span data-ttu-id="1d965-164">Sie verwenden `_docSize` zum Berechnen von `pvalueHistoryLength`.</span><span class="sxs-lookup"><span data-stu-id="1d965-164">You'll use `_docSize` to calculate `pvalueHistoryLength`.</span></span>

6. <span data-ttu-id="1d965-165">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:</span><span class="sxs-lookup"><span data-stu-id="1d965-165">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

    [!code-csharp[Declare global variables](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a><span data-ttu-id="1d965-166">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="1d965-166">Initialize variables in Main</span></span>

1. <span data-ttu-id="1d965-167">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die Variable `mlContext` zu deklarieren und zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="1d965-167">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    <span data-ttu-id="1d965-168">Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1d965-168">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="1d965-169">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="1d965-169">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="load-the-data"></a><span data-ttu-id="1d965-170">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="1d965-170">Load the data</span></span>

<span data-ttu-id="1d965-171">Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1d965-171">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="1d965-172">Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1d965-172">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="1d965-173">Daten können aus einer Textdatei oder aus anderen Ressourcen (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1d965-173">Data can be loaded from a text file or from other sources (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="1d965-174">Fügen Sie der `Main()`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d965-174">Add the following code as the next line of the `Main()` method:</span></span>

    [!code-csharp[LoadData](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="1d965-175">Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest die Datei ein.</span><span class="sxs-lookup"><span data-stu-id="1d965-175">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="1d965-176">Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="1d965-176">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="time-series-anomaly-detection"></a><span data-ttu-id="1d965-177">Anomalieerkennung in Zeitreihen</span><span class="sxs-lookup"><span data-stu-id="1d965-177">Time series anomaly detection</span></span>

<span data-ttu-id="1d965-178">Die Anomalieerkennung zeigt unerwartete oder ungewöhnliche Ereignisse oder Verhaltensweisen an.</span><span class="sxs-lookup"><span data-stu-id="1d965-178">Anomaly detection flags unexpected or unusual events or behaviors.</span></span> <span data-ttu-id="1d965-179">Sie erhalten Hinweise darauf, wo Sie nach Problemen schauen müssen, und können die Frage beantworten, ob das Ereignis oder Verhalten ungewöhnlich ist.</span><span class="sxs-lookup"><span data-stu-id="1d965-179">It gives clues where to look for problems and helps you answer the question "Is this weird?".</span></span>

![Beispiel der Anomalieerkennung „Ist das ungewöhnlich“](./media/sales-anomaly-detection/time-series-anomaly-detection.png)

<span data-ttu-id="1d965-181">Die Anomalieerkennung ist ein Prozess, bei dem Ausreißer in Zeitreihendaten ermittelt. Damit wird auf Eingabezeitreihen hingewiesen, bei denen nicht das erwartete oder ein ungewöhnliches Verhalten aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1d965-181">Anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span>

<span data-ttu-id="1d965-182">Die Anomalieerkennung kann auf viele Weisen nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="1d965-182">Anomaly detection can be useful in lots of ways.</span></span> <span data-ttu-id="1d965-183">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1d965-183">For instance:</span></span>

<span data-ttu-id="1d965-184">Wenn Sie ein Auto besitzen, möchten Sie vielleicht wissen: Ist diese Ölstandsanzeige normal oder habe ich ein Leck?</span><span class="sxs-lookup"><span data-stu-id="1d965-184">If you have a car, you might want to know: Is this oil gauge reading normal, or do I have a leak?</span></span>
<span data-ttu-id="1d965-185">Wenn Sie den Energieverbrauch überwachen, möchten Sie vielleicht wissen: Gibt es einen Stromausfall?</span><span class="sxs-lookup"><span data-stu-id="1d965-185">If you're monitoring power consumption, you’d want to know: Is there an outage?</span></span>

<span data-ttu-id="1d965-186">Es können zwei Arten von Zeitreihenanomalien erkannt werden:</span><span class="sxs-lookup"><span data-stu-id="1d965-186">There are two types of time series anomalies that can be detected:</span></span>

* <span data-ttu-id="1d965-187">**Spitzen** zeigen temporäre Häufungen von anomalem Verhalten im System an.</span><span class="sxs-lookup"><span data-stu-id="1d965-187">**Spikes** indicate temporary bursts of anomalous behavior in the system.</span></span>

* <span data-ttu-id="1d965-188">**Änderungspunkte** zeigen den Beginn anhaltender Änderungen im Zeitverlauf im System an.</span><span class="sxs-lookup"><span data-stu-id="1d965-188">**Change points** indicate the beginning of persistent changes over time in the system.</span></span>

<span data-ttu-id="1d965-189">In ML.NET eignen sich die Algorithmen „IID Spike Detection“ oder „IID Change point Detection“ für [unabhängige und identisch verteilte Datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span><span class="sxs-lookup"><span data-stu-id="1d965-189">In ML.NET, The IID Spike Detection or IID Change point Detection algorithms are suited for [independent and identically distributed datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span></span>

<span data-ttu-id="1d965-190">Im Gegensatz zu den Modellen in den anderen Tutorials werden die Transformationen für die Zeitreihenanomalieerkennung direkt auf Eingabedaten angewendet.</span><span class="sxs-lookup"><span data-stu-id="1d965-190">Unlike the models in the other tutorials, the time series anomaly detector transforms operate directly on input data.</span></span> <span data-ttu-id="1d965-191">Die `IEstimator.Fit()`-Methode benötigt keine Trainingsdaten, um die Transformation zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="1d965-191">The `IEstimator.Fit()` method does not need training data to produce the transform.</span></span> <span data-ttu-id="1d965-192">Sie benötigt jedoch das Datenschema, das aus einer Datenansicht bereitgestellt wird, die aus einer leeren Liste von `ProductSalesData` generiert wird.</span><span class="sxs-lookup"><span data-stu-id="1d965-192">It does need the data schema though, which is provided by a data view generated from an empty list of `ProductSalesData`.</span></span>

<span data-ttu-id="1d965-193">Sie analysieren die gleichen Produktvertriebsdaten, um Spitzen und Änderungspunkte zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="1d965-193">You'll analyze the same product sales data to detect spikes and change points.</span></span> <span data-ttu-id="1d965-194">Der Prozess zum Erstellen und Trainieren eines Modells ist für die Erkennung von Spitzen und Änderungspunkten gleich; der Hauptunterschied besteht in dem verwendeten spezifischen Erkennungsalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="1d965-194">The building and training model process is the same for spike detection and change point detection; the main difference is the specific detection algorithm used.</span></span>

## <a name="spike-detection"></a><span data-ttu-id="1d965-195">Spitzenerkennung</span><span class="sxs-lookup"><span data-stu-id="1d965-195">Spike detection</span></span>

<span data-ttu-id="1d965-196">Das Ziel der Spitzenerkennung ist es, plötzliche, aber temporäre Häufungen zu identifizieren, die sich signifikant von der Mehrzahl der Zeitreihen-Datenwerte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1d965-196">The goal of spike detection is to identify sudden yet temporary bursts that significantly differ from the majority of the time series data values.</span></span> <span data-ttu-id="1d965-197">Es ist wichtig, diese verdächtigen seltenen Elemente, Ereignisse oder Beobachtungen rechtzeitig zu erkennen, um sie zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="1d965-197">It's important to detect these suspicious rare items, events, or observations in a timely manner to be minimized.</span></span> <span data-ttu-id="1d965-198">Der folgende Ansatz kann zur Erkennung einer Vielzahl von Anomalien verwendet werden: z.B. Ausfälle, Cyberangriffe oder virale Webinhalte.</span><span class="sxs-lookup"><span data-stu-id="1d965-198">The following approach can be used to detect a variety of anomalies such as: outages, cyber-attacks, or viral web content.</span></span> <span data-ttu-id="1d965-199">Das folgende Bild zeigt ein Beispiel für Spitzen in einem Zeitreihen-Dataset:</span><span class="sxs-lookup"><span data-stu-id="1d965-199">The following image is an example of spikes in a time series dataset:</span></span>

![Screenshot: zwei ermittelte Spitzen](./media/sales-anomaly-detection/two-spike-detections.png)

### <a name="add-the-createemptydataview-method"></a><span data-ttu-id="1d965-201">Hinzufügen der CreateEmptyDataView()-Methode</span><span class="sxs-lookup"><span data-stu-id="1d965-201">Add the CreateEmptyDataView() method</span></span>

<span data-ttu-id="1d965-202">Fügen Sie `Program.cs` zur folgenden Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d965-202">Add the following method to `Program.cs`:</span></span>

[!code-csharp[CreateEmptyDataView](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateEmptyDataView)]

<span data-ttu-id="1d965-203">Die Methode `CreateEmptyDataView()` erzeugt ein leeres Datenansichtsobjekt mit dem korrekten Schema, das für die Methode `IEstimator.Fit()` als Eingabe verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1d965-203">The `CreateEmptyDataView()` produces an empty data view object with the correct schema to be used as input to the `IEstimator.Fit()` method.</span></span>

### <a name="create-the-detectspike-method"></a><span data-ttu-id="1d965-204">Erstellen der DetectSpike()-Methode</span><span class="sxs-lookup"><span data-stu-id="1d965-204">Create the DetectSpike() method</span></span>

<span data-ttu-id="1d965-205">Die `DetectSpike()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="1d965-205">The `DetectSpike()` method:</span></span>

* <span data-ttu-id="1d965-206">erstellt die Transformation aus der Schätzung</span><span class="sxs-lookup"><span data-stu-id="1d965-206">Creates the transform from the estimator.</span></span>
* <span data-ttu-id="1d965-207">Erkennen von Spitzen basierend auf historischen Vertriebsdaten.</span><span class="sxs-lookup"><span data-stu-id="1d965-207">Detects spikes based on historical sales data.</span></span>
* <span data-ttu-id="1d965-208">Anzeigen der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="1d965-208">Displays the results.</span></span>

1. <span data-ttu-id="1d965-209">Erstellen Sie die `DetectSpike()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="1d965-209">Create the `DetectSpike()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. <span data-ttu-id="1d965-210">Verwenden Sie [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator), um das Modell zum Erkennen von Spitzen zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="1d965-210">Use the [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) to train the model for spike detection.</span></span> <span data-ttu-id="1d965-211">Fügen Sie ihn mit dem folgenden Code zur `DetectSpike()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d965-211">Add it to the `DetectSpike()` method with the following code:</span></span>

    [!code-csharp[AddSpikeTrainer](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#AddSpikeTrainer)]

1. <span data-ttu-id="1d965-212">Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `DetectSpike()`-Methode ein, um die Spitzenerkennungstransformation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d965-212">Create the spike detection transform by adding the following as the next line of code in the `DetectSpike()` method:</span></span>

    [!code-csharp[TrainModel1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TrainModel1)]

1. <span data-ttu-id="1d965-213">Fügen Sie die folgende Codezeile hinzu, um die `productSales`-Daten als nächste Zeile in der `DetectSpike()`-Methode zu transformieren:</span><span class="sxs-lookup"><span data-stu-id="1d965-213">Add the following line of code to transform the `productSales` data as the next line in the `DetectSpike()` method:</span></span>

    [!code-csharp[TransformData1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TransformData1)]

    <span data-ttu-id="1d965-214">Der vorherige Code verwendet die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere Eingabezeilen eines Datasets.</span><span class="sxs-lookup"><span data-stu-id="1d965-214">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple input rows of a dataset.</span></span>

1. <span data-ttu-id="1d965-215">Konvertieren Sie Ihre `transformedData` mit der [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A)-Methode mit dem folgenden Code in ein stark typisiertes `IEnumerable`-Element zur einfacheren Anzeige:</span><span class="sxs-lookup"><span data-stu-id="1d965-215">Convert your `transformedData` into a strongly typed `IEnumerable` for easier display using the [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

    [!code-csharp[CreateEnumerable1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateEnumerable1)]

1. <span data-ttu-id="1d965-216">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Kopfzeile:</span><span class="sxs-lookup"><span data-stu-id="1d965-216">Create a display header line using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

    [!code-csharp[DisplayHeader1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayHeader1)]

    <span data-ttu-id="1d965-217">In den Ergebnissen der Spitzenerkennung werden folgende Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d965-217">You'll display the following information in your spike detection results:</span></span>

    * <span data-ttu-id="1d965-218">`Alert` gibt eine Spitzenwarnung für einen bestimmten Datenpunkt an.</span><span class="sxs-lookup"><span data-stu-id="1d965-218">`Alert` indicates a spike alert for a given data point.</span></span>
    * <span data-ttu-id="1d965-219">`Score` ist der `ProductSales`-Wert für einen bestimmten Datenpunkt im Dataset.</span><span class="sxs-lookup"><span data-stu-id="1d965-219">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
    * <span data-ttu-id="1d965-220">`P-Value` Das „P“ steht für „Probability“ (Wahrscheinlichkeit).</span><span class="sxs-lookup"><span data-stu-id="1d965-220">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="1d965-221">Je näher der Signifikanzwert an 0 ist, desto größer ist die Wahrscheinlichkeit, dass der Datenpunkt eine Anomalie darstellt.</span><span class="sxs-lookup"><span data-stu-id="1d965-221">The closer the p-value is to 0, the more likely the data point is an anomaly.</span></span>

1. <span data-ttu-id="1d965-222">Verwenden Sie den folgenden Code, um `predictions` `IEnumerable` zu durchlaufen und die Ergebnisse anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="1d965-222">Use the following code to iterate through the `predictions` `IEnumerable` and display the results:</span></span>

    [!code-csharp[DisplayResults1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayResults1)]

1. <span data-ttu-id="1d965-223">Fügen Sie den Aufruf der `DetectSpike()`-Methode in der `Main()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d965-223">Add the call to the `DetectSpike()`method in the `Main()` method:</span></span>

    [!code-csharp[CallDetectSpike](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CallDetectSpike)]

## <a name="spike-detection-results"></a><span data-ttu-id="1d965-224">Ergebnisse der Spitzenerkennung</span><span class="sxs-lookup"><span data-stu-id="1d965-224">Spike detection results</span></span>

<span data-ttu-id="1d965-225">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="1d965-225">Your results should be similar to the following.</span></span> <span data-ttu-id="1d965-226">Während der Verarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d965-226">During processing, messages are displayed.</span></span> <span data-ttu-id="1d965-227">Sie können Warnungen oder Verarbeitungsmeldungen sehen.</span><span class="sxs-lookup"><span data-stu-id="1d965-227">You may see warnings, or processing messages.</span></span> <span data-ttu-id="1d965-228">Einige dieser Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="1d965-228">Some of the messages have been removed from the following results for clarity.</span></span>

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a><span data-ttu-id="1d965-229">Erkennen von Änderungspunkten</span><span class="sxs-lookup"><span data-stu-id="1d965-229">Change point detection</span></span>

<span data-ttu-id="1d965-230">`Change points` sind anhaltende Änderungen in der Verteilung der Werte in einem Zeitreihen-Ereignisstrom, wie Niveauänderungen und Trends.</span><span class="sxs-lookup"><span data-stu-id="1d965-230">`Change points` are persistent changes in a time series event stream distribution of values, like level changes and trends.</span></span> <span data-ttu-id="1d965-231">Diese anhaltenden Änderungen dauern wesentlich länger als `spikes` und könnten auf katastrophale Ereignisse hinweisen.</span><span class="sxs-lookup"><span data-stu-id="1d965-231">These persistent changes last much longer than `spikes` and could indicate catastrophic event(s).</span></span> <span data-ttu-id="1d965-232">`Change points` sind in der Regel nicht mit bloßem Auge erkennbar, können aber mit Ansätzen wie beispielsweise der folgenden Methode in Ihren Daten festgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1d965-232">`Change points` are not usually visible to the naked eye, but can be detected in your data using approaches such as in the following method.</span></span>  <span data-ttu-id="1d965-233">Das folgende Bild ist ein Beispiel für eine Änderungspunkterkennung:</span><span class="sxs-lookup"><span data-stu-id="1d965-233">The following image is an example of a change point detection:</span></span>

![Screenshot: Änderungspunkterkennung](./media/sales-anomaly-detection/change-point-detection.png)

### <a name="create-the-detectchangepoint-method"></a><span data-ttu-id="1d965-235">Erstellen der DetectChangepoint()-Methode</span><span class="sxs-lookup"><span data-stu-id="1d965-235">Create the DetectChangepoint() method</span></span>

<span data-ttu-id="1d965-236">Die `DetectChangepoint()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="1d965-236">The `DetectChangepoint()` method executes the following tasks:</span></span>

* <span data-ttu-id="1d965-237">erstellt die Transformation aus der Schätzung</span><span class="sxs-lookup"><span data-stu-id="1d965-237">Creates the transform from the estimator.</span></span>
* <span data-ttu-id="1d965-238">Erkennen von Änderungspunkten basierend auf historischen Vertriebsdaten.</span><span class="sxs-lookup"><span data-stu-id="1d965-238">Detects change points based on historical sales data.</span></span>
* <span data-ttu-id="1d965-239">Anzeigen der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="1d965-239">Displays the results.</span></span>

1. <span data-ttu-id="1d965-240">Erstellen Sie die `DetectChangepoint()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="1d965-240">Create the `DetectChangepoint()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. <span data-ttu-id="1d965-241">Erstellen Sie den [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) in der `DetectChangepoint()`-Methode mit folgendem Code:</span><span class="sxs-lookup"><span data-stu-id="1d965-241">Create the [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) in the `DetectChangepoint()` method with the following code:</span></span>

    [!code-csharp[AddChangepointTrainer](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#AddChangepointTrainer)]

1. <span data-ttu-id="1d965-242">Erstellen Sie wie zuvor die Transformation aus der Schätzung, indem Sie die folgende Codezeile in der `DetectChangePoint()`-Methode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1d965-242">As you did previously, create the transform from the estimator by adding the following line of code in the `DetectChangePoint()` method:</span></span>

    [!code-csharp[TrainModel2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TrainModel2)]

1. <span data-ttu-id="1d965-243">Verwenden Sie die `Transform()`-Methode, um die Daten zu transformieren, indem Sie den folgenden Code zu `DetectChangePoint()` hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="1d965-243">Use the `Transform()` method to transform the data by adding the following code to `DetectChangePoint()`:</span></span>

    [!code-csharp[TransformData2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TransformData2)]

1. <span data-ttu-id="1d965-244">Konvertieren Sie wie bereits zuvor Ihre `transformedData` mit der `CreateEnumerable()`-Methode mit dem folgenden Code in ein stark typisiertes `IEnumerable`-Element zur einfacheren Anzeige:</span><span class="sxs-lookup"><span data-stu-id="1d965-244">As you did previously, convert your `transformedData` into a strongly typed `IEnumerable` for easier display using the `CreateEnumerable()`method with the following code:</span></span>

    [!code-csharp[CreateEnumerable2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateEnumerable2)]

1. <span data-ttu-id="1d965-245">Erstellen Sie mit dem folgenden Code als nächste Zeile in der `DetectChangePoint()`-Methode einen Anzeigeheader:</span><span class="sxs-lookup"><span data-stu-id="1d965-245">Create a display header with the following code as the next line in the `DetectChangePoint()` method:</span></span>

    [!code-csharp[DisplayHeader2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayHeader2)]

    <span data-ttu-id="1d965-246">In den Ergebnissen der Änderungspunkterkennung werden folgende Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d965-246">You'll display the following information in your change point detection results:</span></span>

    * <span data-ttu-id="1d965-247">`Alert` gibt eine Änderungspunktwarnung für einen bestimmten Datenpunkt an.</span><span class="sxs-lookup"><span data-stu-id="1d965-247">`Alert` indicates a change point alert for a given data point.</span></span>
    * <span data-ttu-id="1d965-248">`Score` ist der `ProductSales`-Wert für einen bestimmten Datenpunkt im Dataset.</span><span class="sxs-lookup"><span data-stu-id="1d965-248">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
    * <span data-ttu-id="1d965-249">`P-Value` Das „P“ steht für „Probability“ (Wahrscheinlichkeit).</span><span class="sxs-lookup"><span data-stu-id="1d965-249">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="1d965-250">Je näher der Signifikanzwert an 0 ist, desto größer ist die Wahrscheinlichkeit, dass der Datenpunkt eine Anomalie darstellt.</span><span class="sxs-lookup"><span data-stu-id="1d965-250">The closer the P-value is to 0, the more likely the data point is an anomaly.</span></span>
    * <span data-ttu-id="1d965-251">`Martingale value` wird verwendet, um basierend auf der Reihenfolge der P-Werte zu bestimmen, wie „ungewöhnlich ein Datenpunkt ist.</span><span class="sxs-lookup"><span data-stu-id="1d965-251">`Martingale value` is used to identify how "weird" a data point is, based on the sequence of P-values.</span></span>

1. <span data-ttu-id="1d965-252">Mit dem folgenden Code können Sie `predictions` `IEnumerable` durchlaufen und die Ergebnisse anzeigen:</span><span class="sxs-lookup"><span data-stu-id="1d965-252">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

    [!code-csharp[DisplayResults2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayResults2)]

1. <span data-ttu-id="1d965-253">Fügen Sie den folgenden Aufruf der `DetectChangepoint()`-Methode in der `Main()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="1d965-253">Add the following call to the `DetectChangepoint()`method in the `Main()` method:</span></span>

    [!code-csharp[CallDetectChangepoint](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CallDetectChangepoint)]

## <a name="change-point-detection-results"></a><span data-ttu-id="1d965-254">Ergebnisse der Änderungspunkterkennung</span><span class="sxs-lookup"><span data-stu-id="1d965-254">Change point detection results</span></span>

<span data-ttu-id="1d965-255">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="1d965-255">Your results should be similar to the following.</span></span> <span data-ttu-id="1d965-256">Während der Verarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d965-256">During processing, messages are displayed.</span></span> <span data-ttu-id="1d965-257">Sie können Warnungen oder Verarbeitungsmeldungen sehen.</span><span class="sxs-lookup"><span data-stu-id="1d965-257">You may see warnings, or processing messages.</span></span> <span data-ttu-id="1d965-258">Einige der Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="1d965-258">Some messages have been removed from the following results for clarity.</span></span>

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

<span data-ttu-id="1d965-259">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="1d965-259">Congratulations!</span></span> <span data-ttu-id="1d965-260">Sie haben jetzt erfolgreich Machine Learning-Modelle zur Erkennung von Spitzen und Änderungspunktanomalien in Vertriebsdaten erstellt.</span><span class="sxs-lookup"><span data-stu-id="1d965-260">You've now successfully built machine learning models for detecting spikes and change point anomalies in sales data.</span></span>

<span data-ttu-id="1d965-261">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="1d965-261">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

<span data-ttu-id="1d965-262">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="1d965-262">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="1d965-263">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="1d965-263">Load the data</span></span>
> * <span data-ttu-id="1d965-264">Trainieren des Modells zur Erkennung von Anomaliespitzen</span><span class="sxs-lookup"><span data-stu-id="1d965-264">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="1d965-265">Erkennen von Anomaliespitzen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="1d965-265">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="1d965-266">Trainieren des Modells zur Erkennung einer Änderungspunktanomalie</span><span class="sxs-lookup"><span data-stu-id="1d965-266">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="1d965-267">Erkennen von Änderungspunktanomalien mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="1d965-267">Detect change point anomalies with the trained mode</span></span>

## <a name="next-steps"></a><span data-ttu-id="1d965-268">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1d965-268">Next steps</span></span>

<span data-ttu-id="1d965-269">Durchsuchen Sie das GitHub-Repository für Machine Learning-Beispiele nach einem Beispiel für die Erkennung von Stromverbrauchsanomalien, damit Sie es untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="1d965-269">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="1d965-270">dotnet/machinelearning-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="1d965-270">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
