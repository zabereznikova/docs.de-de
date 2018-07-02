---
title: Verwenden von ML.NET, um Taxifahrtpreise in New York vorherzusagen (Regression)
description: Erfahren Sie, wie Sie ML.NET in einem Regressionsszenario verwenden.
author: aditidugar
ms.author: johalex
ms.date: 06/05/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 048ed1d38408c1ba4901c554cae33d5552c9e303
ms.sourcegitcommit: 5b0802832fb9ad684d34e69b8644a16a5b7c4810
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2018
ms.locfileid: "34860672"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="b2b57-103">Tutorial: Verwenden von ML.NET, um Taxifahrtpreise in New York vorherzusagen (Regression)</span><span class="sxs-lookup"><span data-stu-id="b2b57-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="b2b57-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b2b57-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="b2b57-105">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="b2b57-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="b2b57-106">In diesem Tutorial wird veranschaulicht, wie ML.NET zum Erstellen eines [Regressionsmodells](../resources/glossary.md#regression) für die Vorhersage von Taxifahrtpreisen in New York City verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2b57-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="b2b57-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b2b57-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="b2b57-108">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="b2b57-108">Understand the problem</span></span>
> * <span data-ttu-id="b2b57-109">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="b2b57-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="b2b57-110">Vorbereiten und Verstehen Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="b2b57-110">Prepare and understand your data</span></span>
> * <span data-ttu-id="b2b57-111">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="b2b57-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="b2b57-112">Laden und Transformieren Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="b2b57-112">Load and transform your data</span></span>
> * <span data-ttu-id="b2b57-113">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="b2b57-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="b2b57-114">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="b2b57-114">Train the model</span></span>
> * <span data-ttu-id="b2b57-115">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="b2b57-115">Evaluate the model</span></span>
> * <span data-ttu-id="b2b57-116">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="b2b57-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2b57-117">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="b2b57-117">Prerequisites</span></span>

* <span data-ttu-id="b2b57-118">[Visual Studio 2017 15.6 oder höher](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload für die „plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="b2b57-118">[Visual Studio 2017 15.6 or later](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="b2b57-119">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="b2b57-119">Understand the problem</span></span>

<span data-ttu-id="b2b57-120">Im Zentrum des Problems steht die **Vorhersage des Fahrtpreises einer Taxifahrt in New York City**.</span><span class="sxs-lookup"><span data-stu-id="b2b57-120">This problem is centered around **predicting the fare of a taxi trip in New York City**.</span></span> <span data-ttu-id="b2b57-121">Dies mag auf den ersten Blick einfach von der zurückgelegten Stecke abhängen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="b2b57-122">Taxiunternehmer in New York berechnen jedoch abhängig von anderen Faktoren wie zusätzlichen Fahrgästen oder Kreditkartenzahlung anstelle von Barzahlung unterschiedliche Beträge.</span><span class="sxs-lookup"><span data-stu-id="b2b57-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="b2b57-123">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="b2b57-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="b2b57-124">Um den Taxifahrtpreis vorhersagen zu können, wählen Sie zunächst die entsprechende Machine Learning-Aufgabe aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-124">To predict the taxi fare, you first select the appropriate machine learning task.</span></span> <span data-ttu-id="b2b57-125">Sie möchten einen realen Wert (einen Double-Datentypwert, der den Preis darstellt) auf Basis der anderen Faktoren im Dataset vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-125">You are looking to predict a real value (a double that represents price) based on the other factors in the dataset.</span></span> <span data-ttu-id="b2b57-126">Wählen Sie eine [**Regression**](../resources/glossary.md#regression)saufgabe aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-126">You choose a [**regression**](../resources/glossary.md#regression) task.</span></span>

<span data-ttu-id="b2b57-127">Der Prozess zum Trainieren des Modells identifiziert, welche Faktoren im Dataset bei der endgültigen Fahrtpreisvorhersage am einflussreichsten sind.</span><span class="sxs-lookup"><span data-stu-id="b2b57-127">The process of training the model identifies which factors in the dataset are most influential when predicting the final fare price.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="b2b57-128">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="b2b57-128">Create a console application</span></span>

1. <span data-ttu-id="b2b57-129">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="b2b57-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="b2b57-130">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="b2b57-131">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="b2b57-132">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="b2b57-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="b2b57-133">Geben Sie „TaxiFarePrediction“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

2. <span data-ttu-id="b2b57-134">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="b2b57-134">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="b2b57-135">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-135">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="b2b57-136">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="b2b57-136">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="b2b57-137">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="b2b57-137">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="b2b57-138">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-138">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b2b57-139">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-139">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="b2b57-140">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-and-understand-your-data"></a><span data-ttu-id="b2b57-141">Vorbereiten und Verstehen Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="b2b57-141">Prepare and understand your data</span></span>

1. <span data-ttu-id="b2b57-142">Laden Sie die Datasets [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) und [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*.</span><span class="sxs-lookup"><span data-stu-id="b2b57-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="b2b57-143">Das Taxi Trip-Dataset trainiert das Machine Learning-Modell und kann verwendet werden, um zu evaluieren, wie genau das Modell ist.</span><span class="sxs-lookup"><span data-stu-id="b2b57-143">The Taxi Trip data set trains the machine learning model and can be used to evaluate how accurate your model is.</span></span> <span data-ttu-id="b2b57-144">Diese Datasets stammen ursprünglich aus dem [Dataset „NYC TLC Taxi Trip“](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="b2b57-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

2. <span data-ttu-id="b2b57-145">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.csv-Dateien, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="b2b57-146">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Immer**.</span><span class="sxs-lookup"><span data-stu-id="b2b57-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

3. <span data-ttu-id="b2b57-147">Öffnen Sie das Dataset **taxi-fare-train.csv** im Code-Editor, und sehen Sie sich die Spaltenüberschriften in der ersten Zeile an.</span><span class="sxs-lookup"><span data-stu-id="b2b57-147">Open the **taxi-fare-train.csv** data set in the code editor and look at column headers in the first row.</span></span> <span data-ttu-id="b2b57-148">Sehen Sie sich jede der Spalten an.</span><span class="sxs-lookup"><span data-stu-id="b2b57-148">Take a look at each of the columns.</span></span> <span data-ttu-id="b2b57-149">Machen Sie sich mit den Daten vertraut, und entscheiden Sie, welche Spalten **Features** sind, und was die **Bezeichnung** ist.</span><span class="sxs-lookup"><span data-stu-id="b2b57-149">Understand the data and decide which columns are **features** and which is the **label**.</span></span>

<span data-ttu-id="b2b57-150">Die **Bezeichnung** ist der Bezeichner der Spalte, die Sie vorhersagen möchten.</span><span class="sxs-lookup"><span data-stu-id="b2b57-150">The **label** is the identifier of the column you are trying to predict.</span></span> <span data-ttu-id="b2b57-151">Die angegebenen **Features** werden verwendet, um die Bezeichnung vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-151">The identified **features** are used to predict the label.</span></span>

* <span data-ttu-id="b2b57-152">**vendor_id:** Die ID des Taxiunternehmers ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="b2b57-152">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="b2b57-153">**rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="b2b57-153">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="b2b57-154">**passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="b2b57-154">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="b2b57-155">**trip_time_in_secs:** Die Dauer der Fahrt.</span><span class="sxs-lookup"><span data-stu-id="b2b57-155">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="b2b57-156">Die Dauer der Fahrt ist erst nach ihrem Ende bekannt.</span><span class="sxs-lookup"><span data-stu-id="b2b57-156">You won't know how long the trip takes until after it is completed.</span></span> <span data-ttu-id="b2b57-157">Sie können diese Spalte aus dem Modell ausschließen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-157">You exclude this column from the model.</span></span>
* <span data-ttu-id="b2b57-158">**trip_distance:** Die Fahrtstrecke ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="b2b57-158">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="b2b57-159">**payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="b2b57-159">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="b2b57-160">**fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="b2b57-160">**fare_amount:** The total taxi fare paid is the label.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="b2b57-161">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="b2b57-161">Create classes and define paths</span></span>

<span data-ttu-id="b2b57-162">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2b57-162">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="b2b57-163">Sie müssen drei globale Variablen erstellen, die die Pfade zu den zuletzt heruntergeladenen Dateien enthalten und das Modell speichern:</span><span class="sxs-lookup"><span data-stu-id="b2b57-163">You need to create three global variables to hold the paths to the recently downloaded files and to save the model:</span></span>

* <span data-ttu-id="b2b57-164">`_datapath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2b57-164">`_datapath` has the path to the data set used to train the model.</span></span>
* <span data-ttu-id="b2b57-165">`_testdatapath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2b57-165">`_testdatapath` has the path to the data set used to evaluate the model.</span></span>
* <span data-ttu-id="b2b57-166">`_modelpath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="b2b57-166">`_modelpath` has the path where the trained model is stored.</span></span>

<span data-ttu-id="b2b57-167">Fügen Sie den folgenden Code der Zeile direkt oberhalb von `Main` hinzu, um die zuletzt heruntergeladenen Dateien anzugeben:</span><span class="sxs-lookup"><span data-stu-id="b2b57-167">Add the following code to the line right above `Main` to specify the recently downloaded files:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="b2b57-168">Erstellen Sie als Nächstes Klassen für die Eingabedaten und die Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="b2b57-168">Next, create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="b2b57-169">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-169">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="b2b57-170">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="b2b57-170">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="b2b57-171">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-171">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="b2b57-172">Fügen Sie folgenden `using`-Anweisungen der neuen Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2b57-172">Add the following `using` statements to the new file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="b2b57-173">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `TaxiTrip` und `TaxiTripFarePrediction` der Datei *TaxiTrip.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2b57-173">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="b2b57-174">`TaxiTrip` ist die Eingabedatasetklasse und verfügt über Definitionen für jede der Datasetspalten.</span><span class="sxs-lookup"><span data-stu-id="b2b57-174">`TaxiTrip` is the input data set class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="b2b57-175">Die `TaxiTripFarePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b2b57-175">The `TaxiTripFarePrediction` class is used for prediction after the model has been trained.</span></span> <span data-ttu-id="b2b57-176">Sie verfügt über einen einzelnen Gleitkommawert (`FareAmount`) und das [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute)-Attribut `Score`.</span><span class="sxs-lookup"><span data-stu-id="b2b57-176">It has a single float (`FareAmount`) and a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span>

<span data-ttu-id="b2b57-177">Wechseln Sie nun zurück zur **Program.cs**-Datei.</span><span class="sxs-lookup"><span data-stu-id="b2b57-177">Now go back to the **Program.cs** file.</span></span> <span data-ttu-id="b2b57-178">Ersetzen Sie in `Main` `Console.WriteLine("Hello World!")` durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="b2b57-178">In `Main`, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="b2b57-179">Die `Train`-Methode trainiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="b2b57-179">The `Train` method trains your model.</span></span> <span data-ttu-id="b2b57-180">Erstellen Sie die Funktion direkt unter `Main` mit folgendem Code:</span><span class="sxs-lookup"><span data-stu-id="b2b57-180">Create that function just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="b2b57-181">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="b2b57-181">Create a learning pipeline</span></span>

<span data-ttu-id="b2b57-182">Die Lernpipeline lädt alle Daten und Algorithmen, die zum Trainieren des Modells erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b2b57-182">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="b2b57-183">Fügen Sie der `Train()`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2b57-183">Add the following code into the `Train()` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a><span data-ttu-id="b2b57-184">Laden und Transformieren Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="b2b57-184">Load and transform your data</span></span>

<span data-ttu-id="b2b57-185">Als Nächstes laden Sie die Daten in die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="b2b57-185">Next, load your data into the pipeline.</span></span> <span data-ttu-id="b2b57-186">Zeigen Sie auf die anfänglich erstellte Variable `_datapath`, und geben Sie das Trennzeichen der CSV-Datei („,“) an.</span><span class="sxs-lookup"><span data-stu-id="b2b57-186">Point to the `_datapath` created initially and specify the delimiter of the .csv file (,).</span></span> <span data-ttu-id="b2b57-187">Fügen Sie den folgenden Code in die `Train()`-Methode unterhalb des letzten Schritts ein:</span><span class="sxs-lookup"><span data-stu-id="b2b57-187">Add the following code into the `Train()` method underneath the last step:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

<span data-ttu-id="b2b57-188">Sie müssen in dem Code, den Sie erstellen, ohne Unterstriche auf die Spalten verweisen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-188">You'll refer to the columns without the underscores in the code you're creating.</span></span> <span data-ttu-id="b2b57-189">Kopieren Sie die `FareAmount`-Spalte mit der `ColumnCopier()`-Funktion in eine neue Spalte namens „Label“.</span><span class="sxs-lookup"><span data-stu-id="b2b57-189">Copy the `FareAmount` column into a new column called "Label" using the `ColumnCopier()` function.</span></span> <span data-ttu-id="b2b57-190">Diese Spalte ist die **Bezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="b2b57-190">This column is the **Label**.</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="b2b57-191">Transformieren Sie die Daten mittels **Feature Engineering**, sodass sie effektiv für das Machine Learning verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b2b57-191">Conduct some **feature engineering** to transform the data so that it can be used effectively for machine learning.</span></span> <span data-ttu-id="b2b57-192">Da der Algorithmus, der das Modell trainiert, **numerische** Features erfordert, transformieren Sie die kategorischen Daten (`VendorId`, `RateCode` und `PaymentType`) in Zahlen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-192">The algorithm that trains the model requires **numeric** features, you transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) into numbers.</span></span> <span data-ttu-id="b2b57-193">Die `CategoricalOneHotVectorizer()`-Funktion weist den Werten in diesen Spalten einen numerischen Schlüssel zu.</span><span class="sxs-lookup"><span data-stu-id="b2b57-193">The `CategoricalOneHotVectorizer()` function assigns a numeric key to the values in each of these columns.</span></span> <span data-ttu-id="b2b57-194">Transformieren Sie die Daten, indem Sie diesen Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b2b57-194">Transform your data by adding this code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="b2b57-195">Im letzten Schritt der Datenvorbereitung werden alle Ihre **Features** mit der `ColumnConcatenator()`-Funktion in einem Vektor kombiniert.</span><span class="sxs-lookup"><span data-stu-id="b2b57-195">The last step in data preparation combines all of your **features** into one vector using the `ColumnConcatenator()` function.</span></span> <span data-ttu-id="b2b57-196">Dank dieses erforderlichen Schritts kann der Algorithmus Ihre Features problemlos verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b2b57-196">This necessary step helps the algorithm easily process your features.</span></span> <span data-ttu-id="b2b57-197">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2b57-197">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="b2b57-198">Beachten Sie, dass die `trip_time_in_secs`-Spalte nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b2b57-198">Notice that the `trip_time_in_secs` column isn't included.</span></span> <span data-ttu-id="b2b57-199">Sie haben bereits bestimmt, dass sie kein nützliches Feature für die Vorhersage ist.</span><span class="sxs-lookup"><span data-stu-id="b2b57-199">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="b2b57-200">Diese Schritte müssen der Pipeline zur erfolgreichen Ausführung in der oben angegebenen Reihenfolge hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b2b57-200">These steps must be added to Pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="b2b57-201">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="b2b57-201">Choose a learning algorithm</span></span>

<span data-ttu-id="b2b57-202">Nach dem Hinzufügen von Daten zur Pipeline und dem Transformieren in das richtige Eingabeformat wählen Sie einen Lernalgorithmus (**Lernmodul**) aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-202">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="b2b57-203">Der Lernalgorithmus trainiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="b2b57-203">The learning algorithm trains the model.</span></span> <span data-ttu-id="b2b57-204">Da Sie eine **Regressionsaufgabe** für dieses Problem ausgewählt haben, fügen Sie der Pipeline ein Lernmodul namens `FastTreeRegressor()` hinzu, das **Gradient Boosting** einsetzt.</span><span class="sxs-lookup"><span data-stu-id="b2b57-204">You chose a **regression task** for this problem, so you add a learner called `FastTreeRegressor()` to the pipeline that utilizes **gradient boosting**.</span></span>

<span data-ttu-id="b2b57-205">Gradient Boosting ist eine Machine Learning-Technik für Regressionsprobleme.</span><span class="sxs-lookup"><span data-stu-id="b2b57-205">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="b2b57-206">Sie erstellt jede Regressionsstruktur schrittweise.</span><span class="sxs-lookup"><span data-stu-id="b2b57-206">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="b2b57-207">Sie verwendet eine vordefinierte Verlustfunktion, um den Fehler in jedem Schritt zu messen und im nächsten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b2b57-207">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="b2b57-208">Das Ergebnis ist ein Vorhersagemodell, das sich im Grunde aus schwächeren Vorhersagemodellen zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="b2b57-208">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="b2b57-209">Weitere Informationen zu Gradient Boosting finden Sie unter [Boosted-Entscheidungsstrukturregression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span><span class="sxs-lookup"><span data-stu-id="b2b57-209">For more information about gradient boosting, see [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="b2b57-210">Fügen Sie den folgenden Code nach dem im letzten Schritt hinzugefügten Datenverarbeitungscode in die `Train()`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="b2b57-210">Add the following code into the `Train()` method following the data processing code added in the last step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="b2b57-211">Sie haben alle vorherigen Schritte als einzelne Anweisungen der Pipeline hinzugefügt, aber C# verfügt über eine praktische Initialisierungssyntaxsammlung, die das Erstellen und Initialisieren der Pipeline vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="b2b57-211">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="b2b57-212">Ersetzen Sie den Code, den Sie bislang der `Train()`-Methode hinzugefügt haben, durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="b2b57-212">Replace the code you added so far to the `Train()` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="b2b57-213">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="b2b57-213">Train the model</span></span>

<span data-ttu-id="b2b57-214">Der letzte Schritt ist das Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="b2b57-214">The final step is to train the model.</span></span> <span data-ttu-id="b2b57-215">Bis zu diesem Punkt wurde nichts in der Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b2b57-215">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="b2b57-216">Die `pipeline.Train<T_Input, T_Output>()`-Funktion nimmt den vordefinierten `TaxiTrip`-Klassentyp entgegen und gibt einen `TaxiTripFarePrediction`-Typ aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-216">The `pipeline.Train<T_Input, T_Output>()` function takes in the pre-defined `TaxiTrip` class type and outputs a `TaxiTripFarePrediction` type.</span></span> <span data-ttu-id="b2b57-217">Fügen Sie diesen letzten Codeabschnitt der `Train()`-Funktion hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2b57-217">Add this final piece of code into the `Train()` function:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="b2b57-218">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="b2b57-218">And that's it!</span></span> <span data-ttu-id="b2b57-219">Sie haben erfolgreich ein Machine Learning-Modell trainiert, das Taxifahrtpreise in NYC vorhersagen kann.</span><span class="sxs-lookup"><span data-stu-id="b2b57-219">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="b2b57-220">Untersuchen Sie nun, wie genau Ihr Modell funktioniert, und wie Sie es verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b2b57-220">Now take a look to understand how accurate your model is and learn how to consume it.</span></span>

## <a name="save-the-model"></a><span data-ttu-id="b2b57-221">Speichern des Modells</span><span class="sxs-lookup"><span data-stu-id="b2b57-221">Save the model</span></span>

<span data-ttu-id="b2b57-222">Bevor Sie mit dem nächsten Schritt fortfahren, speichern Sie Ihr Modell in einer ZIP-Datei, indem Sie den folgenden Code am Ende Ihrer `Train()`-Funktion hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b2b57-222">Before you go onto the next step, save your model to a .zip file by adding the following code at the end of your `Train()` function:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="b2b57-223">Wenn die `await`-Anweisung dem `model.WriteAsync()`-Aufruf hinzugefügt wird, bedeutet dies, dass die `Train()`-Methode in eine asynchrone Methode geändert werden muss, die eine `Task` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b2b57-223">Adding the `await` statement to the `model.WriteAsync()` call means that the `Train()` method must be changed to an async method that returns a `Task`.</span></span> <span data-ttu-id="b2b57-224">Ändern Sie die Signatur von `Train` wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b2b57-224">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="b2b57-225">Eine Änderung des Rückgabetyps der `Train`-Methode bedeutet, dass Sie wie im folgenden Code dargestellt ein `await` dem Code hinzufügen müssen, der `Train` in der `Main`-Methode aufruft:</span><span class="sxs-lookup"><span data-stu-id="b2b57-225">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="b2b57-226">Das Hinzufügen eines `await` zu Ihrer `Main`-Methode bedeutet, dass die `Main`-Methode den `async`-Modifizierer benötigt und eine `Task` zurückgeben muss:</span><span class="sxs-lookup"><span data-stu-id="b2b57-226">Adding an `await` in your `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="b2b57-227">Sie müssen auch am Anfang der Datei die folgende Using-Anweisung hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b2b57-227">You also need to add the following using statement at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="b2b57-228">Da die `async Main`-Methode ein neues Feature in C# 7.1 und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.</span><span class="sxs-lookup"><span data-stu-id="b2b57-228">Because the `async Main` method is a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="b2b57-229">Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-229">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="b2b57-230">Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="b2b57-230">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="b2b57-231">Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-231">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="b2b57-232">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2b57-232">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="b2b57-233">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="b2b57-233">Evaluate the model</span></span>

<span data-ttu-id="b2b57-234">Mit der Auswertung wird überprüft, wie gut das Modell funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b2b57-234">Evaluation is the process of checking how well the model works.</span></span> <span data-ttu-id="b2b57-235">Es ist wichtig, dass Ihr Modell gute Vorhersagen mithilfe von Daten trifft, die es nicht verwendet hat, als es trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b2b57-235">It's important that your model makes good predictions on data that it didn't use when it was trained.</span></span> <span data-ttu-id="b2b57-236">Eine Möglichkeit hierfür ist das Aufteilen der Daten in Trainings- und Testdatasets, was Sie in diesem Tutorial praktiziert haben.</span><span class="sxs-lookup"><span data-stu-id="b2b57-236">One way to do this is by splitting the data into train and test datasets, as you did in this tutorial.</span></span> <span data-ttu-id="b2b57-237">Da Sie nun das Modell anhand der Trainingsdaten trainiert haben, können Sie prüfen, wie gut es mit den Testdaten arbeitet.</span><span class="sxs-lookup"><span data-stu-id="b2b57-237">Now that you've trained the model on the train data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="b2b57-238">Wechseln Sie zurück zu Ihrer `Main`-Funktion, und fügen Sie den folgenden Code unterhalb des Aufrufs der `Train()`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="b2b57-238">Go back to your `Main` function and add the following code beneath the call to the `Train()`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="b2b57-239">Die `Evaluate()`-Funktion evaluiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="b2b57-239">The `Evaluate()` function evaluates your model.</span></span> <span data-ttu-id="b2b57-240">Erstellen Sie diese Funktion unter `Train()`.</span><span class="sxs-lookup"><span data-stu-id="b2b57-240">Create that function below `Train()`.</span></span> <span data-ttu-id="b2b57-241">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2b57-241">Add the following code:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="b2b57-242">Laden Sie die Testdaten mit der `TextLoader()`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="b2b57-242">Load the test data using the `TextLoader()` function.</span></span> <span data-ttu-id="b2b57-243">Fügen Sie den folgenden Code der `Evaluate()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2b57-243">Add the following code into the `Evaluate()` method:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="b2b57-244">Fügen Sie den folgenden Code hinzu, um das Modell zu evaluieren und die Metriken dafür zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="b2b57-244">Add the following code to evaluate the model and produce the metrics for it:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="b2b57-245">RMS ist eine Metrik zur Auswertung von Regressionsproblemen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-245">RMS is one metric for evaluating regression problems.</span></span> <span data-ttu-id="b2b57-246">Je niedriger sie ausfällt, desto besser das Modell.</span><span class="sxs-lookup"><span data-stu-id="b2b57-246">The lower it is, the better your model.</span></span> <span data-ttu-id="b2b57-247">Fügen Sie den folgenden Code der `Evaluate()`-Funktion hinzu, um den RMS-Wert für Ihr Modell zu drucken.</span><span class="sxs-lookup"><span data-stu-id="b2b57-247">Add the following code into the `Evaluate()` function to print the RMS for your model.</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="b2b57-248">RSquared ist eine weitere Metrik zur Auswertung von Regressionsproblemen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-248">RSquared is another metric for evaluating regression problems.</span></span> <span data-ttu-id="b2b57-249">RSquared wird einen Wert zwischen 0 und 1 besitzen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-249">RSquared will be a value between 0 and 1.</span></span> <span data-ttu-id="b2b57-250">Je näher Sie an 1 sind, umso besser das Modell.</span><span class="sxs-lookup"><span data-stu-id="b2b57-250">The closer you are to 1, the better your model.</span></span> <span data-ttu-id="b2b57-251">Fügen Sie den folgenden Code der `Evaluate()`-Funktion hinzu, um den RSquared-Wert für Ihr Modell zu drucken.</span><span class="sxs-lookup"><span data-stu-id="b2b57-251">Add the following code into the `Evaluate()` function to print the RSquared value for your model.</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="b2b57-252">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="b2b57-252">Use the model for predictions</span></span>

<span data-ttu-id="b2b57-253">Als Nächstes erstellen Sie eine Klasse, um Testszenarien unterzubringen, die Sie verwenden können, um sicherzustellen, dass Ihr Modell ordnungsgemäß arbeitet:</span><span class="sxs-lookup"><span data-stu-id="b2b57-253">Next, create a class to house test scenarios that you can use to make sure your model is working correctly:</span></span>

1. <span data-ttu-id="b2b57-254">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-254">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="b2b57-255">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TestTrips.cs*.</span><span class="sxs-lookup"><span data-stu-id="b2b57-255">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="b2b57-256">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="b2b57-256">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="b2b57-257">Ändern Sie die Klasse wie im folgenden Beispiel in „statisch“:</span><span class="sxs-lookup"><span data-stu-id="b2b57-257">Modify the class to be static like in the following example:</span></span>

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="b2b57-258">Dieses Tutorial verwendet eine Testfahrt innerhalb dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="b2b57-258">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="b2b57-259">Sie können später weitere Szenarien zum Experimentieren mit diesem Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-259">Later you can add other scenarios to experiment with this sample.</span></span> <span data-ttu-id="b2b57-260">Fügen Sie den folgenden Code der `TestTrips`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2b57-260">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="b2b57-261">Der tatsächliche Preis dieser Fahrt beträgt 29,5, aber verwenden Sie 0 als Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="b2b57-261">This trip's actual fare is 29.5, but use 0 as a placeholder.</span></span> <span data-ttu-id="b2b57-262">Der Machine Learning-Algorithmus wird den Fahrpreis vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-262">The machine learning algorithm will predict the fare.</span></span>

<span data-ttu-id="b2b57-263">Fügen Sie den folgenden Code Ihrer `Main`-Funktion hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b57-263">Add the following code in your `Main` function.</span></span> <span data-ttu-id="b2b57-264">Sie testet unser Modell mithilfe der `TestTrip`-Daten:</span><span class="sxs-lookup"><span data-stu-id="b2b57-264">It tests out your model using the `TestTrip` data:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="b2b57-265">Führen Sie das Programm aus, um den vorhergesagten Taxifahrtpreis für den Testfall anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2b57-265">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="b2b57-266">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="b2b57-266">Congratulations!</span></span> <span data-ttu-id="b2b57-267">Sie haben jetzt erfolgreich ein Machine Learning-Modell für die Vorhersage von Taxifahrtpreisen erstellt, seine Genauigkeit ausgewertet und es getestet.</span><span class="sxs-lookup"><span data-stu-id="b2b57-267">You've now successfully built a machine learning model for predicting taxi fares, evaluated its accuracy, and tested it.</span></span> <span data-ttu-id="b2b57-268">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="b2b57-268">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b2b57-269">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b2b57-269">Next steps</span></span>

<span data-ttu-id="b2b57-270">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b2b57-270">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="b2b57-271">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="b2b57-271">Understand the problem</span></span>
> * <span data-ttu-id="b2b57-272">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="b2b57-272">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="b2b57-273">Vorbereiten und Verstehen Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="b2b57-273">Prepare and understand your data</span></span>
> * <span data-ttu-id="b2b57-274">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="b2b57-274">Create a learning pipeline</span></span>
> * <span data-ttu-id="b2b57-275">Laden und Transformieren Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="b2b57-275">Load and transform your data</span></span>
> * <span data-ttu-id="b2b57-276">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="b2b57-276">Choose a learning algorithm</span></span>
> * <span data-ttu-id="b2b57-277">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="b2b57-277">Train the model</span></span>
> * <span data-ttu-id="b2b57-278">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="b2b57-278">Evaluate the model</span></span>
> * <span data-ttu-id="b2b57-279">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="b2b57-279">Use the model for predictions</span></span>

<span data-ttu-id="b2b57-280">In unserem GitHub-Repository können Sie mit dem Lernen fortfahren und weitere Beispiele finden.</span><span class="sxs-lookup"><span data-stu-id="b2b57-280">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="b2b57-281">dotnet/machinelearning GitHub repository</span><span class="sxs-lookup"><span data-stu-id="b2b57-281">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
