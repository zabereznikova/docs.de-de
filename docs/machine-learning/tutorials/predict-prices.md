---
title: 'Tutorial: Vorhersagen von Preisen per Regression'
description: In diesem Tutorial wird veranschaulicht, wie mit ML.NET ein Regressionsmodell für die Vorhersage von Preisen für Taxifahrten in New York City erstellt wird.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: e4014dbdfb81af65c35d2f7693ef2c57885303ff
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711622"
---
# <a name="tutorial-predict-prices-using-regression-with-mlnet"></a><span data-ttu-id="6e48d-103">Tutorial: Vorhersagen von Preisen per Regression mit ML.NET</span><span class="sxs-lookup"><span data-stu-id="6e48d-103">Tutorial: Predict prices using regression with ML.NET</span></span>

<span data-ttu-id="6e48d-104">In diesem Tutorial wird veranschaulicht, wie mit ML.NET ein [Regressionsmodell](../resources/glossary.md#regression) für die Vorhersage von Preisen für Taxifahrten in New York City erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6e48d-104">This tutorial illustrates how to build a [regression model](../resources/glossary.md#regression) using ML.NET to predict prices, specifically, New York City taxi fares.</span></span>

<span data-ttu-id="6e48d-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6e48d-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="6e48d-106">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="6e48d-106">Prepare and understand the data</span></span>
> * <span data-ttu-id="6e48d-107">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="6e48d-107">Load and transform the data</span></span>
> * <span data-ttu-id="6e48d-108">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="6e48d-108">Choose a learning algorithm</span></span>
> * <span data-ttu-id="6e48d-109">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="6e48d-109">Train the model</span></span>
> * <span data-ttu-id="6e48d-110">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="6e48d-110">Evaluate the model</span></span>
> * <span data-ttu-id="6e48d-111">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="6e48d-111">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e48d-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6e48d-112">Prerequisites</span></span>

* <span data-ttu-id="6e48d-113">[Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="6e48d-113">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="6e48d-114">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="6e48d-114">Create a console application</span></span>

1. <span data-ttu-id="6e48d-115">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TaxiFarePrediction“.</span><span class="sxs-lookup"><span data-stu-id="6e48d-115">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="6e48d-116">Erstellen Sie in Ihrem Projekt ein Verzeichnis mit dem Namen *Data*, um das Dataset und die Modelldateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6e48d-116">Create a directory named *Data* in your project to store the data set and model files.</span></span>

1. <span data-ttu-id="6e48d-117">Installieren Sie das NuGet-Paket **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="6e48d-117">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="6e48d-118">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="6e48d-118">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="6e48d-119">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="6e48d-119">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="6e48d-120">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-120">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="6e48d-121">Gehen Sie für das NuGet-Paket **Microsoft.ML.FastTreee** genauso vor.</span><span class="sxs-lookup"><span data-stu-id="6e48d-121">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="6e48d-122">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="6e48d-122">Prepare and understand the data</span></span>

1. <span data-ttu-id="6e48d-123">Laden Sie die Datasets [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) und [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*.</span><span class="sxs-lookup"><span data-stu-id="6e48d-123">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="6e48d-124">Diese Datasets werden zum Trainieren des Machine Learning-Modells und zum anschließenden Auswerten der Genauigkeit des Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e48d-124">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="6e48d-125">Diese Datasets stammen ursprünglich aus dem [Dataset „NYC TLC Taxi Trip“](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).</span><span class="sxs-lookup"><span data-stu-id="6e48d-125">These data sets are originally from the [NYC TLC Taxi Trip data set](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).</span></span>

1. <span data-ttu-id="6e48d-126">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die „\*.csv“-Dateien, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="6e48d-126">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="6e48d-127">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="6e48d-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="6e48d-128">Öffnen Sie das Dataset **taxi-fare-train.csv**, und sehen Sie sich die Spaltenheader in der ersten Zeile an.</span><span class="sxs-lookup"><span data-stu-id="6e48d-128">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="6e48d-129">Sehen Sie sich jede der Spalten an.</span><span class="sxs-lookup"><span data-stu-id="6e48d-129">Take a look at each of the columns.</span></span> <span data-ttu-id="6e48d-130">Machen Sie sich mit den Daten vertraut, und entscheiden Sie, welche Spalten **Features** sind, und welche Spalte die **Bezeichnung** ist.</span><span class="sxs-lookup"><span data-stu-id="6e48d-130">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="6e48d-131">`label` ist die Spalte, die vorhergesagt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e48d-131">The `label` is the column you want to predict.</span></span> <span data-ttu-id="6e48d-132">Die identifizierten `Features` sind die Eingaben, die Sie für das Modell zum Vorhersagen von `Label` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-132">The identified `Features`are the inputs you give the model to predict the `Label`.</span></span>

<span data-ttu-id="6e48d-133">Das angegebene Dataset enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="6e48d-133">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="6e48d-134">**vendor_id:** Die ID des Taxiunternehmers ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="6e48d-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="6e48d-135">**rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="6e48d-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="6e48d-136">**passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="6e48d-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="6e48d-137">**trip_time_in_secs:** Die Dauer der Fahrt.</span><span class="sxs-lookup"><span data-stu-id="6e48d-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="6e48d-138">Der Fahrpreis soll vorhergesagt werden, bevor die Fahrt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6e48d-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="6e48d-139">Zu diesem Zeitpunkt wissen Sie noch nicht, wie lange die Fahrt dauert.</span><span class="sxs-lookup"><span data-stu-id="6e48d-139">At that moment, you don't know how long the trip would take.</span></span> <span data-ttu-id="6e48d-140">Deshalb ist die Fahrtzeit kein Feature, und Sie müssen diese Spalte aus dem Modell ausschließen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="6e48d-141">**trip_distance:** Die Fahrtstrecke ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="6e48d-141">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="6e48d-142">**payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="6e48d-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="6e48d-143">**fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="6e48d-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="6e48d-144">Erstellen von Datenklassen</span><span class="sxs-lookup"><span data-stu-id="6e48d-144">Create data classes</span></span>

<span data-ttu-id="6e48d-145">Erstellen Sie Klassen für die Eingabedaten und die Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="6e48d-145">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="6e48d-146">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="6e48d-146">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="6e48d-147">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="6e48d-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="6e48d-148">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e48d-148">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="6e48d-149">Fügen Sie der Formularklasse die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-149">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="6e48d-150">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `TaxiTrip` und `TaxiTripFarePrediction` der Datei *TaxiTrip.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-150">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="6e48d-151">`TaxiTrip` ist die Eingabedatenklasse und verfügt über Definitionen für jede der Datasetspalten.</span><span class="sxs-lookup"><span data-stu-id="6e48d-151">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="6e48d-152">Verwenden Sie das <xref:Microsoft.ML.Data.LoadColumnAttribute>-Attribut, um die Indizes der Quellspalten im Dataset festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-152">Use the <xref:Microsoft.ML.Data.LoadColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="6e48d-153">Die Klasse `TaxiTripFarePrediction` stellt die vorhergesagten Ergebnisse dar.</span><span class="sxs-lookup"><span data-stu-id="6e48d-153">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="6e48d-154">Sie verfügt über ein einzelnes Feld für einen Gleitkommawert (`FareAmount`) mit einem angewendeten `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="6e48d-154">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="6e48d-155">Für die Regressionsaufgabe enthält die Spalte **Score** die vorhergesagten Bezeichnungswerte.</span><span class="sxs-lookup"><span data-stu-id="6e48d-155">In case of the regression task, the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="6e48d-156">Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-156">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

### <a name="define-data-and-model-paths"></a><span data-ttu-id="6e48d-157">Definieren von Daten und Modellpfaden</span><span class="sxs-lookup"><span data-stu-id="6e48d-157">Define data and model paths</span></span>

<span data-ttu-id="6e48d-158">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-158">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="6e48d-159">Sie müssen drei Felder erstellen, die die Pfade zu den Dateien mit Datasets und der Datei zum Speichern des Modells enthalten:</span><span class="sxs-lookup"><span data-stu-id="6e48d-159">You need to create three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="6e48d-160">`_trainDataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e48d-160">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="6e48d-161">`_testDataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Evaluieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e48d-161">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="6e48d-162">`_modelPath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="6e48d-162">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="6e48d-163">Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben, und für die `_textLoader`-Variable:</span><span class="sxs-lookup"><span data-stu-id="6e48d-163">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="6e48d-164">Alle ML.NET-Operationen beginnen in der [MLContext-Klasse](xref:Microsoft.ML.MLContext).</span><span class="sxs-lookup"><span data-stu-id="6e48d-164">All ML.NET operations start in the [MLContext class](xref:Microsoft.ML.MLContext).</span></span> <span data-ttu-id="6e48d-165">Beim Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für alle Objekte des Workflows für die Modellerstellung gemeinsam genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e48d-165">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="6e48d-166">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="6e48d-166">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="6e48d-167">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="6e48d-167">Initialize variables in Main</span></span>

<span data-ttu-id="6e48d-168">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die Variable `mlContext` zu deklarieren und zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="6e48d-168">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="6e48d-169">Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode zum Aufruf der `Train`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="6e48d-169">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

<span data-ttu-id="6e48d-170">Die `Train()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="6e48d-170">The `Train()` method executes the following tasks:</span></span>

* <span data-ttu-id="6e48d-171">Laden der Daten.</span><span class="sxs-lookup"><span data-stu-id="6e48d-171">Loads the data.</span></span>
* <span data-ttu-id="6e48d-172">Extrahieren und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="6e48d-172">Extracts and transforms the data.</span></span>
* <span data-ttu-id="6e48d-173">Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="6e48d-173">Trains the model.</span></span>
* <span data-ttu-id="6e48d-174">Zurückgeben des Modells.</span><span class="sxs-lookup"><span data-stu-id="6e48d-174">Returns the model.</span></span>

<span data-ttu-id="6e48d-175">Die `Train`-Methode trainiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="6e48d-175">The `Train` method trains the model.</span></span> <span data-ttu-id="6e48d-176">Erstellen Sie die Methode direkt unter `Main` mit folgendem Code:</span><span class="sxs-lookup"><span data-stu-id="6e48d-176">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

## <a name="load-and-transform-data"></a><span data-ttu-id="6e48d-177">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="6e48d-177">Load and transform data</span></span>

<span data-ttu-id="6e48d-178">Für ML.NET wird die [IDataView-Klasse](xref:Microsoft.ML.IDataView) als flexible, effiziente Möglichkeit zum Beschreiben von Tabellendaten in Zahlen- oder Textform verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e48d-178">ML.NET uses the [IDataView class](xref:Microsoft.ML.IDataView) as a flexible, efficient way of describing numeric or text tabular data.</span></span> <span data-ttu-id="6e48d-179">Mit `IDataView` können entweder Textdateien geladen werden, oder es kann ein Echtzeitladevorgang durchgeführt werden (z. B. SQL-Datenbank- oder Protokolldateien).</span><span class="sxs-lookup"><span data-stu-id="6e48d-179">`IDataView` can load either text files or in real time (for example, SQL database or log files).</span></span> <span data-ttu-id="6e48d-180">Fügen Sie den folgenden Code am Ende der ersten Zeile der `Train()`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e48d-180">Add the following code as the first line of the `Train()` method:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

<span data-ttu-id="6e48d-181">Da Sie den Preis der Taxifahrt vorhersagen möchten, ist die Spalte `FareAmount` das `Label`-Element für die Vorhersage (Ausgabe des Modells).</span><span class="sxs-lookup"><span data-stu-id="6e48d-181">As you want to predict the taxi trip fare, the `FareAmount` column is the `Label` that you will predict (the output of the model).</span></span> <span data-ttu-id="6e48d-182">Verwenden Sie die `CopyColumnsEstimator`-Transformationsklasse, um `FareAmount` zu kopieren, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-182">Use the `CopyColumnsEstimator` transformation class to copy `FareAmount`, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="6e48d-183">Da der Algorithmus, der das Modell trainiert, **numerische** Features erfordert, müssen Sie die kategorischen Datenwerte (`VendorId`, `RateCode` und `PaymentType`) in Zahlen transformieren (`VendorIdEncoded`, `RateCodeEncoded` und `PaymentTypeEncoded`).</span><span class="sxs-lookup"><span data-stu-id="6e48d-183">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers (`VendorIdEncoded`, `RateCodeEncoded`, and `PaymentTypeEncoded`).</span></span> <span data-ttu-id="6e48d-184">Verwenden Sie hierzu die [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer)-Transformationsklasse, mit der verschiedenen Werten in den Spalten verschiedene numerische Schlüsselwerte zugeordnet werden, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-184">To do that, use the [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer) transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="6e48d-185">Im letzten Schritt der Vorbereitung der Daten werden alle Feature-Spalten mithilfe der Transformationsklasse `mlContext.Transforms.Concatenate` in die Spalte **Features** kombiniert.</span><span class="sxs-lookup"><span data-stu-id="6e48d-185">The last step in data preparation combines all of the feature columns into the **Features** column using the `mlContext.Transforms.Concatenate` transformation class.</span></span> <span data-ttu-id="6e48d-186">Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**.</span><span class="sxs-lookup"><span data-stu-id="6e48d-186">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="6e48d-187">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-187">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="6e48d-188">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="6e48d-188">Choose a learning algorithm</span></span>

<span data-ttu-id="6e48d-189">Bei diesem Problem geht es darum, den Preis einer Taxifahrt in New York City vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-189">This problem is about predicting a taxi trip fare in New York City.</span></span> <span data-ttu-id="6e48d-190">Dies mag auf den ersten Blick einfach von der zurückgelegten Stecke abhängen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-190">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="6e48d-191">Taxiunternehmer in New York berechnen jedoch abhängig von anderen Faktoren wie zusätzlichen Fahrgästen oder Kreditkartenzahlung anstelle von Barzahlung unterschiedliche Beträge.</span><span class="sxs-lookup"><span data-stu-id="6e48d-191">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span> <span data-ttu-id="6e48d-192">Ihr Ziel ist es, den Preiswert vorherzusagen. Dies ist ein realer Wert, der auf anderen Faktoren im Dataset basiert.</span><span class="sxs-lookup"><span data-stu-id="6e48d-192">You want to predict the price value, which is a real value, based on the other factors in the dataset.</span></span> <span data-ttu-id="6e48d-193">Wählen Sie hierzu eine Machine Learning-Aufgabe für die [Regression](../resources/glossary.md#regression) aus.</span><span class="sxs-lookup"><span data-stu-id="6e48d-193">To do that, you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

<span data-ttu-id="6e48d-194">Fügen Sie die Machine Learning-Aufgabe [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) an die Definitionen für die Datentransformation an, indem Sie in `Train()` Folgendes als nächste Codezeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="6e48d-194">Append the [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) machine learning task to the data transformation definitions by adding the following as the next line of code in `Train()`:</span></span>

[!code-csharp[FastTreeRegressionTrainer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="6e48d-195">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="6e48d-195">Train the model</span></span>

<span data-ttu-id="6e48d-196">Fügen Sie die folgende Codezeile in der `Train()`-Methode hinzu, um das Modell an die `dataview`-Daten für das Trainieren anzupassen und das trainierte Modell zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="6e48d-196">Fit the model to the training `dataview` and return the trained model by adding the following line of code in the `Train()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

<span data-ttu-id="6e48d-197">Mit der [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29)-Methode wird Ihr Modell trainiert, indem das Dataset transformiert und das Training angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e48d-197">The [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="6e48d-198">Geben Sie das trainierte Modell mit der folgenden Codezeile in der Methode `Train()` zurück:</span><span class="sxs-lookup"><span data-stu-id="6e48d-198">Return the trained model with the following line of code in the `Train()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="6e48d-199">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="6e48d-199">Evaluate the model</span></span>

<span data-ttu-id="6e48d-200">Evaluieren Sie als Nächstes die Leistung Ihres Modells mit Ihren Testdaten zur Qualitätssicherung und Validierung.</span><span class="sxs-lookup"><span data-stu-id="6e48d-200">Next, evaluate your model performance with your test data for quality assurance and validation.</span></span> <span data-ttu-id="6e48d-201">Erstellen Sie mit dem folgenden Code die `Evaluate()`-Methode direkt nach `Train()`:</span><span class="sxs-lookup"><span data-stu-id="6e48d-201">Create the `Evaluate()` method, just after `Train()`, with the following code:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="6e48d-202">Die `Evaluate`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="6e48d-202">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="6e48d-203">Laden des Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="6e48d-203">Loads the test dataset.</span></span>
* <span data-ttu-id="6e48d-204">Erstellen des Regressionsauswerters.</span><span class="sxs-lookup"><span data-stu-id="6e48d-204">Creates the regression evaluator.</span></span>
* <span data-ttu-id="6e48d-205">Evaluieren des Modells und Erstellen von Metriken.</span><span class="sxs-lookup"><span data-stu-id="6e48d-205">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="6e48d-206">Anzeigen der Metriken.</span><span class="sxs-lookup"><span data-stu-id="6e48d-206">Displays the metrics.</span></span>

<span data-ttu-id="6e48d-207">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Train`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-207">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="6e48d-208">Laden Sie das Testdataset, indem Sie die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A)-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e48d-208">Load the test dataset using the [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method.</span></span> <span data-ttu-id="6e48d-209">Evaluieren Sie das Modell, indem Sie dieses Dataset als Qualitätsprüfung verwenden. Fügen Sie hierzu in der `Evaluate`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-209">Evaluate the model using this dataset as a quality check by adding the following code in the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="6e48d-210">Fügen Sie als Nächstes `Evaluate()` den folgenden Code hinzu, um die `Test`-Daten zu transformieren:</span><span class="sxs-lookup"><span data-stu-id="6e48d-210">Next, transform the `Test` data by adding the following code to `Evaluate()`:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="6e48d-211">Mit der [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode werden Vorhersagen für die Eingabezeilen des Testdatasets getroffen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-211">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for the test dataset input rows.</span></span>

<span data-ttu-id="6e48d-212">Die `RegressionContext.Evaluate`-Methode berechnet die Qualitätsmetriken für das `PredictionModel` mit dem angegebenen Dataset.</span><span class="sxs-lookup"><span data-stu-id="6e48d-212">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="6e48d-213">Das zurückgegebene <xref:Microsoft.ML.Data.RegressionMetrics>-Objekt enthält alle von Regressionsauswertern berechneten Metriken.</span><span class="sxs-lookup"><span data-stu-id="6e48d-213">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span>

<span data-ttu-id="6e48d-214">Um diese zur Bestimmung der Qualität des Modells anzuzeigen, müssen Sie die Metriken zuerst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-214">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="6e48d-215">Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-215">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="6e48d-216">Nach der Vorhersagekonfiguration wertet die [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A)-Methode das Modell aus. Dabei werden die Vorhersagewerte mit den tatsächlichen `Labels` im Testdataset verglichen und die Leistungsmetriken für das Modell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6e48d-216">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="6e48d-217">Fügen Sie den folgenden Code hinzu, um das Modell zu evaluieren und die Auswertungsmetriken zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="6e48d-217">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="6e48d-218">[RSquared](../resources/glossary.md#coefficient-of-determination) ist eine weitere Auswertungsmetrik der Regressionsmodelle.</span><span class="sxs-lookup"><span data-stu-id="6e48d-218">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="6e48d-219">RSquared akzeptiert Werte zwischen 0 (null) und 1.</span><span class="sxs-lookup"><span data-stu-id="6e48d-219">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="6e48d-220">Je näher der Wert an 1 liegt, desto besser ist das Modell.</span><span class="sxs-lookup"><span data-stu-id="6e48d-220">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="6e48d-221">Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RSquared-Wert anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="6e48d-221">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="6e48d-222">[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) ist eine der Auswertungsmetriken aus dem Regressionsmodell.</span><span class="sxs-lookup"><span data-stu-id="6e48d-222">[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="6e48d-223">Je niedriger sie ausfällt, desto besser ist das Modell.</span><span class="sxs-lookup"><span data-stu-id="6e48d-223">The lower it is, the better the model is.</span></span> <span data-ttu-id="6e48d-224">Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RMS-Wert anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="6e48d-224">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="6e48d-225">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="6e48d-225">Use the model for predictions</span></span>

<span data-ttu-id="6e48d-226">Erstellen Sie die `TestSinglePrediction`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:</span><span class="sxs-lookup"><span data-stu-id="6e48d-226">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="6e48d-227">Die `TestSinglePrediction`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="6e48d-227">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="6e48d-228">Erstellen eines einzelnen Kommentars aus Testdaten.</span><span class="sxs-lookup"><span data-stu-id="6e48d-228">Creates a single comment of test data.</span></span>
* <span data-ttu-id="6e48d-229">Vorhersagen des Fahrpreisbetrags anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="6e48d-229">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="6e48d-230">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="6e48d-230">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="6e48d-231">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="6e48d-231">Displays the predicted results.</span></span>

<span data-ttu-id="6e48d-232">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-232">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="6e48d-233">Fügen Sie `TestSinglePrediction()` den folgenden Code hinzu, um mit `PredictionEngine` den Preis für die Fahrt vorherzusagen:</span><span class="sxs-lookup"><span data-stu-id="6e48d-233">Use the `PredictionEngine` to predict the fare by adding the following code to `TestSinglePrediction()`:</span></span>

[!code-csharp[MakePredictionEngine](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]

<span data-ttu-id="6e48d-234">Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können.</span><span class="sxs-lookup"><span data-stu-id="6e48d-234">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="6e48d-235">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="6e48d-235">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="6e48d-236">Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="6e48d-236">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="6e48d-237">Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="6e48d-237">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="6e48d-238">Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.</span><span class="sxs-lookup"><span data-stu-id="6e48d-238">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="6e48d-239">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6e48d-239">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="6e48d-240">Dieses Tutorial verwendet eine Testfahrt innerhalb dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="6e48d-240">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="6e48d-241">Sie können später weitere Szenarios zum Experimentieren mit dem Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-241">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="6e48d-242">Fügen Sie eine Fahrt hinzu, um die Kostenvorhersage des trainierten Modells in der `TestSinglePrediction()`-Methode zu testen, indem Sie eine `TaxiTrip`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="6e48d-242">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction()` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

<span data-ttu-id="6e48d-243">Als Nächstes wird der Preis für die Fahrt basierend auf einer einzelnen Instanz der Taxifahrtdaten vorhergesagt und an `PredictionEngine` übergeben, indem als nächste Codezeilen der `TestSinglePrediction()`-Methode Folgendes hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="6e48d-243">Next, predict the fare based on a single instance of the taxi trip data and pass it to the `PredictionEngine` by adding the following as the next lines of code in the `TestSinglePrediction()` method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="6e48d-244">Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Dateninstanz.</span><span class="sxs-lookup"><span data-stu-id="6e48d-244">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single instance of data.</span></span>

<span data-ttu-id="6e48d-245">Um den vorhergesagten Preis der angegebenen Fahrt anzuzeigen, fügen Sie den folgenden Code der `TestSinglePrediction`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="6e48d-245">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="6e48d-246">Führen Sie das Programm aus, um den vorhergesagten Taxifahrtpreis für den Testfall anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6e48d-246">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="6e48d-247">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="6e48d-247">Congratulations!</span></span> <span data-ttu-id="6e48d-248">Hiermit haben Sie ein Machine Learning-Modell erfolgreich zum Vorhersagen von Taxifahrtpreisen erstellt, die Genauigkeit ausgewertet und es zum Vorhersagen der Preise verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e48d-248">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="6e48d-249">Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="6e48d-249">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6e48d-250">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6e48d-250">Next steps</span></span>

<span data-ttu-id="6e48d-251">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6e48d-251">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="6e48d-252">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="6e48d-252">Prepare and understand the data</span></span>
> * <span data-ttu-id="6e48d-253">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="6e48d-253">Create a learning pipeline</span></span>
> * <span data-ttu-id="6e48d-254">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="6e48d-254">Load and transform the data</span></span>
> * <span data-ttu-id="6e48d-255">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="6e48d-255">Choose a learning algorithm</span></span>
> * <span data-ttu-id="6e48d-256">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="6e48d-256">Train the model</span></span>
> * <span data-ttu-id="6e48d-257">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="6e48d-257">Evaluate the model</span></span>
> * <span data-ttu-id="6e48d-258">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="6e48d-258">Use the model for predictions</span></span>

<span data-ttu-id="6e48d-259">Fahren Sie mit dem nächsten Tutorial fort, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="6e48d-259">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6e48d-260">Iris-Clustering</span><span class="sxs-lookup"><span data-stu-id="6e48d-260">Iris clustering</span></span>](iris-clustering.md)
