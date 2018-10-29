---
title: Verwenden von ML.NET, um Taxifahrtpreise in New York vorherzusagen (Regression)
description: Erfahren Sie, wie Sie ML.NET in einem Regressionsszenario verwenden.
author: aditidugar
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bfae97d65ec192e9289841c82d84807b4937b09a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183814"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="36497-103">Tutorial: Verwenden von ML.NET, um Taxifahrtpreise in New York vorherzusagen (Regression)</span><span class="sxs-lookup"><span data-stu-id="36497-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="36497-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="36497-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="36497-105">Weitere Informationen finden Sie in der [ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="36497-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="36497-106">In diesem Tutorial wird veranschaulicht, wie ML.NET zum Erstellen eines [Regressionsmodells](../resources/glossary.md#regression) für die Vorhersage von Taxifahrtpreisen in New York City verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="36497-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="36497-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="36497-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="36497-108">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="36497-108">Understand the problem</span></span>
> * <span data-ttu-id="36497-109">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="36497-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="36497-110">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="36497-110">Prepare and understand the data</span></span>
> * <span data-ttu-id="36497-111">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="36497-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="36497-112">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="36497-112">Load and transform the data</span></span>
> * <span data-ttu-id="36497-113">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="36497-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="36497-114">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="36497-114">Train the model</span></span>
> * <span data-ttu-id="36497-115">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="36497-115">Evaluate the model</span></span>
> * <span data-ttu-id="36497-116">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="36497-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36497-117">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="36497-117">Prerequisites</span></span>

* <span data-ttu-id="36497-118">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="36497-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="36497-119">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="36497-119">Understand the problem</span></span>

<span data-ttu-id="36497-120">Bei diesem Problem geht es darum, den Fahrtpreis einer Taxifahrt in New York City vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="36497-120">This problem is about predicting the fare of a taxi trip in New York City.</span></span> <span data-ttu-id="36497-121">Dies mag auf den ersten Blick einfach von der zurückgelegten Stecke abhängen.</span><span class="sxs-lookup"><span data-stu-id="36497-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="36497-122">Taxiunternehmer in New York berechnen jedoch abhängig von anderen Faktoren wie zusätzlichen Fahrgästen oder Kreditkartenzahlung anstelle von Barzahlung unterschiedliche Beträge.</span><span class="sxs-lookup"><span data-stu-id="36497-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="36497-123">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="36497-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="36497-124">Ihr Ziel ist es, den Preiswert vorherzusagen, was einem echten Wert entspricht, der auf anderen Faktoren im Dataset basiert.</span><span class="sxs-lookup"><span data-stu-id="36497-124">You want to predict the price value, which is a real value, based on the other factors in the data set.</span></span> <span data-ttu-id="36497-125">Wählen Sie hierzu eine Machine Learning-[Regressionsaufgabe](../resources/glossary.md#regression) aus.</span><span class="sxs-lookup"><span data-stu-id="36497-125">To do that you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="36497-126">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="36497-126">Create a console application</span></span>

1. <span data-ttu-id="36497-127">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="36497-127">Open Visual Studio 2017.</span></span> <span data-ttu-id="36497-128">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="36497-128">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="36497-129">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-129">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="36497-130">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="36497-130">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="36497-131">Geben Sie „TaxiFarePrediction“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-131">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

1. <span data-ttu-id="36497-132">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset und die Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="36497-132">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="36497-133">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-133">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="36497-134">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="36497-134">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="36497-135">Installieren Sie das NuGet-Paket **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="36497-135">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="36497-136">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-136">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="36497-137">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, wählen Sie das Paket in der Liste aus, und klicken Sie anschließend auf die Schaltfläche **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="36497-137">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="36497-138">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="36497-138">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="36497-139">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="36497-139">Prepare and understand the data</span></span>

1. <span data-ttu-id="36497-140">Laden Sie die Datasets [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) und [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*.</span><span class="sxs-lookup"><span data-stu-id="36497-140">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="36497-141">Diese Datasets werden zum Trainieren des Machine Learning-Modells und zum anschließenden Auswerten der Genauigkeit des Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="36497-141">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="36497-142">Diese Datasets stammen ursprünglich aus dem [Dataset „NYC TLC Taxi Trip“](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="36497-142">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="36497-143">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die „\*.csv“-Dateien, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-143">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="36497-144">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="36497-144">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="36497-145">Öffnen Sie das Dataset **taxi-fare-train.csv**, und sehen Sie sich die Spaltenheader in der ersten Zeile an.</span><span class="sxs-lookup"><span data-stu-id="36497-145">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="36497-146">Sehen Sie sich jede der Spalten an.</span><span class="sxs-lookup"><span data-stu-id="36497-146">Take a look at each of the columns.</span></span> <span data-ttu-id="36497-147">Machen Sie sich mit den Daten vertraut, und entscheiden Sie, welche Spalten **Features** sind, und welche Spalte die **Bezeichnung** ist.</span><span class="sxs-lookup"><span data-stu-id="36497-147">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="36497-148">Die **Bezeichnung** ist der Bezeichner der Spalte, die Sie vorhersagen möchten.</span><span class="sxs-lookup"><span data-stu-id="36497-148">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="36497-149">Die angegebenen **Features** werden verwendet, um die Bezeichnung vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="36497-149">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="36497-150">Das angegebene Dataset enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="36497-150">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="36497-151">**vendor_id:** Die ID des Taxiunternehmers ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="36497-151">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="36497-152">**rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="36497-152">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="36497-153">**passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="36497-153">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="36497-154">**trip_time_in_secs:** Die Dauer der Fahrt.</span><span class="sxs-lookup"><span data-stu-id="36497-154">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="36497-155">Der Fahrpreis soll vorhergesagt werden, bevor die Fahrt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="36497-155">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="36497-156">Zu diesem Zeitpunkt wissen Sie noch nicht, wie lange die Fahrt dauert.</span><span class="sxs-lookup"><span data-stu-id="36497-156">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="36497-157">Deshalb ist die Fahrtzeit kein Feature, und Sie müssen diese Spalte aus dem Modell ausschließen.</span><span class="sxs-lookup"><span data-stu-id="36497-157">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="36497-158">**trip_distance:** Die Fahrtstrecke ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="36497-158">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="36497-159">**payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="36497-159">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="36497-160">**fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="36497-160">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="36497-161">Erstellen von Datenklassen</span><span class="sxs-lookup"><span data-stu-id="36497-161">Create data classes</span></span>

<span data-ttu-id="36497-162">Erstellen Sie Klassen für die Eingabedaten und die Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="36497-162">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="36497-163">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-163">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="36497-164">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="36497-164">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="36497-165">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-165">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="36497-166">Fügen Sie der Formularklasse die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-166">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="36497-167">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `TaxiTrip` und `TaxiTripFarePrediction` der Datei *TaxiTrip.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-167">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="36497-168">`TaxiTrip` ist die Eingabedatenklasse und verfügt über Definitionen für jede der Datasetspalten.</span><span class="sxs-lookup"><span data-stu-id="36497-168">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="36497-169">Verwenden Sie das [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute)-Attribut, um die Indizes der Quellspalten im Dataset festzulegen.</span><span class="sxs-lookup"><span data-stu-id="36497-169">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="36497-170">Die Klasse `TaxiTripFarePrediction` stellt die vorhergesagten Ergebnisse dar.</span><span class="sxs-lookup"><span data-stu-id="36497-170">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="36497-171">Sie verfügt über ein einzelnes Feld für einen Gleitkommawert (`FareAmount`) mit einem angewendeten `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute)-Attribut.</span><span class="sxs-lookup"><span data-stu-id="36497-171">It has a single float field, `FareAmount`, with a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span> <span data-ttu-id="36497-172">Für die Regressionsaufgabe enthält die Spalte **Score** die vorhergesagten Bezeichnungswerte.</span><span class="sxs-lookup"><span data-stu-id="36497-172">In case of the regression task the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="36497-173">Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="36497-173">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="36497-174">Definieren von Daten und Modellpfaden</span><span class="sxs-lookup"><span data-stu-id="36497-174">Define data and model paths</span></span>

<span data-ttu-id="36497-175">Wechseln Sie zurück zur Datei *Program.cs*, und fügen Sie drei Felder hinzu, die die Pfade zu den Dateien mit Datasets und zur Datei zum Speichern des Modells enthalten:</span><span class="sxs-lookup"><span data-stu-id="36497-175">Go back to the *Program.cs* file and add three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="36497-176">`_datapath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="36497-176">`_datapath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="36497-177">`_testdatapath` enthält den Pfad zur Datei mit dem Dataset, das zum Evaluieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="36497-177">`_testdatapath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="36497-178">`_modelpath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="36497-178">`_modelpath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="36497-179">Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:</span><span class="sxs-lookup"><span data-stu-id="36497-179">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="36497-180">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *Program.cs* hinzu, um den obenstehenden Code zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="36497-180">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsingsForPaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Using statements for path definitions")]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="36497-181">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="36497-181">Create a learning pipeline</span></span>

<span data-ttu-id="36497-182">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-182">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="36497-183">Ersetzen Sie in der `Main`-Methode `Console.WriteLine("Hello World!")` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="36497-183">In the `Main` method, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="36497-184">Die `Train`-Methode trainiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="36497-184">The `Train` method trains the model.</span></span> <span data-ttu-id="36497-185">Erstellen Sie die Methode direkt unter `Main` mit folgendem Code:</span><span class="sxs-lookup"><span data-stu-id="36497-185">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

<span data-ttu-id="36497-186">Die Lernpipeline lädt alle Daten und Algorithmen, die zum Trainieren des Modells erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="36497-186">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="36497-187">Fügen Sie den folgenden Code der `Train`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-187">Add the following code into the `Train` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-data"></a><span data-ttu-id="36497-188">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="36497-188">Load and transform data</span></span>

<span data-ttu-id="36497-189">Der erste Schritt besteht im Laden der Daten aus dem Trainingsdataset.</span><span class="sxs-lookup"><span data-stu-id="36497-189">The first step to perform is to load data from the training data set.</span></span> <span data-ttu-id="36497-190">In diesem Fall wird das Trainingsdataset in der Textdatei mit einem Pfad gespeichert, der vom Feld `_datapath` definiert wird.</span><span class="sxs-lookup"><span data-stu-id="36497-190">In our case, training data set is stored in the text file with a path defined by the `_datapath` field.</span></span> <span data-ttu-id="36497-191">Die Datei enthält den Header mit den Spaltennamen, weshalb die erste Zeile beim Laden der Daten ignoriert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="36497-191">That file has the header with the column names, so the first row should be ignored while loading data.</span></span> <span data-ttu-id="36497-192">Die Spalten in der Datei werden durch Kommas („,“) getrennt.</span><span class="sxs-lookup"><span data-stu-id="36497-192">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="36497-193">Fügen Sie den folgenden Code der `Train`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-193">Add the following code into the `Train` method:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(useHeader: true, separator: ','));
```

<span data-ttu-id="36497-194">In den nächsten Schritten werden die Spalten mit den jeweiligen in der `TaxiTrip`-Klasse definierten Namen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="36497-194">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="36497-195">Wenn das Modell trainiert und ausgewertet wurde, gelten die Werte in der Spalte **Label** standardmäßig als richtige Werte, die vorhergesagt werden.</span><span class="sxs-lookup"><span data-stu-id="36497-195">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="36497-196">Da der Fahrpreis der Taxifahrt vorhergesagt werden soll, kopieren Sie die Spalte `FareAmount` in die Spalte **Label**.</span><span class="sxs-lookup"><span data-stu-id="36497-196">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="36497-197">Verwenden Sie hierzu <xref:Microsoft.ML.Legacy.Transforms.ColumnCopier>, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-197">To do that, use <xref:Microsoft.ML.Legacy.Transforms.ColumnCopier> and add the following code:</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="36497-198">Da der Algorithmus, der das Modell trainiert, **numerische** Features erfordert, müssen Sie die kategorischen Datenwerte (`VendorId`, `RateCode` und `PaymentType`) in Zahlen transformieren.</span><span class="sxs-lookup"><span data-stu-id="36497-198">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers.</span></span> <span data-ttu-id="36497-199">Verwenden Sie hierzu die Klasse <xref:Microsoft.ML.Legacy.Transforms.CategoricalOneHotVectorizer>, die verschiedenen Werten in den Spalten verschiedene numerische Schlüsselwerte zuordnet, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-199">To do that, use <xref:Microsoft.ML.Legacy.Transforms.CategoricalOneHotVectorizer>, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="36497-200">Im letzten Schritt der Vorbereitung der Daten werden alle Feature-Spalten mithilfe der Transformationsklasse <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> in die Spalte **Features** kombiniert.</span><span class="sxs-lookup"><span data-stu-id="36497-200">The last step in data preparation combines all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="36497-201">Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**.</span><span class="sxs-lookup"><span data-stu-id="36497-201">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="36497-202">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-202">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="36497-203">Beachten Sie, dass die `TripTime`-Spalte, die der `trip_time_in_secs`-Spalte in der Dataset-Datei entspricht, nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="36497-203">Notice that the `TripTime` column, which corresponds to the `trip_time_in_secs` column in the data set file, isn't included.</span></span> <span data-ttu-id="36497-204">Sie haben bereits bestimmt, dass sie kein nützliches Feature für die Vorhersage ist.</span><span class="sxs-lookup"><span data-stu-id="36497-204">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="36497-205">Diese Schritte müssen der Pipeline zur erfolgreichen Ausführung in der oben angegebenen Reihenfolge hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="36497-205">These steps must be added to the pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="36497-206">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="36497-206">Choose a learning algorithm</span></span>

<span data-ttu-id="36497-207">Nach dem Hinzufügen von Daten zur Pipeline und dem Transformieren in das richtige Eingabeformat wählen Sie einen Lernalgorithmus (**Lernmodul**) aus.</span><span class="sxs-lookup"><span data-stu-id="36497-207">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="36497-208">Das Lernmodul trainiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="36497-208">The learner trains the model.</span></span> <span data-ttu-id="36497-209">Da Sie für dieses Problem eine **Regressionsaufgabe** ausgewählt haben, verwenden Sie ein <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor>-Lernmodul. Dies ist ein von ML.NET bereitgestelltes Regressionslernmodul.</span><span class="sxs-lookup"><span data-stu-id="36497-209">You chose a **regression** task for this problem, so you use a <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor> learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="36497-210">Das Lernmodul <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor> verwendet Gradient Boosting.</span><span class="sxs-lookup"><span data-stu-id="36497-210"><xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor> learner utilizes gradient boosting.</span></span> <span data-ttu-id="36497-211">Gradient Boosting ist eine Machine Learning-Technik für Regressionsprobleme.</span><span class="sxs-lookup"><span data-stu-id="36497-211">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="36497-212">Sie erstellt jede Regressionsstruktur schrittweise.</span><span class="sxs-lookup"><span data-stu-id="36497-212">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="36497-213">Sie verwendet eine vordefinierte Verlustfunktion, um den Fehler in jedem Schritt zu messen und im nächsten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="36497-213">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="36497-214">Das Ergebnis ist ein Vorhersagemodell, das sich im Grunde aus schwächeren Vorhersagemodellen zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="36497-214">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="36497-215">Weitere Informationen zu Gradient Boosting finden Sie unter [Boosted-Entscheidungsstrukturregression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span><span class="sxs-lookup"><span data-stu-id="36497-215">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="36497-216">Fügen Sie den folgenden Code nach dem im vorherigen Schritt hinzugefügten Datenverarbeitungscode in die `Train`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="36497-216">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="36497-217">Sie haben alle vorherigen Schritte als einzelne Anweisungen der Pipeline hinzugefügt, aber C# verfügt über eine praktische Initialisierungssyntaxsammlung, die das Erstellen und Initialisieren der Pipeline vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="36497-217">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="36497-218">Ersetzen Sie den Code, den Sie bislang der `Train`-Methode hinzugefügt haben, durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="36497-218">Replace the code you added so far to the `Train` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="36497-219">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="36497-219">Train the model</span></span>

<span data-ttu-id="36497-220">Der letzte Schritt ist das Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="36497-220">The final step is to train the model.</span></span> <span data-ttu-id="36497-221">Bis zu diesem Punkt wurde nichts in der Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="36497-221">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="36497-222">Die Methode `pipeline.Train<TInput, TOutput>` erzeugt das Modell, das eine Instanz vom Typ `TInput` annimmt und eine Instanz vom Typ `TOutput` ausgibt.</span><span class="sxs-lookup"><span data-stu-id="36497-222">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="36497-223">Fügen Sie den folgenden Code der `Train`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-223">Add the following code into the `Train` method:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="36497-224">Und das ist schon alles!</span><span class="sxs-lookup"><span data-stu-id="36497-224">And that's it!</span></span> <span data-ttu-id="36497-225">Sie haben erfolgreich ein Machine Learning-Modell trainiert, das Taxifahrtpreise in NYC vorhersagen kann.</span><span class="sxs-lookup"><span data-stu-id="36497-225">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="36497-226">Anschließend erfahren Sie, wie genau das Modell ist, und wie Sie es verwenden, um die Fahrpreiswerte vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="36497-226">Now let's take a look to understand how accurate the model is and learn how to use it to predict taxi fare values.</span></span>

### <a name="save-the-model"></a><span data-ttu-id="36497-227">Speichern des Modells</span><span class="sxs-lookup"><span data-stu-id="36497-227">Save the model</span></span>

<span data-ttu-id="36497-228">An diesem Punkt haben Sie ein Modell, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="36497-228">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="36497-229">Fügen Sie folgenden Code am Ende der `Train`-Methode hinzu, um das Modell in einer ZIP-Datei zu speichern:</span><span class="sxs-lookup"><span data-stu-id="36497-229">To save the model to a .zip file, add the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="36497-230">Wenn die `await`-Anweisung dem `model.WriteAsync`-Aufruf hinzugefügt wird, bedeutet dies, dass die `Train`-Methode in eine asynchrone Methode geändert werden muss, die eine Aufgabe zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="36497-230">Adding the `await` statement to the `model.WriteAsync` call means that the `Train` method must be changed to an async method that returns a task.</span></span> <span data-ttu-id="36497-231">Ändern Sie die Signatur von `Train` wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="36497-231">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="36497-232">Eine Änderung des Rückgabetyps der `Train`-Methode bedeutet, dass Sie wie im folgenden Code dargestellt ein `await` dem Code hinzufügen müssen, der `Train` in der `Main`-Methode aufruft:</span><span class="sxs-lookup"><span data-stu-id="36497-232">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="36497-233">Wenn Sie `await` in der Methode `Main` verwenden, bedeutet dies, dass die `Main`-Methode den Modifizierer `async` erfordert und eine Aufgabe `Task` zurückgeben muss:</span><span class="sxs-lookup"><span data-stu-id="36497-233">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="36497-234">Außerdem müssen Sie die folgende `using`-Anweisung am Anfang der Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="36497-234">You also need to add the following `using` directive at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="36497-235">Da die `async Main`-Methode ein neues Feature in C# 7.1 und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.</span><span class="sxs-lookup"><span data-stu-id="36497-235">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="36497-236">Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-236">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="36497-237">Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="36497-237">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="36497-238">Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus.</span><span class="sxs-lookup"><span data-stu-id="36497-238">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="36497-239">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="36497-239">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="36497-240">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="36497-240">Evaluate the model</span></span>

<span data-ttu-id="36497-241">Mit der Auswertung wird überprüft, wie gut das Modell Bezeichnungswerte vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="36497-241">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="36497-242">Es ist wichtig, dass das Modell gute Vorhersagen zu Daten trifft, die nicht zum Trainieren des Modells verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="36497-242">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="36497-243">Eine Möglichkeit hierfür ist es, die Daten wie in diesem Tutorial in Trainings- und Testdatasets aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="36497-243">One way to do this is to split the data into training and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="36497-244">Da Sie nun das Modell anhand der Trainingsdaten trainiert haben, können Sie prüfen, wie gut es mit den Testdaten arbeitet.</span><span class="sxs-lookup"><span data-stu-id="36497-244">Now that you've trained the model on the training data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="36497-245">Wechseln Sie zurück zu der `Main`-Methode, und fügen Sie den folgenden Code unter dem Aufruf der `Train`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="36497-245">Go back to the `Main` method and add the following code beneath the call to the `Train`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="36497-246">Die Methode `Evaluate` wertet das Modell aus.</span><span class="sxs-lookup"><span data-stu-id="36497-246">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="36497-247">Fügen Sie den folgenden Code unter der `Train`-Methode hinzu, um die Methode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="36497-247">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="36497-248">Fügen Sie den folgenden Code der `Evaluate`-Methode hinzu, um das Laden der Testdaten einzurichten:</span><span class="sxs-lookup"><span data-stu-id="36497-248">Add the following code into the `Evaluate` method to setup loading of the test data:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="36497-249">Fügen Sie den folgenden Code hinzu, um das Modell zu evaluieren und die Auswertungsmetriken zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="36497-249">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="36497-250">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) ist eine der Auswertungsmetriken aus dem Regressionsmodell.</span><span class="sxs-lookup"><span data-stu-id="36497-250">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="36497-251">Je niedriger sie ausfällt, desto besser ist das Modell.</span><span class="sxs-lookup"><span data-stu-id="36497-251">The lower it is, the better the model is.</span></span> <span data-ttu-id="36497-252">Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RMS-Wert anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="36497-252">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="36497-253">[RSquared](../resources/glossary.md#coefficient-of-determination) ist eine weitere Auswertungsmetrik der Regressionsmodelle.</span><span class="sxs-lookup"><span data-stu-id="36497-253">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="36497-254">RSquared akzeptiert Werte zwischen 0 (null) und 1.</span><span class="sxs-lookup"><span data-stu-id="36497-254">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="36497-255">Je näher der Wert an 1 liegt, desto besser ist das Modell.</span><span class="sxs-lookup"><span data-stu-id="36497-255">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="36497-256">Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RSquared-Wert anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="36497-256">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="36497-257">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="36497-257">Use the model for predictions</span></span>

<span data-ttu-id="36497-258">Erstellen Sie eine Klasse, um Testdateninstanzen unterzubringen:</span><span class="sxs-lookup"><span data-stu-id="36497-258">Create a class to house test data instances:</span></span>

1. <span data-ttu-id="36497-259">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-259">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="36497-260">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TestTrips.cs*.</span><span class="sxs-lookup"><span data-stu-id="36497-260">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="36497-261">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="36497-261">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="36497-262">Ändern Sie die Klasse wie im folgenden Beispiel in „statisch“:</span><span class="sxs-lookup"><span data-stu-id="36497-262">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="36497-263">Dieses Tutorial verwendet eine Testfahrt innerhalb dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="36497-263">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="36497-264">Sie können später weitere Szenarios zum Experimentieren mit dem Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="36497-264">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="36497-265">Fügen Sie den folgenden Code der `TestTrips`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="36497-265">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="36497-266">Der tatsächliche Fahrpreis beträgt $ 29,5.</span><span class="sxs-lookup"><span data-stu-id="36497-266">This trip's actual fare is 29.5.</span></span> <span data-ttu-id="36497-267">Verwenden Sie 0 (null) als Platzhalter, da das Modell den Fahrpreis vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="36497-267">Use 0 as a placeholder, as the model will predict the fare.</span></span>

<span data-ttu-id="36497-268">Wechseln Sie zurück zur Datei *Program.cs*, und fügen Sie der `Main`-Methode den folgenden Code hinzu, um den Fahrpreis für die angegebene Fahrt vorherzusagen:</span><span class="sxs-lookup"><span data-stu-id="36497-268">To predict the fare of the specified trip, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="36497-269">Führen Sie das Programm aus, um den vorhergesagten Taxifahrtpreis für den Testfall anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36497-269">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="36497-270">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="36497-270">Congratulations!</span></span> <span data-ttu-id="36497-271">Hiermit haben Sie ein Machine Learning-Modell erfolgreich zum Vorhersagen von Taxifahrtpreisen erstellt, die Genauigkeit ausgewertet und es zum Vorhersagen der Preise verwendet.</span><span class="sxs-lookup"><span data-stu-id="36497-271">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="36497-272">Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="36497-272">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="36497-273">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="36497-273">Next steps</span></span>

<span data-ttu-id="36497-274">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="36497-274">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="36497-275">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="36497-275">Understand the problem</span></span>
> * <span data-ttu-id="36497-276">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="36497-276">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="36497-277">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="36497-277">Prepare and understand the data</span></span>
> * <span data-ttu-id="36497-278">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="36497-278">Create a learning pipeline</span></span>
> * <span data-ttu-id="36497-279">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="36497-279">Load and transform the data</span></span>
> * <span data-ttu-id="36497-280">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="36497-280">Choose a learning algorithm</span></span>
> * <span data-ttu-id="36497-281">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="36497-281">Train the model</span></span>
> * <span data-ttu-id="36497-282">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="36497-282">Evaluate the model</span></span>
> * <span data-ttu-id="36497-283">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="36497-283">Use the model for predictions</span></span>

<span data-ttu-id="36497-284">Fahren Sie mit dem nächsten Tutorial fort, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="36497-284">Advance to the next tutorial to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="36497-285">Iris-Clustering</span><span class="sxs-lookup"><span data-stu-id="36497-285">Iris clustering</span></span>](iris-clustering.md)
