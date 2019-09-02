---
title: Vorhersagen von Preisen per Regression mit dem Modell-Generator
description: In diesem Tutorial wird veranschaulicht, wie mit dem ML.NET-Modell-Generator ein Regressionsmodell für die Vorhersage von Preisen für Taxifahrten in New York City erstellt wird.
author: luisquintanilla
ms.author: luquinta
ms.date: 07/15/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 1bdbe31e16408da2d7dfe17941c90a022f3d8c32
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107143"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="061f1-103">Vorhersagen von Preisen per Regression mit dem Modell-Generator</span><span class="sxs-lookup"><span data-stu-id="061f1-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="061f1-104">Hier erfahren Sie, wie Sie mit dem ML.NET-Modellgenerator ein Regressionsmodells für Preisvorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="061f1-104">Learn how to use ML.NET Model Builder to build a regression model() to predict prices.</span></span>  <span data-ttu-id="061f1-105">Die .NET Konsolenanwendung, die Sie in diesem Tutorial entwickeln, sagt Taxipreise basierend auf historischen Taxipreisdaten aus New York vorher.</span><span class="sxs-lookup"><span data-stu-id="061f1-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="061f1-106">Die Preisvorhersagevorlage des Modell-Generators kann für jedes Szenario verwendet werden, das einen numerischen Vorhersagewert erfordert.</span><span class="sxs-lookup"><span data-stu-id="061f1-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="061f1-107">Beispielszenarien sind: Vorhersagen des Hauspreises oder der Nachfrage und Umsatzprognosen.</span><span class="sxs-lookup"><span data-stu-id="061f1-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="061f1-108">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="061f1-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="061f1-109">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="061f1-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="061f1-110">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="061f1-110">Choose a scenario</span></span>
> - <span data-ttu-id="061f1-111">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="061f1-111">Load the data</span></span>
> - <span data-ttu-id="061f1-112">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="061f1-112">Train the model</span></span>
> - <span data-ttu-id="061f1-113">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="061f1-113">Evaluate the model</span></span>
> - <span data-ttu-id="061f1-114">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="061f1-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="061f1-115">Der Modell-Generator befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="061f1-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="061f1-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="061f1-116">Pre-requisites</span></span>

<span data-ttu-id="061f1-117">Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie in der [Installationsanleitung für den Modell-Generator](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="061f1-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="061f1-118">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="061f1-118">Create a console application</span></span>

1. <span data-ttu-id="061f1-119">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TaxiFarePrediction“.</span><span class="sxs-lookup"><span data-stu-id="061f1-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="061f1-120">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="061f1-120">Prepare and understand the data</span></span>

1. <span data-ttu-id="061f1-121">Erstellen Sie ein Verzeichnis mit dem Namen *Daten* in Ihrem Projekt, um die Datasetdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="061f1-121">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="061f1-122">Das Dataset zum Trainieren und Bewerten des Machine Learning-Modells stammt ursprünglich aus dem Dataset „NYC TLC Taxi Trip“.</span><span class="sxs-lookup"><span data-stu-id="061f1-122">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    <span data-ttu-id="061f1-123">Navigieren Sie zum Herunterladen des Datasets zum [Downloadlink für „taxi-fare-train.csv“](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span><span class="sxs-lookup"><span data-stu-id="061f1-123">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    <span data-ttu-id="061f1-124">Klicken Sie mit der rechten Maustaste auf die geladene Seite, und wählen Sie **Speichern unter** aus.</span><span class="sxs-lookup"><span data-stu-id="061f1-124">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    <span data-ttu-id="061f1-125">Speichern Sie die Datei über das Dialogfeld **Speichern unter** im Ordner *Daten*, den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="061f1-125">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="061f1-126">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *taxi-fare-train.csv*, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="061f1-126">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="061f1-127">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="061f1-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="061f1-128">Jede Zeile im Dataset `taxi-fare-train.csv` enthält Details zu den Fahrten eines Taxis.</span><span class="sxs-lookup"><span data-stu-id="061f1-128">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="061f1-129">Öffnen Sie das Dataset **taxi-fare-train.csv**.</span><span class="sxs-lookup"><span data-stu-id="061f1-129">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="061f1-130">Das angegebene Dataset enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="061f1-130">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="061f1-131">**vendor_id:** Die ID des Taxiunternehmers ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="061f1-131">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="061f1-132">**rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="061f1-132">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="061f1-133">**passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="061f1-133">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="061f1-134">**trip_time_in_secs:** Die Dauer der Fahrt.</span><span class="sxs-lookup"><span data-stu-id="061f1-134">**trip_time_in_secs:** The amount of time the trip took.</span></span>
    - <span data-ttu-id="061f1-135">**trip_distance:** Die Fahrtstrecke ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="061f1-135">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="061f1-136">**payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="061f1-136">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="061f1-137">**fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="061f1-137">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="061f1-138">`label` ist die Spalte, die vorhergesagt werden soll.</span><span class="sxs-lookup"><span data-stu-id="061f1-138">The `label` is the column you want to predict.</span></span> <span data-ttu-id="061f1-139">Das Ziel bei der Durchführung einer Regressionsaufgabe ist die Vorhersage eines numerischen Werts.</span><span class="sxs-lookup"><span data-stu-id="061f1-139">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="061f1-140">In diesem Preisvorhersageszenario werden die Kosten für eine Taxifahrt vorhergesagt.</span><span class="sxs-lookup"><span data-stu-id="061f1-140">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="061f1-141">Daher lautet die Bezeichnung **fare_amount**.</span><span class="sxs-lookup"><span data-stu-id="061f1-141">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="061f1-142">Die identifizierten `features` sind die Eingaben, die Sie für das Modell zum Vorhersagen von `label` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="061f1-142">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="061f1-143">In diesem Fall werden die restlichen Spalten als Features oder Eingaben verwendet, um den Fahrpreis vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="061f1-143">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="061f1-144">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="061f1-144">Choose a scenario</span></span>

<span data-ttu-id="061f1-145">Um Ihr Modell zu trainieren, wählen Sie ein Szenario aus der Liste der vom Modell-Generator bereitgestellten verfügbaren Machine Learning-Szenarien aus.</span><span class="sxs-lookup"><span data-stu-id="061f1-145">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="061f1-146">In diesem Fall handelt es sich um das Szenario `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="061f1-146">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="061f1-147">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*, und wählen Sie **Hinzufügen** > **Machine Learning** aus.</span><span class="sxs-lookup"><span data-stu-id="061f1-147">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="061f1-148">Wählen Sie im Schritt „Szenario“ des Modell-Generator-Tools das Szenario *Price Prediction* aus.</span><span class="sxs-lookup"><span data-stu-id="061f1-148">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="061f1-149">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="061f1-149">Load the data</span></span>

<span data-ttu-id="061f1-150">Der Modellgenerator akzeptiert Daten aus zwei Quellen: aus einer SQL Server-Datenbank oder aus einer lokalen Datei im CSV- oder TSV-Format.</span><span class="sxs-lookup"><span data-stu-id="061f1-150">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="061f1-151">Wählen Sie im Schritt „Daten“ des Modell-Generator-Tools die Option *Datei* aus der Dropdownliste „Datenquelle“ aus.</span><span class="sxs-lookup"><span data-stu-id="061f1-151">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="061f1-152">Wählen Sie die Schaltfläche neben dem Textfeld *Datei auswählen*, und verwenden Sie den Datei-Explorer, um die Datei *taxi-fare-test.csv* im Verzeichnis *Daten* zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="061f1-152">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="061f1-153">Wählen Sie *fare_amount* in der Dropdownliste *Bezeichnung oder Spalte für die Vorhersage* aus, und navigieren Sie zum Schritt „Trainieren“ des Modell-Generator-Tools.</span><span class="sxs-lookup"><span data-stu-id="061f1-153">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="061f1-154">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="061f1-154">Train the model</span></span>

<span data-ttu-id="061f1-155">Die in diesem Tutorial zum Trainieren des Preisvorhersagemodells verwendete Machine Learning-Aufgabe ist die Regression.</span><span class="sxs-lookup"><span data-stu-id="061f1-155">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="061f1-156">Während des Modelltrainings trainiert der Modell-Generator einzelne Modelle mit verschiedenen Regressionsalgorithmen und Einstellungen, um das leistungsfähigste Modell für Ihr Dataset zu finden.</span><span class="sxs-lookup"><span data-stu-id="061f1-156">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="061f1-157">Die Zeit, die für das Trainieren des Modells benötigt wird, ist proportional zur Datenmenge.</span><span class="sxs-lookup"><span data-stu-id="061f1-157">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="061f1-158">Verwenden Sie diese Tabelle als Orientierungshilfe, um einen geeigneten Wert für das Feld `Time to train (seconds)` auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="061f1-158">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="061f1-159">\*Datasetgröße</span><span class="sxs-lookup"><span data-stu-id="061f1-159">\*Dataset Size</span></span>  | <span data-ttu-id="061f1-160">Datasettyp</span><span class="sxs-lookup"><span data-stu-id="061f1-160">Dataset Type</span></span>       | <span data-ttu-id="061f1-161">Durchschn. Trainingszeit\*</span><span class="sxs-lookup"><span data-stu-id="061f1-161">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="061f1-162">0 bis 10 MB</span><span class="sxs-lookup"><span data-stu-id="061f1-162">0 - 10 Mb</span></span>     | <span data-ttu-id="061f1-163">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="061f1-163">Numeric and Text</span></span>   | <span data-ttu-id="061f1-164">10 Sek.</span><span class="sxs-lookup"><span data-stu-id="061f1-164">10 sec</span></span>
<span data-ttu-id="061f1-165">10 bis 100 MB</span><span class="sxs-lookup"><span data-stu-id="061f1-165">10 - 100 Mb</span></span>   | <span data-ttu-id="061f1-166">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="061f1-166">Numeric and Text</span></span>   | <span data-ttu-id="061f1-167">10 Min.</span><span class="sxs-lookup"><span data-stu-id="061f1-167">10 min</span></span>
<span data-ttu-id="061f1-168">100 bis 500 MB</span><span class="sxs-lookup"><span data-stu-id="061f1-168">100 - 500 Mb</span></span>  | <span data-ttu-id="061f1-169">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="061f1-169">Numeric and Text</span></span>   | <span data-ttu-id="061f1-170">30 Min.</span><span class="sxs-lookup"><span data-stu-id="061f1-170">30 min</span></span>
<span data-ttu-id="061f1-171">500 MB bis 1 GB</span><span class="sxs-lookup"><span data-stu-id="061f1-171">500 - 1 Gb</span></span>    | <span data-ttu-id="061f1-172">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="061f1-172">Numeric and Text</span></span>   | <span data-ttu-id="061f1-173">60 Min.</span><span class="sxs-lookup"><span data-stu-id="061f1-173">60 min</span></span>
<span data-ttu-id="061f1-174">1 GB+</span><span class="sxs-lookup"><span data-stu-id="061f1-174">1 Gb+</span></span>         | <span data-ttu-id="061f1-175">Numerisch und Text</span><span class="sxs-lookup"><span data-stu-id="061f1-175">Numeric and Text</span></span>   | <span data-ttu-id="061f1-176">3 Stunden +</span><span class="sxs-lookup"><span data-stu-id="061f1-176">3 hour+</span></span>

1. <span data-ttu-id="061f1-177">Da die Trainingsdatendatei mehr als 10 MB umfasst, verwenden Sie 600 Sekunden (10 Minuten) als Wert für *Trainingszeit (Sekunden)* .</span><span class="sxs-lookup"><span data-stu-id="061f1-177">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="061f1-178">Wählen Sie *Training starten* aus.</span><span class="sxs-lookup"><span data-stu-id="061f1-178">Select *Start Training*.</span></span>

<span data-ttu-id="061f1-179">Während des gesamten Trainingsprozesses werden die Fortschrittsdaten im Abschnitt `Progress` des Schritts „Trainieren“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="061f1-179">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="061f1-180">„Status“ zeigt den Abschlussstatus des Trainingsprozesses an.</span><span class="sxs-lookup"><span data-stu-id="061f1-180">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="061f1-181">„Beste Genauigkeit“ zeigt die Genauigkeit des leistungsfähigsten Modells, das bisher vom Modell-Generator gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="061f1-181">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="061f1-182">Eine höhere Genauigkeit bedeutet, dass die Vorhersage des Modells anhand der Testdaten präziser ist.</span><span class="sxs-lookup"><span data-stu-id="061f1-182">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="061f1-183">„Bester Algorithmus“ zeigt den Namen des leistungsfähigsten Algorithmus an, der bisher vom Modell-Generator gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="061f1-183">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="061f1-184">„Letzter Algorithmus“ zeigt den Namen des Algorithmus an, der zuletzt vom Modell-Generator zum Trainieren des Modells verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="061f1-184">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="061f1-185">Navigieren Sie nach Abschluss des Trainings zum Schritt „Evaluieren“.</span><span class="sxs-lookup"><span data-stu-id="061f1-185">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="061f1-186">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="061f1-186">Evaluate the model</span></span>

<span data-ttu-id="061f1-187">Das Ergebnis des Schritts „Trainieren“ ist ein Modell mit der besten Leistung.</span><span class="sxs-lookup"><span data-stu-id="061f1-187">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="061f1-188">Der Schritt „Evaluieren“ des Modell-Generator-Tools, der Ausgabebereich, enthält den Algorithmus, der vom leistungsfähigsten Modell im Eintrag *Bestes Modell* verwendet wird, sowie Metriken in *Beste Modellqualität (RSquared)* .</span><span class="sxs-lookup"><span data-stu-id="061f1-188">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="061f1-189">Außerdem finden Sie hier eine Übersichtstabelle mit den fünf besten Modellen und deren Metriken.</span><span class="sxs-lookup"><span data-stu-id="061f1-189">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="061f1-190">Wenn Sie mit Ihren Genauigkeitsmetriken nicht zufrieden sind, gibt es einige einfache Möglichkeiten, die Modellgenauigkeit zu verbessern. Dazu müssen Sie die Zeit für das Training des Modells erhöhen oder mehr Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="061f1-190">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="061f1-191">Navigieren Sie andernfalls zum Codeschritt.</span><span class="sxs-lookup"><span data-stu-id="061f1-191">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="061f1-192">Hinzufügen des Codes für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="061f1-192">Add the code to make predictions</span></span>

<span data-ttu-id="061f1-193">Das Ergebnis des Trainings sind zwei Projekte.</span><span class="sxs-lookup"><span data-stu-id="061f1-193">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="061f1-194">TaxiFarePredictionML.ConsoleApp: Eine .NET Core-Konsolenanwendung, die den Modelltrainings- und Verbrauchscode enthält.</span><span class="sxs-lookup"><span data-stu-id="061f1-194">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="061f1-195">TaxiFarePredictionML.Model: Eine .NET-Standardklassenbibliothek, die die Datenmodelle enthält, die das Schema der Eingabe- und Ausgabemodelldaten sowie die persistente Version des leistungsfähigsten Modells während des Trainings definieren.</span><span class="sxs-lookup"><span data-stu-id="061f1-195">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="061f1-196">Wählen Sie im Codeschritt des Modellgenerators die Option **Projekte hinzufügen** aus, um der Projektmappe die automatisch generierten Projekte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="061f1-196">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="061f1-197">Klicken Sie mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="061f1-197">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="061f1-198">Klicken Sie dann auf **Hinzufügen > Verweis**.</span><span class="sxs-lookup"><span data-stu-id="061f1-198">Then, **Add > Reference**.</span></span> <span data-ttu-id="061f1-199">Wählen Sie den Knoten **Projekte > Projektmappe** aus der Liste, aktivieren Sie das Kontrollkästchen für das Projekt *TaxiFarePredictionML.Model*, und wählen Sie „OK“ aus.</span><span class="sxs-lookup"><span data-stu-id="061f1-199">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>
1. <span data-ttu-id="061f1-200">Öffnen Sie die Datei *Program.cs* im Projekt *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="061f1-200">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="061f1-201">Fügen Sie die folgenden using-Anweisungen hinzu, um auf das NuGet-Paket *Microsoft.ML* und auf das Projekt *TaxiFarePredictionML.Model* zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="061f1-201">Add the following using statements to reference the *Microsoft.ML* NuGet package and *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

1. <span data-ttu-id="061f1-202">Fügen Sie der Klasse `Program` zur Klasse `ConsumeModel` hinzu.</span><span class="sxs-lookup"><span data-stu-id="061f1-202">Add the `ConsumeModel` method to the `Program` class.</span></span>

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

    <span data-ttu-id="061f1-203">`ConsumeModel` lädt das trainierte Modell, erstellt eine Vorhersageengine ([`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)) für das Modell und verwendet sie, um Vorhersagen für neue Daten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="061f1-203">The `ConsumeModel` will load the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and use it to make predictions on new data.</span></span>

1. <span data-ttu-id="061f1-204">Erstellen Sie eine neue Instanz der Klasse `ModelInput`, und verwenden Sie die Methode `ConsumeModel`, um unter Verwendung des Modells eine Vorhersage für neue Daten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="061f1-204">To make a prediction on new data using the model, create a new instance of the `ModelInput` class and use the `ConsumeModel` method.</span></span> <span data-ttu-id="061f1-205">Beachten Sie, dass der Fahrpreis nicht Teil der Eingabe ist.</span><span class="sxs-lookup"><span data-stu-id="061f1-205">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="061f1-206">Das liegt daran, dass das Modell die Vorhersage dafür generiert.</span><span class="sxs-lookup"><span data-stu-id="061f1-206">This is because the model will generate the prediction for it.</span></span> <span data-ttu-id="061f1-207">Fügen Sie der Methode `Main` den folgenden Code hinzu, und führen Sie die Anwendung aus:</span><span class="sxs-lookup"><span data-stu-id="061f1-207">Add the following code to the `Main` method and run the application</span></span>

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

    <span data-ttu-id="061f1-208">Die vom Programm generierte Ausgabe sollte wie der folgende Ausschnitt aussehen:</span><span class="sxs-lookup"><span data-stu-id="061f1-208">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="061f1-209">Wenn Sie zu einem späteren Zeitpunkt innerhalb einer anderen Projektmappe auf die generierten Projekte verweisen müssen, finden Sie diese im Verzeichnis `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="061f1-209">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="061f1-210">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="061f1-210">Next Steps</span></span>

<span data-ttu-id="061f1-211">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="061f1-211">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="061f1-212">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="061f1-212">Prepare and understand the data</span></span>
> - <span data-ttu-id="061f1-213">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="061f1-213">Choose a scenario</span></span>
> - <span data-ttu-id="061f1-214">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="061f1-214">Load the data</span></span>
> - <span data-ttu-id="061f1-215">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="061f1-215">Train the model</span></span>
> - <span data-ttu-id="061f1-216">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="061f1-216">Evaluate the model</span></span>
> - <span data-ttu-id="061f1-217">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="061f1-217">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="061f1-218">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="061f1-218">Additional Resources</span></span>

<span data-ttu-id="061f1-219">Weitere Informationen zu den in diesem Tutorial erwähnten Themen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="061f1-219">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="061f1-220">Szenarien für den Modellgenerator</span><span class="sxs-lookup"><span data-stu-id="061f1-220">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="061f1-221">Regression</span><span class="sxs-lookup"><span data-stu-id="061f1-221">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="061f1-222">Metriken für Regression</span><span class="sxs-lookup"><span data-stu-id="061f1-222">Regression Model Metrics</span></span>](../resources/metrics.md#metrics-for-regression)
- [<span data-ttu-id="061f1-223">Dataset „NYC TLC Taxi Trip“</span><span class="sxs-lookup"><span data-stu-id="061f1-223">NYC TLC Taxi Trip data set</span></span>](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)
