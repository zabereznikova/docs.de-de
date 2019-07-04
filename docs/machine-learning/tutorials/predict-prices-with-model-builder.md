---
title: Vorhersagen von Preisen per Regression mit dem Modell-Generator
description: In diesem Tutorial wird veranschaulicht, wie mit dem ML.NET-Modell-Generator ein Regressionsmodell für die Vorhersage von Preisen für Taxifahrten in New York City erstellt wird.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: db9788e3065a0f2f21d712b2d4826efea2d8a829
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410578"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="4b1b8-103">Vorhersagen von Preisen per Regression mit dem Modell-Generator</span><span class="sxs-lookup"><span data-stu-id="4b1b8-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="4b1b8-104">Erfahren Sie, wie Sie mit dem ML.NET-Modell-Generator ein [Regressionsmodells](../resources/glossary.md#regression) für Preisvorhersagen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-104">Learn how to use ML.NET Model Builder to build a [regression model](../resources/glossary.md#regression) to predict prices.</span></span>  <span data-ttu-id="4b1b8-105">Die .NET Konsolenanwendung, die Sie in diesem Tutorial entwickeln, sagt Taxipreise basierend auf historischen Taxipreisdaten aus New York vorher.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="4b1b8-106">Die Preisvorhersagevorlage des Modell-Generators kann für jedes Szenario verwendet werden, das einen numerischen Vorhersagewert erfordert.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="4b1b8-107">Beispielszenarien sind: Vorhersagen des Hauspreises oder der Nachfrage und Umsatzprognosen.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="4b1b8-108">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="4b1b8-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="4b1b8-109">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="4b1b8-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="4b1b8-110">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="4b1b8-110">Choose a scenario</span></span>
> * <span data-ttu-id="4b1b8-111">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="4b1b8-111">Load the data</span></span>
> * <span data-ttu-id="4b1b8-112">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4b1b8-112">Train the model</span></span>
> * <span data-ttu-id="4b1b8-113">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4b1b8-113">Evaluate the model</span></span>
> * <span data-ttu-id="4b1b8-114">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="4b1b8-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="4b1b8-115">Der Modell-Generator befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="4b1b8-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4b1b8-116">Pre-requisites</span></span>

<span data-ttu-id="4b1b8-117">Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie in der [Installationsanleitung für den Modell-Generator](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4b1b8-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="4b1b8-118">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="4b1b8-118">Create a console application</span></span>

1. <span data-ttu-id="4b1b8-119">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TaxiFarePrediction“.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="4b1b8-120">Installieren Sie das NuGet-Paket **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="4b1b8-120">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="4b1b8-121">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf *TaxiFarePrediction*, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-121">In **Solution Explorer**, right-click the *TaxiFarePrediction* project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="4b1b8-122">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-122">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="4b1b8-123">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="4b1b8-124">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="4b1b8-124">Prepare and understand the data</span></span>

1. <span data-ttu-id="4b1b8-125">Erstellen Sie ein Verzeichnis mit dem Namen *Daten* in Ihrem Projekt, um die Datasetdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-125">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="4b1b8-126">Laden Sie das Dataset [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) herunter und speichern Sie es im Ordner *Daten*, den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-126">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) data set and save it to the *Data* folder you created at the previous step.</span></span> <span data-ttu-id="4b1b8-127">Dieses Dataset wird zum Trainieren und Evaluieren des Machine Learning-Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-127">This data set is used to train and evaluate the machine learning model.</span></span> <span data-ttu-id="4b1b8-128">Dieses Dataset stammt ursprünglich aus dem [Dataset „NYC TLC Taxi Trip“](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="4b1b8-128">This data set is originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="4b1b8-129">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *taxi-fare-train.csv*, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-129">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="4b1b8-130">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-130">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="4b1b8-131">Jede Zeile im Dataset `taxi-fare-train.csv` enthält Details zu den Fahrten eines Taxis.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-131">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span> 

1. <span data-ttu-id="4b1b8-132">Öffnen Sie das Dataset **taxi-fare-train.csv**.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-132">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="4b1b8-133">Das angegebene Dataset enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="4b1b8-133">The provided data set contains the following columns:</span></span>

    * <span data-ttu-id="4b1b8-134">**vendor_id:** Die ID des Taxiunternehmers ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    * <span data-ttu-id="4b1b8-135">**rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    * <span data-ttu-id="4b1b8-136">**passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    * <span data-ttu-id="4b1b8-137">**trip_time_in_secs:** Die Dauer der Fahrt.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="4b1b8-138">Der Fahrpreis soll vorhergesagt werden, bevor die Fahrt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="4b1b8-139">Zu diesem Zeitpunkt wissen Sie noch nicht, wie lange die Fahrt dauert.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-139">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="4b1b8-140">Deshalb ist die Fahrtzeit kein Feature, und Sie müssen diese Spalte aus dem Modell ausschließen.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    * <span data-ttu-id="4b1b8-141">**trip_distance:** Die Fahrtstrecke ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-141">**trip_distance:** The distance of the trip is a feature.</span></span>
    * <span data-ttu-id="4b1b8-142">**payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    * <span data-ttu-id="4b1b8-143">**fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="4b1b8-144">`label` ist die Spalte, die vorhergesagt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-144">The `label` is the column you want to predict.</span></span> <span data-ttu-id="4b1b8-145">Das Ziel bei der Durchführung einer Regressionsaufgabe ist die Vorhersage eines numerischen Werts.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-145">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="4b1b8-146">In diesem Preisvorhersageszenario werden die Kosten für eine Taxifahrt vorhergesagt.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-146">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="4b1b8-147">Daher lautet die Bezeichnung **fare_amount**.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-147">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="4b1b8-148">Die identifizierten `features` sind die Eingaben, die Sie für das Modell zum Vorhersagen von `label` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-148">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="4b1b8-149">In diesem Fall werden die restlichen Spalten als Features oder Eingaben verwendet, um den Fahrpreis vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-149">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="4b1b8-150">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="4b1b8-150">Choose a scenario</span></span>

<span data-ttu-id="4b1b8-151">Um Ihr Modell zu trainieren, wählen Sie ein Szenario aus der Liste der vom Modell-Generator bereitgestellten verfügbaren Machine Learning-Szenarien aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-151">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="4b1b8-152">In diesem Fall handelt es sich um das Szenario `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-152">In this case, the scenario is `Price Prediction`.</span></span> <span data-ttu-id="4b1b8-153">Eine ausführlichere Liste finden Sie im [Übersichtsartikel zum Modell-Generator](../automate-training-with-model-builder.md#scenarios).</span><span class="sxs-lookup"><span data-stu-id="4b1b8-153">For a more extensive list visit the [Model Builder overview article](../automate-training-with-model-builder.md#scenarios).</span></span>

1. <span data-ttu-id="4b1b8-154">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*, und wählen Sie **Hinzufügen** > **Machine Learning** aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-154">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="4b1b8-155">Wählen Sie im Schritt „Szenario“ des Modell-Generator-Tools das Szenario *Price Prediction* aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-155">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="4b1b8-156">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="4b1b8-156">Load the data</span></span>

<span data-ttu-id="4b1b8-157">Der Modell-Generator akzeptiert Daten aus zwei Quellen: eine SQL Server-Datenbank oder eine lokalen csv- oder tsv-Datei.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-157">Model Builder accepts data from two sources, a SQL Server database or a local file csv or tsv file.</span></span> <span data-ttu-id="4b1b8-158">Weitere Informationen zu Anforderungen an das Datenformat finden Sie auf über den folgenden [Link](../how-to-guides/install-model-builder.md#limitations).</span><span class="sxs-lookup"><span data-stu-id="4b1b8-158">For more information on data format requirements, visit the following [link](../how-to-guides/install-model-builder.md#limitations).</span></span>

1. <span data-ttu-id="4b1b8-159">Wählen Sie im Schritt „Daten“ des Modell-Generator-Tools die Option *Datei* aus der Dropdownliste „Datenquelle“ aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-159">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="4b1b8-160">Wählen Sie die Schaltfläche neben dem Textfeld *Datei auswählen*, und verwenden Sie den Datei-Explorer, um die Datei *taxi-fare-test.csv* im Verzeichnis *Daten* zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-160">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="4b1b8-161">Wählen Sie *fare_amount* in der Dropdownliste *Bezeichnung oder Spalte für die Vorhersage* aus, und navigieren Sie zum Schritt „Trainieren“ des Modell-Generator-Tools.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-161">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="4b1b8-162">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4b1b8-162">Train the model</span></span>

<span data-ttu-id="4b1b8-163">Die in diesem Tutorial zum Trainieren des Preisvorhersagemodells verwendete Machine Learning-Aufgabe ist die Regression.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-163">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="4b1b8-164">Während des Modelltrainings trainiert der Modell-Generator einzelne Modelle mit verschiedenen Regressionsalgorithmen und Einstellungen, um das leistungsfähigste Modell für Ihr Dataset zu finden.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-164">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="4b1b8-165">Die Zeit, die für das Trainieren des Modells benötigt wird, ist proportional zur Datenmenge.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-165">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="4b1b8-166">Verwenden Sie diese Tabelle als Orientierungshilfe, um einen geeigneten Wert für das Feld `Time to train (seconds)` auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="4b1b8-166">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="4b1b8-167">\*Datasetgröße</span><span class="sxs-lookup"><span data-stu-id="4b1b8-167">\*Dataset Size</span></span>  | <span data-ttu-id="4b1b8-168">Datasettyp</span><span class="sxs-lookup"><span data-stu-id="4b1b8-168">Dataset Type</span></span>       | <span data-ttu-id="4b1b8-169">Durchschn. Trainingszeit\*</span><span class="sxs-lookup"><span data-stu-id="4b1b8-169">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="4b1b8-170">0 bis 10 MB</span><span class="sxs-lookup"><span data-stu-id="4b1b8-170">0 - 10 Mb</span></span>     | <span data-ttu-id="4b1b8-171">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="4b1b8-171">Numeric and Text</span></span>   | <span data-ttu-id="4b1b8-172">10 Sek.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-172">10 sec</span></span>
<span data-ttu-id="4b1b8-173">10 bis 100 MB</span><span class="sxs-lookup"><span data-stu-id="4b1b8-173">10 - 100 Mb</span></span>   | <span data-ttu-id="4b1b8-174">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="4b1b8-174">Numeric and Text</span></span>   | <span data-ttu-id="4b1b8-175">10 Min.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-175">10 min</span></span>
<span data-ttu-id="4b1b8-176">100 bis 500 MB</span><span class="sxs-lookup"><span data-stu-id="4b1b8-176">100 - 500 Mb</span></span>  | <span data-ttu-id="4b1b8-177">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="4b1b8-177">Numeric and Text</span></span>   | <span data-ttu-id="4b1b8-178">30 Min.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-178">30 min</span></span>
<span data-ttu-id="4b1b8-179">500 MB bis 1 GB</span><span class="sxs-lookup"><span data-stu-id="4b1b8-179">500 - 1 Gb</span></span>    | <span data-ttu-id="4b1b8-180">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="4b1b8-180">Numeric and Text</span></span>   | <span data-ttu-id="4b1b8-181">60 Min.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-181">60 min</span></span>
<span data-ttu-id="4b1b8-182">1 GB+</span><span class="sxs-lookup"><span data-stu-id="4b1b8-182">1 Gb+</span></span>         | <span data-ttu-id="4b1b8-183">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="4b1b8-183">Numeric and Text</span></span>   | <span data-ttu-id="4b1b8-184">3 Stunden +</span><span class="sxs-lookup"><span data-stu-id="4b1b8-184">3 hour+</span></span>

1. <span data-ttu-id="4b1b8-185">Da die Trainingsdatendatei mehr als 10 MB umfasst, verwenden Sie 600 Sekunden (10 Minuten) als Wert für *Trainingszeit (Sekunden)* .</span><span class="sxs-lookup"><span data-stu-id="4b1b8-185">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="4b1b8-186">Wählen Sie *Training starten* aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-186">Select *Start Training*.</span></span>

<span data-ttu-id="4b1b8-187">Während des gesamten Trainingsprozesses werden die Fortschrittsdaten im Abschnitt `Progress` des Schritts „Trainieren“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-187">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="4b1b8-188">„Status“ zeigt den Abschlussstatus des Trainingsprozesses an.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-188">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="4b1b8-189">„Beste Genauigkeit“ zeigt die Genauigkeit des leistungsfähigsten Modells, das bisher vom Modell-Generator gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-189">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="4b1b8-190">Eine höhere Genauigkeit bedeutet, dass die Vorhersage des Modells anhand der Testdaten präziser ist.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-190">Higher accuracy means the model predicted more correctly on test data.</span></span> 
- <span data-ttu-id="4b1b8-191">„Bester Algorithmus“ zeigt den Namen des leistungsfähigsten Algorithmus an, der bisher vom Modell-Generator gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-191">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="4b1b8-192">„Letzter Algorithmus“ zeigt den Namen des Algorithmus an, der zuletzt vom Modell-Generator zum Trainieren des Modells verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-192">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="4b1b8-193">Navigieren Sie nach Abschluss des Trainings zum Schritt „Evaluieren“.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-193">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="4b1b8-194">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4b1b8-194">Evaluate the model</span></span>

<span data-ttu-id="4b1b8-195">Das Ergebnis des Schritts „Trainieren“ ist ein Modell mit der besten Leistung.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-195">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="4b1b8-196">Der Schritt „Evaluieren“ des Modell-Generator-Tools, der Ausgabebereich, enthält den Algorithmus, der vom leistungsfähigsten Modell im Eintrag *Bestes Modell* verwendet wird, sowie Metriken in *Beste Modellqualität (RSquared)* .</span><span class="sxs-lookup"><span data-stu-id="4b1b8-196">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="4b1b8-197">Außerdem finden Sie hier eine Übersichtstabelle mit den fünf besten Modellen und deren Metriken.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-197">Additionally, a summary table containing top five models and their metrics.</span></span> <span data-ttu-id="4b1b8-198">Klicken Sie auf den folgenden Link, um mehr über das [Evaluieren von Modellmetriken](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics) zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-198">Visit the following link to learn more about [evaluating model metrics](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span></span>

<span data-ttu-id="4b1b8-199">Wenn Sie mit Ihren Genauigkeitsmetriken nicht zufrieden sind, gibt es einige einfache Möglichkeiten, die Modellgenauigkeit zu verbessern. Dazu müssen Sie die Zeit für das Training des Modells erhöhen oder mehr Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-199">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="4b1b8-200">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="4b1b8-200">Use the model for predictions</span></span>

<span data-ttu-id="4b1b8-201">Das Ergebnis des Trainings sind zwei Projekte.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-201">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="4b1b8-202">TaxiFarePredictionML.ConsoleApp: Eine .NET-Konsolenanwendung, die den Modelltrainings- und Verbrauchscode enthält.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-202">TaxiFarePredictionML.ConsoleApp: A .NET Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="4b1b8-203">TaxiFarePredictionML.Model: Eine .NET-Standardklassenbibliothek, die die Datenmodelle enthält, die das Schema der Eingabe- und Ausgabemodelldaten sowie die persistente Version des leistungsfähigsten Modells während des Trainings definieren.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-203">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="4b1b8-204">Wählen Sie im Abschnitt „Code“ des Modell-Generator-Tools die Option **Hinzugefügte Projekte**, um die Projekte zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-204">In the code section of the Model Builder tool, select **Added Projects** to add the projects to the solution.</span></span>
1. <span data-ttu-id="4b1b8-205">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-205">In solution explorer, right-click the *TaxiFarePrediction* project.</span></span> <span data-ttu-id="4b1b8-206">Wählen Sie dann **Hinzufügen > Vorhandenes Element** aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-206">Then, select **Add > Existing Item**.</span></span> <span data-ttu-id="4b1b8-207">Wählen Sie dann in der Dropdownliste „Dateityp“ `All Files` aus, navigieren Sie zum Projektverzeichnis *TaxiFarePredictionML.Model*, und wählen Sie die Datei `MLModel.zip` aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-207">For file type drop down, select `All Files`, navigate to the *TaxiFarePredictionML.Model* project directory and select the `MLModel.zip` file.</span></span> <span data-ttu-id="4b1b8-208">Klicken Sie dann mit der rechten Maustaste auf die zuletzt hinzugefügte Datei `MLModel.zip`, und wählen Sie *Eigenschaften* aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-208">Then right-click the recently added `MLModel.zip` file and select *Properties*.</span></span> <span data-ttu-id="4b1b8-209">Wählen Sie für die Option „In Ausgabeverzeichnis kopieren“ in der Dropdownliste *Kopieren, wenn neuer* aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-209">For the Copy to Output Directory option, select *Copy if Newer* from the dropdown.</span></span>
1. <span data-ttu-id="4b1b8-210">Klicken Sie mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-210">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="4b1b8-211">Klicken Sie dann auf **Hinzufügen > Verweis**.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-211">Then, **Add > Reference**.</span></span> <span data-ttu-id="4b1b8-212">Wählen Sie den Knoten **Projekte > Projektmappe** aus der Liste, aktivieren Sie das Kontrollkästchen für das Projekt *TaxiFarePredictionML.Model*, und wählen Sie „OK“ aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-212">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>

4. <span data-ttu-id="4b1b8-213">Öffnen Sie die Datei *Program.cs* im Projekt *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-213">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
5. <span data-ttu-id="4b1b8-214">Fügen Sie die folgenden using-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="4b1b8-214">Add the following using statements:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. <span data-ttu-id="4b1b8-215">Fügen Sie der Klasse `Program` zur Klasse `ConsumeModel` hinzu.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-215">Add the `ConsumeModel` method to the `Program` class.</span></span> <span data-ttu-id="4b1b8-216">Das `ConsumeModel` erstellt eine `PredictionEngine` basierend auf dem vom Modell-Generator generierten Modell, um Vorhersagen für neue Daten zu treffen und diese an die Konsole auszugeben.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-216">The `ConsumeModel` will create a `PredictionEngine` based on the model generated by Model Builder to make predictions on new data and print them out to the console.</span></span>

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

7. <span data-ttu-id="4b1b8-217">Fügen Sie den folgenden Code zur Methode `Main` hinzu, und führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-217">Add the following code to the `Main` method and run the application.</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    <span data-ttu-id="4b1b8-218">Die vom Programm generierte Ausgabe sollte wie der folgende Ausschnitt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4b1b8-218">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="4b1b8-219">Wenn Sie zu einem späteren Zeitpunkt innerhalb einer anderen Projektmappe auf die generierten Projekte verweisen müssen, finden Sie diese im Verzeichnis `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-219">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4b1b8-220">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4b1b8-220">Next Steps</span></span>

<span data-ttu-id="4b1b8-221">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="4b1b8-221">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="4b1b8-222">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="4b1b8-222">Prepare and understand the data</span></span>
> * <span data-ttu-id="4b1b8-223">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="4b1b8-223">Choose a scenario</span></span>
> * <span data-ttu-id="4b1b8-224">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="4b1b8-224">Load the data</span></span>
> * <span data-ttu-id="4b1b8-225">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4b1b8-225">Train the model</span></span>
> * <span data-ttu-id="4b1b8-226">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4b1b8-226">Evaluate the model</span></span>
> * <span data-ttu-id="4b1b8-227">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="4b1b8-227">Use the model for predictions</span></span>

<span data-ttu-id="4b1b8-228">Lesen Sie einen der folgenden Anleitungsartikel, um zu erfahren, wie Sie Ihr Modell bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="4b1b8-228">Advance to either of the following how-to articles to learn how to deploy your model.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4b1b8-229">Bereitstellen des Modells für Azure Functions</span><span class="sxs-lookup"><span data-stu-id="4b1b8-229">Deploy a model to Azure Functions</span></span>](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="4b1b8-230">Bereitstellen eines Modells für eine Web-API</span><span class="sxs-lookup"><span data-stu-id="4b1b8-230">Deploy a model to a Web API</span></span>](../how-to-guides/serve-model-web-api-ml-net.md)
