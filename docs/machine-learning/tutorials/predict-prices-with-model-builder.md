---
title: 'Tutorial: Vorhersagen von Preisen per Regression mit dem Modell-Generator'
description: In diesem Tutorial wird veranschaulicht, wie mit dem ML.NET-Modell-Generator ein Regressionsmodell für die Vorhersage von Preisen für Taxifahrten in New York City erstellt wird.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.topic: tutorial
ms.custom: mvc, mlnet-tooling
ms.openlocfilehash: 750738f8e3c65363e9996667feeccd1b84391f9f
ms.sourcegitcommit: 2ff49dcf9ddf107d139b4055534681052febad62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2020
ms.locfileid: "80438247"
---
# <a name="tutorial-predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="f2f8e-103">Tutorial: Vorhersagen von Preisen per Regression mit dem Modell-Generator</span><span class="sxs-lookup"><span data-stu-id="f2f8e-103">Tutorial: Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="f2f8e-104">Hier erfahren Sie, wie Sie mit dem ML.NET-Modellgenerator ein Regressionsmodells für Preisvorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-104">Learn how to use ML.NET Model Builder to build a regression model to predict prices.</span></span>  <span data-ttu-id="f2f8e-105">Die .NET Konsolenanwendung, die Sie in diesem Tutorial entwickeln, sagt Taxipreise basierend auf historischen Taxipreisdaten aus New York vorher.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="f2f8e-106">Die Preisvorhersagevorlage des Modell-Generators kann für jedes Szenario verwendet werden, das einen numerischen Vorhersagewert erfordert.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="f2f8e-107">Beispielszenarien sind: Vorhersagen des Hauspreises oder der Nachfrage und Umsatzprognosen.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="f2f8e-108">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="f2f8e-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f2f8e-109">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="f2f8e-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="f2f8e-110">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="f2f8e-110">Choose a scenario</span></span>
> - <span data-ttu-id="f2f8e-111">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="f2f8e-111">Load the data</span></span>
> - <span data-ttu-id="f2f8e-112">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f2f8e-112">Train the model</span></span>
> - <span data-ttu-id="f2f8e-113">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f2f8e-113">Evaluate the model</span></span>
> - <span data-ttu-id="f2f8e-114">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="f2f8e-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="f2f8e-115">Der Modell-Generator befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="f2f8e-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f2f8e-116">Pre-requisites</span></span>

<span data-ttu-id="f2f8e-117">Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie in der [Installationsanleitung für den Modell-Generator](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f2f8e-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f2f8e-118">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="f2f8e-118">Create a console application</span></span>

1. <span data-ttu-id="f2f8e-119">Erstellen Sie eine **C# .NET Core-Konsolenanwendung** mit dem Namen „TaxiFarePrediction“.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-119">Create a **C# .NET Core Console Application** called "TaxiFarePrediction".</span></span> <span data-ttu-id="f2f8e-120">Stellen Sie sicher, dass die Option zum **Platzieren von Projektmappe und Projekt im selben Verzeichnis** **deaktiviert** (VS 2019) oder die Option **Verzeichnis für Projektmappe erstellen** **aktiviert** ist (VS 2017).</span><span class="sxs-lookup"><span data-stu-id="f2f8e-120">Make sure **Place solution and project in the same directory** is **unchecked** (VS 2019), or **Create directory for solution** is **checked** (VS 2017).</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="f2f8e-121">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="f2f8e-121">Prepare and understand the data</span></span>

1. <span data-ttu-id="f2f8e-122">Erstellen Sie ein Verzeichnis mit dem Namen *Daten* in Ihrem Projekt, um die Datasetdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-122">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="f2f8e-123">Das Dataset zum Trainieren und Bewerten des Machine Learning-Modells stammt ursprünglich aus dem Dataset „NYC TLC Taxi Trip“.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-123">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    1. <span data-ttu-id="f2f8e-124">Navigieren Sie zum Herunterladen des Datasets zum [Downloadlink für „taxi-fare-train.csv“](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span><span class="sxs-lookup"><span data-stu-id="f2f8e-124">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    1. <span data-ttu-id="f2f8e-125">Klicken Sie mit der rechten Maustaste auf die geladene Seite, und wählen Sie **Speichern unter** aus.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-125">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    1. <span data-ttu-id="f2f8e-126">Speichern Sie die Datei über das Dialogfeld **Speichern unter** im Ordner *Daten*, den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-126">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="f2f8e-127">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *taxi-fare-train.csv*, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-127">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="f2f8e-128">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-128">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="f2f8e-129">Jede Zeile im Dataset `taxi-fare-train.csv` enthält Details zu den Fahrten eines Taxis.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-129">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="f2f8e-130">Öffnen Sie das Dataset **taxi-fare-train.csv**.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-130">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="f2f8e-131">Das angegebene Dataset enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="f2f8e-131">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="f2f8e-132">**vendor_id:** Die ID des Taxiunternehmers ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-132">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="f2f8e-133">**rate_code:** Der Tariftyp der Taxifahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-133">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="f2f8e-134">**passenger_count:** Die Anzahl der Fahrgäste bei einer Fahrt ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-134">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="f2f8e-135">**trip_time_in_secs:** Die Dauer der Fahrt.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-135">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="f2f8e-136">Der Fahrpreis soll vorhergesagt werden, bevor die Fahrt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-136">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="f2f8e-137">Zu diesem Zeitpunkt wissen Sie noch nicht, wie lange die Fahrt dauert.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-137">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="f2f8e-138">Deshalb ist die Fahrtzeit kein Feature, und Sie müssen diese Spalte aus dem Modell ausschließen.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-138">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    - <span data-ttu-id="f2f8e-139">**trip_distance:** Die Fahrtstrecke ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-139">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="f2f8e-140">**payment_type:** Die Zahlungsmethode (Bargeld oder Kreditkarte) ist ein Feature.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-140">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="f2f8e-141">**fare_amount:** Der gesamte gezahlte Taxifahrtpreis ist die Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-141">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="f2f8e-142">`label` ist die Spalte, die vorhergesagt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-142">The `label` is the column you want to predict.</span></span> <span data-ttu-id="f2f8e-143">Das Ziel bei der Durchführung einer Regressionsaufgabe ist die Vorhersage eines numerischen Werts.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-143">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="f2f8e-144">In diesem Preisvorhersageszenario werden die Kosten für eine Taxifahrt vorhergesagt.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-144">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="f2f8e-145">Daher lautet die Bezeichnung **fare_amount**.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-145">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="f2f8e-146">Die identifizierten `features` sind die Eingaben, die Sie für das Modell zum Vorhersagen von `label` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-146">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="f2f8e-147">In diesem Fall werden die restlichen Spalten mit Ausnahme von **trip_time-in-secs** als Features oder Eingaben verwendet, um den Fahrpreis vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-147">In this case, the rest of the columns with the exception of **trip_time_in_secs** are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="f2f8e-148">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="f2f8e-148">Choose a scenario</span></span>

<span data-ttu-id="f2f8e-149">Um Ihr Modell zu trainieren, wählen Sie ein Szenario aus der Liste der vom Modell-Generator bereitgestellten verfügbaren Machine Learning-Szenarien aus.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-149">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="f2f8e-150">In diesem Fall handelt es sich um das Szenario `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-150">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="f2f8e-151">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *TaxiFarePrediction*, und wählen Sie **Hinzufügen** > **Machine Learning** aus.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-151">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="f2f8e-152">Wählen Sie im Schritt „Szenario“ des Modell-Generator-Tools das Szenario *Price Prediction* aus.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-152">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="f2f8e-153">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="f2f8e-153">Load the data</span></span>

<span data-ttu-id="f2f8e-154">Der Modellgenerator akzeptiert Daten aus zwei Quellen: aus einer SQL Server-Datenbank oder aus einer lokalen Datei im CSV- oder TSV-Format.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-154">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="f2f8e-155">Wählen Sie im Schritt „Daten“ des Modell-Generator-Tools die Option *Datei* aus der Dropdownliste „Datenquelle“ aus.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-155">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="f2f8e-156">Wählen Sie die Schaltfläche neben dem Textfeld *Datei auswählen*, und verwenden Sie den Datei-Explorer, um die Datei *taxi-fare-test.csv* im Verzeichnis *Daten* zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-156">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="f2f8e-157">Wählen Sie in der Dropdownliste *Column to Predict (Label)* (Vorherzusagende Spalte (Bezeichnung)) die Option *fare_amount* aus.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-157">Choose *fare_amount* in the *Column to Predict (Label)* dropdown.</span></span>
1. <span data-ttu-id="f2f8e-158">Erweitern Sie die Dropdownliste *Eingabespalten (Features)* , und deaktivieren Sie die Spalte *trip_time_in_secs*, um Sie während des Trainings als Feature auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-158">Expand the *Input Columns (Features)* dropdown and uncheck the *trip_time_in_secs* column to exclude it as a feature during training.</span></span>  <span data-ttu-id="f2f8e-159">Navigieren Sie zum Schritt „Trainieren“ des Modell-Generator-Tools.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-159">Navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="f2f8e-160">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f2f8e-160">Train the model</span></span>

<span data-ttu-id="f2f8e-161">Die in diesem Tutorial zum Trainieren des Preisvorhersagemodells verwendete Machine Learning-Aufgabe ist die Regression.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-161">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="f2f8e-162">Während des Modelltrainings trainiert der Modell-Generator einzelne Modelle mit verschiedenen Regressionsalgorithmen und Einstellungen, um das leistungsfähigste Modell für Ihr Dataset zu finden.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-162">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="f2f8e-163">Die Zeit, die für das Trainieren des Modells benötigt wird, ist proportional zur Datenmenge.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-163">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="f2f8e-164">Der Modell-Generator legt automatisch einen Standardwert für **Time to train (seconds)** (Trainingszeit (Sekunden)) basierend auf der Größe der Datenquelle fest.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-164">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="f2f8e-165">Ändern Sie den Standardwert für *Time to train (seconds)* (Trainingszeit (Sekunden)) nur, wenn Sie eine längere Trainingszeit angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-165">Leave the default value as is for *Time to train (seconds)* unless you prefer to train for a longer time.</span></span>
2. <span data-ttu-id="f2f8e-166">Wählen Sie *Training starten* aus.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-166">Select *Start Training*.</span></span>

<span data-ttu-id="f2f8e-167">Während des gesamten Trainingsprozesses werden die Fortschrittsdaten im Abschnitt `Progress` des Schritts „Trainieren“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-167">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="f2f8e-168">„Status“ zeigt den Abschlussstatus des Trainingsprozesses an.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-168">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="f2f8e-169">„Beste Genauigkeit“ zeigt die Genauigkeit des leistungsfähigsten Modells, das bisher vom Modell-Generator gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-169">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="f2f8e-170">Eine höhere Genauigkeit bedeutet, dass die Vorhersage des Modells anhand der Testdaten präziser ist.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-170">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="f2f8e-171">„Bester Algorithmus“ zeigt den Namen des leistungsfähigsten Algorithmus an, der bisher vom Modell-Generator gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-171">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="f2f8e-172">„Letzter Algorithmus“ zeigt den Namen des Algorithmus an, der zuletzt vom Modell-Generator zum Trainieren des Modells verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-172">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="f2f8e-173">Navigieren Sie nach Abschluss des Trainings zum Schritt „Evaluieren“.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-173">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="f2f8e-174">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f2f8e-174">Evaluate the model</span></span>

<span data-ttu-id="f2f8e-175">Das Ergebnis des Schritts „Trainieren“ ist ein Modell mit der besten Leistung.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-175">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="f2f8e-176">Der Schritt „Evaluieren“ des Modell-Generator-Tools, der Ausgabebereich, enthält den Algorithmus, der vom leistungsfähigsten Modell im Eintrag *Bestes Modell* verwendet wird, sowie Metriken in *Beste Modellqualität (RSquared)* .</span><span class="sxs-lookup"><span data-stu-id="f2f8e-176">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="f2f8e-177">Außerdem finden Sie hier eine Übersichtstabelle mit den fünf besten Modellen und deren Metriken.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-177">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="f2f8e-178">Wenn Sie mit Ihren Genauigkeitsmetriken nicht zufrieden sind, gibt es einige einfache Möglichkeiten, die Modellgenauigkeit zu verbessern. Dazu müssen Sie die Zeit für das Training des Modells erhöhen oder mehr Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-178">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="f2f8e-179">Navigieren Sie andernfalls zum Codeschritt.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-179">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="f2f8e-180">Hinzufügen des Codes für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="f2f8e-180">Add the code to make predictions</span></span>

<span data-ttu-id="f2f8e-181">Das Ergebnis des Trainings sind zwei Projekte.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-181">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="f2f8e-182">TaxiFarePredictionML.ConsoleApp: Eine .NET Core-Konsolenanwendung, die den Modelltrainings- und Beispielverbrauchscode enthält.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-182">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and sample consumption code.</span></span>
- <span data-ttu-id="f2f8e-183">TaxiFarePredictionML.Model: Eine .NET-Standardklassenbibliothek, die die Datenmodelle enthält, die das Schema der Eingabe- und Ausgabemodelldaten, die gespeicherte Version des leistungsfähigsten Modells während des Trainings sowie eine Hilfsklasse namens `ConsumeModel` definieren, um Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-183">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data, the saved version of the best performing model during training and a helper class called `ConsumeModel` to make predictions.</span></span>

1. <span data-ttu-id="f2f8e-184">Wählen Sie im Codeschritt des Modellgenerators die Option **Projekte hinzufügen** aus, um der Projektmappe die automatisch generierten Projekte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-184">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="f2f8e-185">Öffnen Sie die Datei *Program.cs* im Projekt *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-185">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="f2f8e-186">Fügen Sie die folgenden using-Anweisungen hinzu, um auf das Projekt *TaxiFarePredictionML.Model* zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="f2f8e-186">Add the following using statement to reference the *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using TaxiFarePredictionML.Model;
    ```

1. <span data-ttu-id="f2f8e-187">Um eine Vorhersage für neue Daten mithilfe des Modells zu erstellen, erstellen Sie eine neue Instanz der Klasse `ModelInput` innerhalb der `Main`-Methode Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-187">To make a prediction on new data using the model, create a new instance of the `ModelInput` class inside the `Main` method of your application.</span></span> <span data-ttu-id="f2f8e-188">Beachten Sie, dass der Fahrpreis nicht Teil der Eingabe ist.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-188">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="f2f8e-189">Das liegt daran, dass das Modell die Vorhersage dafür generiert.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-189">This is because the model will generate the prediction for it.</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };
    ```

1. <span data-ttu-id="f2f8e-190">Verwenden Sie die `Predict`-Methode aus der `ConsumeModel`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-190">Use the `Predict` method from the `ConsumeModel` class.</span></span> <span data-ttu-id="f2f8e-191">Die `Predict`-Methode lädt das trainierte Modell, erstellt eine Vorhersageengine ([`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)) für das Modell und verwendet sie, um Vorhersagen für neue Daten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-191">The `Predict` method loads the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and uses it to make predictions on new data.</span></span>

    ```csharp
    // Make prediction
    ModelOutput prediction = ConsumeModel.Predict(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

1. <span data-ttu-id="f2f8e-192">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-192">Run the application.</span></span>

    <span data-ttu-id="f2f8e-193">Die vom Programm generierte Ausgabe sollte wie der folgende Ausschnitt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f2f8e-193">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 14.96086
    ```

<span data-ttu-id="f2f8e-194">Wenn Sie zu einem späteren Zeitpunkt innerhalb einer anderen Projektmappe auf die generierten Projekte verweisen müssen, finden Sie diese im Verzeichnis `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="f2f8e-194">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f2f8e-195">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f2f8e-195">Next Steps</span></span>

<span data-ttu-id="f2f8e-196">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="f2f8e-196">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f2f8e-197">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="f2f8e-197">Prepare and understand the data</span></span>
> - <span data-ttu-id="f2f8e-198">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="f2f8e-198">Choose a scenario</span></span>
> - <span data-ttu-id="f2f8e-199">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="f2f8e-199">Load the data</span></span>
> - <span data-ttu-id="f2f8e-200">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f2f8e-200">Train the model</span></span>
> - <span data-ttu-id="f2f8e-201">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f2f8e-201">Evaluate the model</span></span>
> - <span data-ttu-id="f2f8e-202">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="f2f8e-202">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f2f8e-203">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f2f8e-203">Additional Resources</span></span>

<span data-ttu-id="f2f8e-204">Weitere Informationen zu den in diesem Tutorial erwähnten Themen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="f2f8e-204">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="f2f8e-205">Szenarien für den Modellgenerator</span><span class="sxs-lookup"><span data-stu-id="f2f8e-205">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenario)
- [<span data-ttu-id="f2f8e-206">Regression</span><span class="sxs-lookup"><span data-stu-id="f2f8e-206">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="f2f8e-207">Metriken für Regression</span><span class="sxs-lookup"><span data-stu-id="f2f8e-207">Regression Model Metrics</span></span>](../resources/metrics.md#evaluation-metrics-for-regression-and-recommendation)
- [<span data-ttu-id="f2f8e-208">Dataset „NYC TLC Taxi Trip“</span><span class="sxs-lookup"><span data-stu-id="f2f8e-208">NYC TLC Taxi Trip data set</span></span>](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
