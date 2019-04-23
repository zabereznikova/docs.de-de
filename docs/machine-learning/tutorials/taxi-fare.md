---
title: Vorhersagen von Preisen mithilfe eines Regressionslernmoduls mit ML.NET
description: Vorhersagen von Preisen mithilfe eines Regressionslernmoduls mit ML.NET.
author: aditidugar
ms.author: johalex
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 49770672ebcff98d8779a888372b5c9f40a55b1d
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611808"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a><span data-ttu-id="881c2-103">Tutorial: Vorhersagen von Preisen mithilfe eines Regressionslernmoduls mit ML.NET</span><span class="sxs-lookup"><span data-stu-id="881c2-103">Tutorial: Predict prices using a regression learner with ML.NET</span></span>

<span data-ttu-id="881c2-104">In diesem Tutorial wird veranschaulicht, wie ML.NET zum Erstellen eines [Regressionsmodells](../resources/glossary.md#regression) für die Vorhersage von Taxifahrtpreisen in New York City verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="881c2-104">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting prices, specifically, New York City taxi fares.</span></span>

> [!NOTE]
> <span data-ttu-id="881c2-105">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="881c2-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="881c2-106">Weitere Informationen finden Sie in der [ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="881c2-106">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="881c2-107">Dieses Tutorial und das zugehörige Beispiel verwenden zurzeit **ML.NET Version 0.11**.</span><span class="sxs-lookup"><span data-stu-id="881c2-107">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="881c2-108">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="881c2-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="881c2-109">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="881c2-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="881c2-110">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="881c2-110">Understand the problem</span></span>
> * <span data-ttu-id="881c2-111">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="881c2-111">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="881c2-112">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="881c2-112">Prepare and understand the data</span></span>
> * <span data-ttu-id="881c2-113">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="881c2-113">Create a learning pipeline</span></span>
> * <span data-ttu-id="881c2-114">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="881c2-114">Load and transform the data</span></span>
> * <span data-ttu-id="881c2-115">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="881c2-115">Choose a learning algorithm</span></span>
> * <span data-ttu-id="881c2-116">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="881c2-116">Train the model</span></span>
> * <span data-ttu-id="881c2-117">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="881c2-117">Evaluate the model</span></span>
> * <span data-ttu-id="881c2-118">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="881c2-118">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="881c2-119">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="881c2-119">Prerequisites</span></span>

* <span data-ttu-id="881c2-120">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="881c2-120">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="881c2-121">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="881c2-121">Understand the problem</span></span>

<span data-ttu-id="881c2-122">Bei diesem Problem geht es darum, den Fahrtpreis einer Taxifahrt in New York City vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="881c2-122">This problem is about predicting the fare of a taxi trip in New York City.</span></span> <span data-ttu-id="881c2-123">Dies mag auf den ersten Blick einfach von der zurückgelegten Stecke abhängen.</span><span class="sxs-lookup"><span data-stu-id="881c2-123">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="881c2-124">Taxiunternehmer in New York berechnen jedoch abhängig von anderen Faktoren wie zusätzlichen Fahrgästen oder Kreditkartenzahlung anstelle von Barzahlung unterschiedliche Beträge.</span><span class="sxs-lookup"><span data-stu-id="881c2-124">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="881c2-125">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="881c2-125">Select the appropriate machine learning task</span></span>

<span data-ttu-id="881c2-126">Ihr Ziel ist es, den Preiswert vorherzusagen, was einem echten Wert entspricht, der auf anderen Faktoren im Dataset basiert.</span><span class="sxs-lookup"><span data-stu-id="881c2-126">You want to predict the price value, which is a real value, based on the other factors in the data set.</span></span> <span data-ttu-id="881c2-127">Wählen Sie hierzu eine Machine Learning-[Regressionsaufgabe](../resources/glossary.md#regression) aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-127">To do that you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="881c2-128">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="881c2-128">Create a console application</span></span>

1. <span data-ttu-id="881c2-129">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="881c2-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="881c2-130">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="881c2-131">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="881c2-132">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="881c2-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="881c2-133">Geben Sie „TaxiFarePrediction“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

1. <span data-ttu-id="881c2-134">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset und die Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="881c2-134">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="881c2-135">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-135">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="881c2-136">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="881c2-136">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="881c2-137">Installieren Sie das NuGet-Paket **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="881c2-137">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="881c2-138">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-138">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="881c2-139">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, wählen Sie das Paket in der Liste aus, und klicken Sie anschließend auf die Schaltfläche **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="881c2-139">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="881c2-140">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="881c2-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="881c2-141">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="881c2-141">Prepare and understand the data</span></span>

1. <span data-ttu-id="881c2-142">Laden Sie die Datasets [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) und [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*.</span><span class="sxs-lookup"><span data-stu-id="881c2-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="881c2-143">Diese Datasets werden zum Trainieren des Machine Learning-Modells und zum anschließenden Auswerten der Genauigkeit des Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="881c2-143">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="881c2-144">Diese Datasets stammen ursprünglich aus dem [Dataset „NYC TLC Taxi Trip“](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="881c2-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="881c2-145">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die „\*.csv“-Dateien, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-145">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="881c2-146">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="881c2-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="881c2-147">Öffnen Sie das Dataset **taxi-fare-train.csv**, und sehen Sie sich die Spaltenheader in der ersten Zeile an.</span><span class="sxs-lookup"><span data-stu-id="881c2-147">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="881c2-148">Sehen Sie sich jede der Spalten an.</span><span class="sxs-lookup"><span data-stu-id="881c2-148">Take a look at each of the columns.</span></span> <span data-ttu-id="881c2-149">Machen Sie sich mit den Daten vertraut, und entscheiden Sie, welche Spalten **Features** sind, und welche Spalte die **Bezeichnung** ist.</span><span class="sxs-lookup"><span data-stu-id="881c2-149">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="881c2-150">Die **Bezeichnung** ist der Bezeichner der Spalte, die Sie vorhersagen möchten.</span><span class="sxs-lookup"><span data-stu-id="881c2-150">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="881c2-151">Die angegebenen **Features** werden verwendet, um die Bezeichnung vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="881c2-151">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="881c2-152">Das angegebene Dataset enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="881c2-152">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="881c2-153">**vendor_id:** Die ID des Taxiunternehmers ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="881c2-153">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="881c2-154">**rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="881c2-154">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="881c2-155">**passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="881c2-155">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="881c2-156">**trip_time_in_secs:** Die Dauer der Fahrt.</span><span class="sxs-lookup"><span data-stu-id="881c2-156">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="881c2-157">Der Fahrpreis soll vorhergesagt werden, bevor die Fahrt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="881c2-157">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="881c2-158">Zu diesem Zeitpunkt wissen Sie noch nicht, wie lange die Fahrt dauert.</span><span class="sxs-lookup"><span data-stu-id="881c2-158">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="881c2-159">Deshalb ist die Fahrtzeit kein Feature, und Sie müssen diese Spalte aus dem Modell ausschließen.</span><span class="sxs-lookup"><span data-stu-id="881c2-159">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="881c2-160">**trip_distance:** Die Fahrtstrecke ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="881c2-160">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="881c2-161">**payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="881c2-161">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="881c2-162">**fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="881c2-162">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="881c2-163">Erstellen von Datenklassen</span><span class="sxs-lookup"><span data-stu-id="881c2-163">Create data classes</span></span>

<span data-ttu-id="881c2-164">Erstellen Sie Klassen für die Eingabedaten und die Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="881c2-164">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="881c2-165">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-165">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="881c2-166">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="881c2-166">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="881c2-167">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-167">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="881c2-168">Fügen Sie der Formularklasse die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-168">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="881c2-169">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `TaxiTrip` und `TaxiTripFarePrediction` der Datei *TaxiTrip.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-169">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="881c2-170">`TaxiTrip` ist die Eingabedatenklasse und verfügt über Definitionen für jede der Datasetspalten.</span><span class="sxs-lookup"><span data-stu-id="881c2-170">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="881c2-171">Verwenden Sie das <xref:Microsoft.ML.Data.LoadColumnAttribute>-Attribut, um die Indizes der Quellspalten im Dataset festzulegen.</span><span class="sxs-lookup"><span data-stu-id="881c2-171">Use the <xref:Microsoft.ML.Data.LoadColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="881c2-172">Die Klasse `TaxiTripFarePrediction` stellt die vorhergesagten Ergebnisse dar.</span><span class="sxs-lookup"><span data-stu-id="881c2-172">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="881c2-173">Sie verfügt über ein einzelnes Feld für einen Gleitkommawert (`FareAmount`) mit einem angewendeten `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="881c2-173">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="881c2-174">Für die Regressionsaufgabe enthält die Spalte **Score** die vorhergesagten Bezeichnungswerte.</span><span class="sxs-lookup"><span data-stu-id="881c2-174">In case of the regression task the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="881c2-175">Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="881c2-175">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="881c2-176">Definieren von Daten und Modellpfaden</span><span class="sxs-lookup"><span data-stu-id="881c2-176">Define data and model paths</span></span>

<span data-ttu-id="881c2-177">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-177">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="881c2-178">Sie müssen drei Felder erstellen, die die Pfade zu den Dateien mit Datasets und der Datei zum Speichern des Modells enthalten:</span><span class="sxs-lookup"><span data-stu-id="881c2-178">You need to create three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="881c2-179">`_trainDataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="881c2-179">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="881c2-180">`_testDataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Evaluieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="881c2-180">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="881c2-181">`_modelPath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="881c2-181">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="881c2-182">Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben, und für die `_textLoader`-Variable:</span><span class="sxs-lookup"><span data-stu-id="881c2-182">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="881c2-183">Beim Erstellen eines Modells mit ML.NET erstellen Sie zunächst einen ML Context.</span><span class="sxs-lookup"><span data-stu-id="881c2-183">When building a model with ML.NET you start by creating an ML Context.</span></span> <span data-ttu-id="881c2-184">Dies ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="881c2-184">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="881c2-185">Die Umgebung bietet einen Kontext für Ihren Machine Learning-Job, der für die Verfolgung und Protokollierung von Ausnahmen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="881c2-185">The environment provides a context for your machine learning job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="881c2-186">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="881c2-186">Initialize variables in Main</span></span>

<span data-ttu-id="881c2-187">Erstellen Sie eine Variable namens `mlContext`, und initialisieren Sie sie mit einer neuen `MLContext`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="881c2-187">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="881c2-188">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="881c2-188">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="881c2-189">Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode zum Aufruf der `Train`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="881c2-189">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

<span data-ttu-id="881c2-190">Die `Train`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="881c2-190">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="881c2-191">Laden der Daten.</span><span class="sxs-lookup"><span data-stu-id="881c2-191">Loads the data.</span></span>
* <span data-ttu-id="881c2-192">Extrahieren und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="881c2-192">Extracts and transforms the data.</span></span>
* <span data-ttu-id="881c2-193">Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="881c2-193">Trains the model.</span></span>
* <span data-ttu-id="881c2-194">Speichern des Modells als ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="881c2-194">Saves the model as .zip file.</span></span>
* <span data-ttu-id="881c2-195">Zurückgeben des Modells.</span><span class="sxs-lookup"><span data-stu-id="881c2-195">Returns the model.</span></span>

<span data-ttu-id="881c2-196">Die `Train`-Methode trainiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="881c2-196">The `Train` method trains the model.</span></span> <span data-ttu-id="881c2-197">Erstellen Sie die Methode direkt unter `Main` mit folgendem Code:</span><span class="sxs-lookup"><span data-stu-id="881c2-197">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="881c2-198">Wir übergeben zwei Parameter an die `Train`-Methode: einen `MLContext` für den Kontext (`mlContext`) und eine Zeichenfolge für den Datasetpfad (`dataPath`).</span><span class="sxs-lookup"><span data-stu-id="881c2-198">We are passing two parameters into the `Train` method; an `MLContext` for the context (`mlContext`), and a string for the dataset path (`dataPath`).</span></span> <span data-ttu-id="881c2-199">Wir werden diese Methode zum Laden von Datasets erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="881c2-199">We're going to reuse this method for loading datasets.</span></span>

## <a name="load-and-transform-data"></a><span data-ttu-id="881c2-200">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="881c2-200">Load and transform data</span></span>

<span data-ttu-id="881c2-201">Laden Sie die Daten mithilfe des `MLContext.Data.LoadFromTextFile`-Wrappers für die [LoadFromTextFile-Methode](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span><span class="sxs-lookup"><span data-stu-id="881c2-201">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="881c2-202">Zurückgegeben wird ein <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="881c2-202">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span>

<span data-ttu-id="881c2-203">Als Ein- und Ausgabe von `Transforms` ist ein `DataView` der grundlegende Datenpipelinetyp, vergleichbar mit `IEnumerable` für `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="881c2-203">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="881c2-204">In ML.NET ähneln die Daten einer SQL-Ansicht.</span><span class="sxs-lookup"><span data-stu-id="881c2-204">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="881c2-205">Sie werden verzögert ausgewertet, sind schematisiert und heterogen.</span><span class="sxs-lookup"><span data-stu-id="881c2-205">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="881c2-206">Das Objekt ist der erste Teil der Pipeline und lädt die Daten.</span><span class="sxs-lookup"><span data-stu-id="881c2-206">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="881c2-207">Für dieses Tutorial wird ein Dataset mit Preisinformationen zu den Taxifahrten geladen.</span><span class="sxs-lookup"><span data-stu-id="881c2-207">For this tutorial, it loads a dataset with taxi trip pricing information.</span></span> <span data-ttu-id="881c2-208">Damit wird das Modell erstellt und trainiert.</span><span class="sxs-lookup"><span data-stu-id="881c2-208">This is used to create the model, and train it.</span></span>

<span data-ttu-id="881c2-209">Fügen Sie den folgenden Code am Ende der ersten Zeile der `Train`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="881c2-209">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

<span data-ttu-id="881c2-210">In den nächsten Schritten werden die Spalten mit den jeweiligen in der `TaxiTrip`-Klasse definierten Namen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="881c2-210">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="881c2-211">Wenn das Modell trainiert und ausgewertet wurde, gelten die Werte in der Spalte **Label** standardmäßig als richtige Werte, die vorhergesagt werden.</span><span class="sxs-lookup"><span data-stu-id="881c2-211">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="881c2-212">Da der Fahrpreis der Taxifahrt vorhergesagt werden soll, kopieren Sie die Spalte `FareAmount` in die Spalte **Label**.</span><span class="sxs-lookup"><span data-stu-id="881c2-212">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="881c2-213">Verwenden Sie hierzu die `CopyColumnsEstimator`-Transformationsklasse, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-213">To do that, use the `CopyColumnsEstimator` transformation class, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="881c2-214">Da der Algorithmus, der das Modell trainiert, **numerische** Features erfordert, müssen Sie die kategorischen Datenwerte (`VendorId`, `RateCode` und `PaymentType`) in Zahlen transformieren (`VendorIdEncoded`, `RateCodeEncoded` und `PaymentTypeEncoded`).</span><span class="sxs-lookup"><span data-stu-id="881c2-214">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers (`VendorIdEncoded`, `RateCodeEncoded`, and `PaymentTypeEncoded`).</span></span> <span data-ttu-id="881c2-215">Verwenden Sie hierzu die Microsoft.ML.Transforms.OneHotEncodingTransformer-Transformationsklasse, die verschiedenen Werten in den Spalten verschiedene numerische Schlüsselwerte zuordnet, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-215">To do that, use the Microsoft.ML.Transforms.OneHotEncodingTransformer> transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="881c2-216">Im letzten Schritt der Vorbereitung der Daten werden alle Feature-Spalten mithilfe der Transformationsklasse `mlContext.Transforms.Concatenate` in die Spalte **Features** kombiniert.</span><span class="sxs-lookup"><span data-stu-id="881c2-216">The last step in data preparation combines all of the feature columns into the **Features** column using the `mlContext.Transforms.Concatenate` transformation class.</span></span> <span data-ttu-id="881c2-217">Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**.</span><span class="sxs-lookup"><span data-stu-id="881c2-217">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="881c2-218">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-218">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="881c2-219">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="881c2-219">Choose a learning algorithm</span></span>

<span data-ttu-id="881c2-220">Nach dem Hinzufügen von Daten zur Pipeline und dem Transformieren in das richtige Eingabeformat wählen wir einen Lernalgorithmus (**Lernmodul**) aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-220">After adding the data to the pipeline and transforming it into the correct input format, we select a learning algorithm (**learner**).</span></span> <span data-ttu-id="881c2-221">Das Lernmodul trainiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="881c2-221">The learner trains the model.</span></span> <span data-ttu-id="881c2-222">Da wir für dieses Problem eine **Regressionsaufgabe** ausgewählt haben, verwenden wir ein `FastTreeRegressionTrainer`-Lernmodul. Dies ist ein von ML.NET bereitgestelltes Regressionslernmodul.</span><span class="sxs-lookup"><span data-stu-id="881c2-222">We chose a **regression** task for this problem, so we use a `FastTreeRegressionTrainer` learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="881c2-223">Der `FastTreeRegressionTrainer`-Trainingsalgorithmus nutzt Gradient Boosting.</span><span class="sxs-lookup"><span data-stu-id="881c2-223">The `FastTreeRegressionTrainer` training algorithm utilizes gradient boosting.</span></span> <span data-ttu-id="881c2-224">Gradient Boosting ist eine Machine Learning-Technik für Regressionsprobleme.</span><span class="sxs-lookup"><span data-stu-id="881c2-224">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="881c2-225">Sie erstellt jede Regressionsstruktur schrittweise.</span><span class="sxs-lookup"><span data-stu-id="881c2-225">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="881c2-226">Sie verwendet eine vordefinierte Verlustfunktion, um den Fehler in jedem Schritt zu messen und im nächsten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="881c2-226">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="881c2-227">Das Ergebnis ist ein Vorhersagemodell, das sich im Grunde aus schwächeren Vorhersagemodellen zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="881c2-227">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="881c2-228">Weitere Informationen zu Gradient Boosting finden Sie unter [Boosted-Entscheidungsstrukturregression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span><span class="sxs-lookup"><span data-stu-id="881c2-228">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="881c2-229">Fügen Sie den folgenden Code in die `Train`-Methode ein, um den `FastTreeRegressionTrainer` dem im vorherigen Schritt hinzugefügten Datenverarbeitungscode hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="881c2-229">Add the following code into the `Train` method to add the `FastTreeRegressionTrainer` to the data processing code added in the previous step:</span></span>

[!code-csharp[FastTreeRegressionTrainer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="881c2-230">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="881c2-230">Train the model</span></span>

<span data-ttu-id="881c2-231">Der letzte Schritt ist das Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="881c2-231">The final step is to train the model.</span></span> <span data-ttu-id="881c2-232">Wir trainieren das Modell <xref:Microsoft.ML.Data.TransformerChain> basierend auf dem Dataset, das geladen und transformiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="881c2-232">We train the model, <xref:Microsoft.ML.Data.TransformerChain>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="881c2-233">Sobald die Schätzung definiert ist, trainieren wir das Modell mit <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> und stellen die bereits geladenen Trainingsdaten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="881c2-233">Once the estimator has been defined, we train the model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="881c2-234">Damit wird ein Modell zurückgegeben, das für Vorhersagen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="881c2-234">This returns a model to use for predictions.</span></span> <span data-ttu-id="881c2-235">`pipeline.Fit()` trainiert die Pipeline und gibt einen `Transformer` basierend auf der eingegebenen `DataView` zurück.</span><span class="sxs-lookup"><span data-stu-id="881c2-235">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="881c2-236">Das Experiment wird erst ausgeführt, wenn dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="881c2-236">The experiment is not executed until this happens.</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

### <a name="save-the-model"></a><span data-ttu-id="881c2-237">Speichern des Modells</span><span class="sxs-lookup"><span data-stu-id="881c2-237">Save the model</span></span>

<span data-ttu-id="881c2-238">An diesem Punkt haben Sie ein Modell vom Typ <xref:Microsoft.ML.Data.TransformerChain>, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="881c2-238">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="881c2-239">Fügen Sie folgenden Code am Ende der `Train`-Methode hinzu, um das Modell in einer ZIP-Datei zu speichern:</span><span class="sxs-lookup"><span data-stu-id="881c2-239">To save the model to a .zip file, add the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="881c2-240">Speichern des Modells als ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="881c2-240">Save the model as a .zip file</span></span>

<span data-ttu-id="881c2-241">Erstellen Sie die `SaveModelAsFile`-Methode mit dem folgenden Code direkt nach der `Train`-Methode:</span><span class="sxs-lookup"><span data-stu-id="881c2-241">Create the `SaveModelAsFile` method, just after the `Train` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="881c2-242">Die `SaveModelAsFile`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="881c2-242">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="881c2-243">Speichern des Modells als ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="881c2-243">Saves the model as a .zip file.</span></span>

<span data-ttu-id="881c2-244">Wir müssen eine Methode zum Speichern des Modells erstellen, damit es wiederverwendet und in anderen Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="881c2-244">We need to create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="881c2-245">Der `ITransformer` enthält eine <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>-Methode mit dem globalen Feld `_modelPath` und einem <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="881c2-245">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="881c2-246">Da wir diesen als ZIP-Datei speichern möchten, erstellen wir den `FileStream` unmittelbar vor dem Aufruf der `SaveTo`-Methode.</span><span class="sxs-lookup"><span data-stu-id="881c2-246">Since we want to save this as a zip file, we'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="881c2-247">Fügen Sie der `SaveModelAsFile`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-247">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

<span data-ttu-id="881c2-248">Wir könnten auch anzeigen, wo die Datei geschrieben wurde, indem wir mit dem folgenden Code eine Konsolenmeldung mit dem `_modelPath` schreiben:</span><span class="sxs-lookup"><span data-stu-id="881c2-248">We could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a><span data-ttu-id="881c2-249">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="881c2-249">Evaluate the model</span></span>

<span data-ttu-id="881c2-250">Mit der Auswertung wird überprüft, wie gut das Modell Bezeichnungswerte vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="881c2-250">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="881c2-251">Es ist wichtig, dass das Modell gute Vorhersagen zu Daten trifft, die nicht zum Trainieren des Modells verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="881c2-251">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="881c2-252">Eine Möglichkeit hierfür ist es, die Daten wie in diesem Tutorial in Trainings- und Testdatasets aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="881c2-252">One way to do this is to split the data into training and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="881c2-253">Da Sie nun das Modell anhand der Trainingsdaten trainiert haben, können Sie prüfen, wie gut es mit den Testdaten arbeitet.</span><span class="sxs-lookup"><span data-stu-id="881c2-253">Now that you've trained the model on the training data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="881c2-254">Die Methode `Evaluate` wertet das Modell aus.</span><span class="sxs-lookup"><span data-stu-id="881c2-254">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="881c2-255">Fügen Sie den folgenden Code unter der `Train`-Methode hinzu, um die Methode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="881c2-255">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="881c2-256">Die `Evaluate`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="881c2-256">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="881c2-257">Laden des Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="881c2-257">Loads the test dataset.</span></span>
* <span data-ttu-id="881c2-258">Erstellen des Regressionsauswerters.</span><span class="sxs-lookup"><span data-stu-id="881c2-258">Creates the regression evaluator.</span></span>
* <span data-ttu-id="881c2-259">Evaluieren des Modells und Erstellen von Metriken.</span><span class="sxs-lookup"><span data-stu-id="881c2-259">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="881c2-260">Anzeigen der Metriken.</span><span class="sxs-lookup"><span data-stu-id="881c2-260">Displays the metrics.</span></span>

<span data-ttu-id="881c2-261">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Train`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-261">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="881c2-262">Laden Sie das Testdataset mit dem `MLContext.Data.LoadFromTextFile`-Wrapper.</span><span class="sxs-lookup"><span data-stu-id="881c2-262">Load the test dataset using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="881c2-263">Sie können das Modell unter Verwendung dieses Datasets in Form einer Qualitätsüberprüfung evaluieren.</span><span class="sxs-lookup"><span data-stu-id="881c2-263">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="881c2-264">Fügen Sie der `Evaluate`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-264">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="881c2-265">Verwenden Sie als nächstes den Machine Learning-Parameter `model` (einen Transformator), um die Features einzugeben und die Vorhersagen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="881c2-265">Next, use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="881c2-266">Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-266">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="881c2-267">Die `RegressionContext.Evaluate`-Methode berechnet die Qualitätsmetriken für das `PredictionModel` mit dem angegebenen Dataset.</span><span class="sxs-lookup"><span data-stu-id="881c2-267">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="881c2-268">Das zurückgegebene <xref:Microsoft.ML.Data.RegressionMetrics>-Objekt enthält alle von Regressionsauswertern berechneten Metriken.</span><span class="sxs-lookup"><span data-stu-id="881c2-268">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span> <span data-ttu-id="881c2-269">Um diese zur Bestimmung der Qualität des Modells anzuzeigen, müssen Sie die Metriken zuerst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="881c2-269">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="881c2-270">Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-270">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="881c2-271">Fügen Sie den folgenden Code hinzu, um das Modell zu evaluieren und die Auswertungsmetriken zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="881c2-271">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="881c2-272">[RSquared](../resources/glossary.md#coefficient-of-determination) ist eine weitere Auswertungsmetrik der Regressionsmodelle.</span><span class="sxs-lookup"><span data-stu-id="881c2-272">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="881c2-273">RSquared akzeptiert Werte zwischen 0 (null) und 1.</span><span class="sxs-lookup"><span data-stu-id="881c2-273">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="881c2-274">Je näher der Wert an 1 liegt, desto besser ist das Modell.</span><span class="sxs-lookup"><span data-stu-id="881c2-274">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="881c2-275">Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RSquared-Wert anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="881c2-275">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="881c2-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) ist eine der Auswertungsmetriken aus dem Regressionsmodell.</span><span class="sxs-lookup"><span data-stu-id="881c2-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="881c2-277">Je niedriger sie ausfällt, desto besser ist das Modell.</span><span class="sxs-lookup"><span data-stu-id="881c2-277">The lower it is, the better the model is.</span></span> <span data-ttu-id="881c2-278">Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu, um den RMS-Wert anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="881c2-278">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="881c2-279">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="881c2-279">Use the model for predictions</span></span>

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="881c2-280">Vorhersagen der Testdatenergebnissen mit dem Modell und einem einzelnen Kommentar</span><span class="sxs-lookup"><span data-stu-id="881c2-280">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="881c2-281">Erstellen Sie die `TestSinglePrediction`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:</span><span class="sxs-lookup"><span data-stu-id="881c2-281">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

<span data-ttu-id="881c2-282">Die `TestSinglePrediction`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="881c2-282">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="881c2-283">Erstellen eines einzelnen Kommentars aus Testdaten.</span><span class="sxs-lookup"><span data-stu-id="881c2-283">Creates a single comment of test data.</span></span>
* <span data-ttu-id="881c2-284">Vorhersagen des Fahrpreisbetrags anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="881c2-284">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="881c2-285">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="881c2-285">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="881c2-286">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="881c2-286">Displays the predicted results.</span></span>

<span data-ttu-id="881c2-287">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-287">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="881c2-288">Da wir das Modell aus der ZIP-Datei laden möchten, erstellen wir den `FileStream` unmittelbar vor dem Aufruf der `Load`-Methode.</span><span class="sxs-lookup"><span data-stu-id="881c2-288">Since we want to load the model from the zip file we saved, we'll create the `FileStream` immediately before calling the `Load` method.</span></span> <span data-ttu-id="881c2-289">Fügen Sie der `TestSinglePrediction`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-289">Add the following code to the `TestSinglePrediction` method as the next line:</span></span>

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

<span data-ttu-id="881c2-290">Das `model` ist ein `transformer`, der auf vielen Datenzeilen arbeitet, doch die Notwendigkeit, Vorhersagen für einzelne Beispiele zu treffen, ist ein sehr gängiges Produktionsszenario.</span><span class="sxs-lookup"><span data-stu-id="881c2-290">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="881c2-291"><xref:Microsoft.ML.PredictionEngine%602> ist ein Wrapper, der von der `CreatePredictionEngine`-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="881c2-291">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="881c2-292">Fügen Sie den folgenden Code hinzu, um `PredictionEngine` als nächste Zeile in der `TestSinglePrediction`-Methode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="881c2-292">Let's add the following code to create the `PredictionEngine` as the next line in the `TestSinglePrediction` Method:</span></span>

[!code-csharp[MakePredictionEngine](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]

<span data-ttu-id="881c2-293">Dieses Tutorial verwendet eine Testfahrt innerhalb dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="881c2-293">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="881c2-294">Sie können später weitere Szenarios zum Experimentieren mit dem Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="881c2-294">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="881c2-295">Fügen Sie eine Fahrt hinzu, um die Kostenvorhersage des trainierten Modells in der `TestSinglePrediction`-Methode zu testen, indem Sie eine `TaxiTrip`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="881c2-295">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

<span data-ttu-id="881c2-296">Wir können hiermit den Fahrpreis basierend auf einer einzelnen Instanz der Taxifahrtdaten vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="881c2-296">We can use that to predict the fare based on a single instance of the taxi trip data.</span></span> <span data-ttu-id="881c2-297">Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten.</span><span class="sxs-lookup"><span data-stu-id="881c2-297">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="881c2-298">Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst.</span><span class="sxs-lookup"><span data-stu-id="881c2-298">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="881c2-299">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="881c2-299">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="881c2-300">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="881c2-300">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="881c2-301">Um den vorhergesagten Preis der angegebenen Fahrt anzuzeigen, fügen Sie den folgenden Code der `TestSinglePrediction`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="881c2-301">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="881c2-302">Führen Sie das Programm aus, um den vorhergesagten Taxifahrtpreis für den Testfall anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="881c2-302">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="881c2-303">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="881c2-303">Congratulations!</span></span> <span data-ttu-id="881c2-304">Hiermit haben Sie ein Machine Learning-Modell erfolgreich zum Vorhersagen von Taxifahrtpreisen erstellt, die Genauigkeit ausgewertet und es zum Vorhersagen der Preise verwendet.</span><span class="sxs-lookup"><span data-stu-id="881c2-304">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="881c2-305">Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="881c2-305">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="881c2-306">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="881c2-306">Next steps</span></span>

<span data-ttu-id="881c2-307">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="881c2-307">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="881c2-308">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="881c2-308">Understand the problem</span></span>
> * <span data-ttu-id="881c2-309">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="881c2-309">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="881c2-310">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="881c2-310">Prepare and understand the data</span></span>
> * <span data-ttu-id="881c2-311">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="881c2-311">Create a learning pipeline</span></span>
> * <span data-ttu-id="881c2-312">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="881c2-312">Load and transform the data</span></span>
> * <span data-ttu-id="881c2-313">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="881c2-313">Choose a learning algorithm</span></span>
> * <span data-ttu-id="881c2-314">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="881c2-314">Train the model</span></span>
> * <span data-ttu-id="881c2-315">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="881c2-315">Evaluate the model</span></span>
> * <span data-ttu-id="881c2-316">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="881c2-316">Use the model for predictions</span></span>

<span data-ttu-id="881c2-317">Fahren Sie mit dem nächsten Tutorial fort, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="881c2-317">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="881c2-318">Iris-Clustering</span><span class="sxs-lookup"><span data-stu-id="881c2-318">Iris clustering</span></span>](iris-clustering.md)
