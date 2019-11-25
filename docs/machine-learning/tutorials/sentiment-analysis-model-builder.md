---
title: 'Tutorial: Analysieren der Stimmung: binäre Klassifikation'
description: Dieses Tutorial zeigt Ihnen, wie Sie eine Razor Pages-Anwendung erstellen, die die Stimmung in Websitekommentaren klassifiziert und die entsprechenden Maßnahmen ergreift. Die binäre Standpunktklassifizierung verwendet den Modell-Generator in Visual Studio.
ms.date: 10/08/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 5e5b60a53db70b33ed798bcf33497b74911ba727
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974794"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a><span data-ttu-id="acc23-104">Tutorial: Analysieren der Stimmung von Websitekommentaren in einer Webanwendung mit dem Modell-Generator von ML.NET</span><span class="sxs-lookup"><span data-stu-id="acc23-104">Tutorial: Analyze sentiment of website comments in a web application using ML.NET Model Builder</span></span>

<span data-ttu-id="acc23-105">Erfahren Sie, wie Sie die Stimmung in Kommentaren in Echtzeit in einer Webanwendung analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="acc23-105">Learn how to analyze sentiment from comments in real-time inside a web application.</span></span>

<span data-ttu-id="acc23-106">Dieses Tutorial zeigt Ihnen, wie Sie eine ASP.NET Core Razor Pages-Anwendung erstellen, die die Stimmung in Websitekommentaren in Echtzeit klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="acc23-106">This tutorial shows you how to create an ASP.NET Core Razor Pages application that classifies sentiment from website comments in real-time.</span></span>

<span data-ttu-id="acc23-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="acc23-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="acc23-108">Erstellen einer ASP.NET Core Razor Pages-Anwendung</span><span class="sxs-lookup"><span data-stu-id="acc23-108">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="acc23-109">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="acc23-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="acc23-110">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="acc23-110">Choose a scenario</span></span>
> - <span data-ttu-id="acc23-111">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="acc23-111">Load the data</span></span>
> - <span data-ttu-id="acc23-112">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="acc23-112">Train the model</span></span>
> - <span data-ttu-id="acc23-113">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="acc23-113">Evaluate the model</span></span>
> - <span data-ttu-id="acc23-114">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="acc23-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="acc23-115">Der Modell-Generator befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="acc23-115">Model Builder is currently in Preview.</span></span>

<span data-ttu-id="acc23-116">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples).</span><span class="sxs-lookup"><span data-stu-id="acc23-116">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) repository.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="acc23-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="acc23-117">Pre-requisites</span></span>

<span data-ttu-id="acc23-118">Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie in der [Installationsanleitung für den Modell-Generator](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="acc23-118">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-razor-pages-application"></a><span data-ttu-id="acc23-119">Erstellen einer Razor Pages Anwendung</span><span class="sxs-lookup"><span data-stu-id="acc23-119">Create a Razor Pages application</span></span>

1. <span data-ttu-id="acc23-120">Erstellen Sie eine **ASP.NET Core Razor Pages-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="acc23-120">Create a **ASP.NET Core Razor Pages Application**.</span></span>

    1. <span data-ttu-id="acc23-121">Öffnen Sie Visual Studio, und wählen Sie **Datei -> Neu -> Projekt** in der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-121">Open Visual Studio and select **File > New > Project** from the menu bar.</span></span>
    1. <span data-ttu-id="acc23-122">Wählen Sie im Dialogfeld „Neues Projekt“ den Knoten **Visual C#** und anschließend den Knoten **Web** aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-122">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span>
    1. <span data-ttu-id="acc23-123">Wählen Sie dann die Projektvorlage **ASP.NET Core-Webanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-123">Then select the **ASP.NET Core Web Application** project template.</span></span>
    1. <span data-ttu-id="acc23-124">Geben Sie in das Textfeld **Name** den Namen „SentimentRazor“ ein.</span><span class="sxs-lookup"><span data-stu-id="acc23-124">In the **Name** text box, type "SentimentRazor".</span></span>
    1. <span data-ttu-id="acc23-125">Das Kontrollkästchen **Verzeichnis für Projektmappe erstellen** sollte standardmäßig aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="acc23-125">The **Create a directory for solution** checkbox should be checked by default.</span></span> <span data-ttu-id="acc23-126">Wenn dies nicht der Fall ist, aktivieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="acc23-126">If that's not the case, check it.</span></span>
    1. <span data-ttu-id="acc23-127">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="acc23-127">Select the **OK** button.</span></span>
    1. <span data-ttu-id="acc23-128">Wählen Sie im Fenster, das die verschiedenen Typen von ASP.NET Core-Projekten anzeigt, **Webanwendung** und dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-128">Choose **Web Application** in the window that displays the different types of ASP.NET Core Projects, and then select the **OK** button.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="acc23-129">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="acc23-129">Prepare and understand the data</span></span>

<span data-ttu-id="acc23-130">Laden Sie das [Wikipedia-detox-Dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv) herunter.</span><span class="sxs-lookup"><span data-stu-id="acc23-130">Download [Wikipedia detox dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span> <span data-ttu-id="acc23-131">Wenn die Webseite geöffnet wird, klicken Sie mit der rechten Maustaste auf die Seite, wählen Sie **Speichern unter** aus, und speichern Sie die Datei auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="acc23-131">When the webpage opens, right-click on the page, select **Save As** and save the file anywhere on your computer.</span></span>

<span data-ttu-id="acc23-132">Jede Zeile im Dataset *wikipedia-detox-250-line-data.tsv* stellt einen anderen Kommentar dar, der von einem Benutzer auf Wikipedia verfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="acc23-132">Each row in the *wikipedia-detox-250-line-data.tsv* dataset represents a different review left by a user on Wikipedia.</span></span> <span data-ttu-id="acc23-133">Die erste Spalte stellt die Stimmung des Texts dar (0 ist nicht toxisch, 1 ist toxisch), und die zweite Spalte stellt den Kommentar dar, den der Benutzer hinterlassen hat.</span><span class="sxs-lookup"><span data-stu-id="acc23-133">The first column represents the sentiment of the text (0 is non-toxic, 1 is toxic), and the second column represents the comment left by the user.</span></span> <span data-ttu-id="acc23-134">Die Spalten werden durch TAB getrennt.</span><span class="sxs-lookup"><span data-stu-id="acc23-134">The columns are separated by tabs.</span></span> <span data-ttu-id="acc23-135">Die Daten sehen folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="acc23-135">The data looks like the following:</span></span>

| <span data-ttu-id="acc23-136">Standpunkt</span><span class="sxs-lookup"><span data-stu-id="acc23-136">Sentiment</span></span> | <span data-ttu-id="acc23-137">SentimentText</span><span class="sxs-lookup"><span data-stu-id="acc23-137">SentimentText</span></span> |
| :---: | :---: |
<span data-ttu-id="acc23-138">1</span><span class="sxs-lookup"><span data-stu-id="acc23-138">1</span></span> | <span data-ttu-id="acc23-139">==RUDE== Dude, you are rude upload that carl picture back, or else.</span><span class="sxs-lookup"><span data-stu-id="acc23-139">==RUDE== Dude, you are rude upload that carl picture back, or else.</span></span>
<span data-ttu-id="acc23-140">1</span><span class="sxs-lookup"><span data-stu-id="acc23-140">1</span></span> | <span data-ttu-id="acc23-141">== OK!</span><span class="sxs-lookup"><span data-stu-id="acc23-141">== OK!</span></span> <span data-ttu-id="acc23-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span><span class="sxs-lookup"><span data-stu-id="acc23-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span></span>
<span data-ttu-id="acc23-143">0</span><span class="sxs-lookup"><span data-stu-id="acc23-143">0</span></span> | <span data-ttu-id="acc23-144">Ich hoffe, dass dies hilfreich ist.</span><span class="sxs-lookup"><span data-stu-id="acc23-144">I hope this helps.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="acc23-145">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="acc23-145">Choose a scenario</span></span>

![Modell-Generator-Assistent in Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

<span data-ttu-id="acc23-147">Um Ihr Modell zu trainieren, wählen Sie ein Szenario aus der Liste der vom Modell-Generator bereitgestellten verfügbaren Machine Learning-Szenarien aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-147">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span>

1. <span data-ttu-id="acc23-148">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *SentimentRazor*, und wählen Sie **Hinzufügen** > **Machine Learning** aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-148">In **Solution Explorer**, right-click the *SentimentRazor* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="acc23-149">Für dieses Beispiel ist das Szenario eine Stimmungsanalyse.</span><span class="sxs-lookup"><span data-stu-id="acc23-149">For this sample, the scenario is sentiment analysis.</span></span> <span data-ttu-id="acc23-150">Wählen Sie im Schritt *Szenario* des Modell-Generator-Tools das Szenario **Standpunktanalyse** aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-150">In the *scenario* step of the Model Builder tool, select the **Sentiment Analysis** scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="acc23-151">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="acc23-151">Load the data</span></span>

<span data-ttu-id="acc23-152">Der Modell-Generator akzeptiert Daten aus zwei Quellen: aus einer SQL Server-Datenbank oder aus einer lokalen Datei im `csv`- oder `tsv`-Format.</span><span class="sxs-lookup"><span data-stu-id="acc23-152">Model Builder accepts data from two sources, a SQL Server database or a local file in `csv` or `tsv` format.</span></span>

1. <span data-ttu-id="acc23-153">Wählen Sie im Schritt „Daten“ des Modell-Generator-Tools die Option **Datei** aus der Dropdownliste „Datenquelle“ aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-153">In the data step of the Model Builder tool, select **File** from the data source dropdown.</span></span>
1. <span data-ttu-id="acc23-154">Wählen Sie die Schaltfläche neben dem Textfeld **Datei auswählen** aus, und verwenden Sie den Datei-Explorer, um die Datei *wikipedia-detox-250-line-data.tsv* zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="acc23-154">Select the button next to the **Select a file** text box and use File Explorer to browse and select the *wikipedia-detox-250-line-data.tsv* file.</span></span>
1. <span data-ttu-id="acc23-155">Wählen Sie **Stimmung** aus der Dropdownliste **Vorherzusagende Spalte (Bezeichnung)** aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-155">Choose **Sentiment** in the **Column to Predict (Label)** dropdown.</span></span>
1. <span data-ttu-id="acc23-156">Behalten Sie die Standardwerte in der Dropdownliste **Eingabespalten (Features)** bei.</span><span class="sxs-lookup"><span data-stu-id="acc23-156">Leave the default values for the **Input Columns (Features)** dropdown.</span></span>
1. <span data-ttu-id="acc23-157">Wählen Sie den Link **Trainieren** aus, um zum nächsten Schritt im Modell-Generator-Tool zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="acc23-157">Select the **Train** link to move to the next step in the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="acc23-158">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="acc23-158">Train the model</span></span>

<span data-ttu-id="acc23-159">Die in diesem Tutorial zum Trainieren des Stimmungsanalysemodells verwendete Machine Learning-Aufgabe ist die binäre Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="acc23-159">The machine learning task used to train the sentiment analysis model in this tutorial is binary classification.</span></span> <span data-ttu-id="acc23-160">Während des Modelltrainings trainiert der Modell-Generator einzelne Modelle mit verschiedenen Algorithmen und Einstellungen für binäre Klassifizierung, um das leistungsfähigste Modell für Ihr Dataset zu finden.</span><span class="sxs-lookup"><span data-stu-id="acc23-160">During the model training process, Model Builder trains separate models using different binary classification algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="acc23-161">Die Zeit, die für das Trainieren des Modells benötigt wird, ist proportional zur Datenmenge.</span><span class="sxs-lookup"><span data-stu-id="acc23-161">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="acc23-162">Der Modell-Generator legt automatisch einen Standardwert für **Time to train (seconds)** (Trainingszeit (Sekunden)) basierend auf der Größe der Datenquelle fest.</span><span class="sxs-lookup"><span data-stu-id="acc23-162">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="acc23-163">Obwohl der Modell-Generator den Wert von **Trainingszeit (Sekunden)** auf 10 Sekunden festlegt, erhöhen Sie den Wert auf 30 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="acc23-163">Although Model Builder sets the value of **Time to train (seconds)** to 10 seconds, increase it to 30 seconds.</span></span> <span data-ttu-id="acc23-164">Ein längeres Training ermöglicht es dem Modell-Generator, eine größere Anzahl von Algorithmen und Kombinationen von Parametern auf der Suche nach dem besten Modell zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="acc23-164">Training for a longer period of time allows Model Builder to explore a larger number of algorithms and combination of parameters in search of the best model.</span></span>
1. <span data-ttu-id="acc23-165">Wählen Sie **Training starten** aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-165">Select **Start Training**.</span></span>

    <span data-ttu-id="acc23-166">Während des gesamten Trainingsprozesses werden die Fortschrittsdaten im Abschnitt `Progress` des Schritts „Trainieren“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="acc23-166">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

    - <span data-ttu-id="acc23-167">„Status“ zeigt den Abschlussstatus des Trainingsprozesses an.</span><span class="sxs-lookup"><span data-stu-id="acc23-167">Status displays the completion status of the training process.</span></span>
    - <span data-ttu-id="acc23-168">„Beste Genauigkeit“ zeigt die Genauigkeit des leistungsfähigsten Modells, das bisher vom Modell-Generator gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="acc23-168">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="acc23-169">Eine höhere Genauigkeit bedeutet, dass die Vorhersage des Modells anhand der Testdaten präziser ist.</span><span class="sxs-lookup"><span data-stu-id="acc23-169">Higher accuracy means the model predicted more correctly on test data.</span></span>
    - <span data-ttu-id="acc23-170">„Bester Algorithmus“ zeigt den Namen des leistungsfähigsten Algorithmus an, der bisher vom Modell-Generator gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="acc23-170">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
    - <span data-ttu-id="acc23-171">„Letzter Algorithmus“ zeigt den Namen des Algorithmus an, der zuletzt vom Modell-Generator zum Trainieren des Modells verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="acc23-171">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

1. <span data-ttu-id="acc23-172">Wählen Sie nach Abschluss des Trainings den Link **Evaluieren** aus, um mit dem nächsten Schritt fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="acc23-172">Once training is complete, select the **evaluate** link to move to the next step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="acc23-173">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="acc23-173">Evaluate the model</span></span>

<span data-ttu-id="acc23-174">Das Ergebnis des Schritts „Trainieren“ ist ein Modell mit der besten Leistung.</span><span class="sxs-lookup"><span data-stu-id="acc23-174">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="acc23-175">Der Schritt „Evaluieren“ des Modellgeneratortools, der Ausgabebereich, enthält den Algorithmus, der vom leistungsfähigsten Modell im Eintrag **Bestes Modell** verwendet wird, sowie Metriken in **Beste Modellgenauigkeit**.</span><span class="sxs-lookup"><span data-stu-id="acc23-175">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the **Best Model** entry along with metrics in **Best Model Accuracy**.</span></span> <span data-ttu-id="acc23-176">Außerdem finden Sie hier eine Übersichtstabelle mit den fünf besten Modellen und deren Metriken.</span><span class="sxs-lookup"><span data-stu-id="acc23-176">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="acc23-177">Wenn Sie mit Ihren Genauigkeitsmetriken nicht zufrieden sind, gibt es einige einfache Möglichkeiten, die Modellgenauigkeit zu verbessern. Dazu müssen Sie die Zeit für das Training des Modells erhöhen oder mehr Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="acc23-177">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="acc23-178">Wählen Sie andernfalls den Link **Code** aus, um zum letzten Schritt im Modell-Generator-Tool zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="acc23-178">Otherwise, select the **code** link to move to the final step in the Model Builder tool.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="acc23-179">Hinzufügen des Codes für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="acc23-179">Add the code to make predictions</span></span>

<span data-ttu-id="acc23-180">Das Ergebnis des Trainings sind zwei Projekte.</span><span class="sxs-lookup"><span data-stu-id="acc23-180">Two projects will be created as a result of the training process.</span></span>

### <a name="reference-the-trained-model"></a><span data-ttu-id="acc23-181">Verweisen auf das trainierte Modell</span><span class="sxs-lookup"><span data-stu-id="acc23-181">Reference the trained model</span></span>

1. <span data-ttu-id="acc23-182">Wählen Sie im Schritt *Code* des Modell-Generators die Option **Projekte hinzufügen** aus, um der Projektmappe die automatisch generierten Projekte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="acc23-182">In the *code* step of the Model Builder tool, select **Add Projects** to add the autogenerated projects to the solution.</span></span>

    <span data-ttu-id="acc23-183">Die folgenden Projekte sollten im **Projektmappen-Explorer** angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="acc23-183">The following projects should appear in the **Solution Explorer**:</span></span>

    - <span data-ttu-id="acc23-184">*SentimentRazorML.ConsoleApp*: Eine .NET Core-Konsolenanwendung, die den Modelltrainings- und Vorhersagecode enthält.</span><span class="sxs-lookup"><span data-stu-id="acc23-184">*SentimentRazorML.ConsoleApp*: A .NET Core Console application that contains the model training and prediction code.</span></span>
    - <span data-ttu-id="acc23-185">*SentimentRazorML.Model*: Eine .NET-Standardklassenbibliothek, die die Datenmodelle enthält, die das Schema der Eingabe- und Ausgabemodelldaten sowie die gespeicherte Version des leistungsfähigsten Modells während des Trainings definieren.</span><span class="sxs-lookup"><span data-stu-id="acc23-185">*SentimentRazorML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the saved version of the best performing model during training.</span></span>

    <span data-ttu-id="acc23-186">Für dieses Tutorial wird nur das Projekt *SentimentRazorML.Model* verwendet, da Vorhersagen in der Webanwendung *SentimentRazor* und nicht in der Konsole getroffen werden.</span><span class="sxs-lookup"><span data-stu-id="acc23-186">For this tutorial, only the *SentimentRazorML.Model* project is used because predictions will be made in the *SentimentRazor* web application rather than in the console.</span></span> <span data-ttu-id="acc23-187">Obwohl die *SentimentRazorML.ConsoleApp* nicht für die Bewertung verwendet wird, kann sie verwendet werden, um das Modell zu einem späteren Zeitpunkt mit neuen Daten erneut zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="acc23-187">Although the *SentimentRazorML.ConsoleApp* won't be used for scoring, it can be used to retrain the model using new data at a later time.</span></span> <span data-ttu-id="acc23-188">Das erneute Trainieren wird in diesem Tutorial jedoch nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="acc23-188">Retraining is outside the scope of this tutorial though.</span></span>

### <a name="configure-the-predictionengine-pool"></a><span data-ttu-id="acc23-189">Konfigurieren des PredictionEngine-Pools</span><span class="sxs-lookup"><span data-stu-id="acc23-189">Configure the PredictionEngine pool</span></span>

<span data-ttu-id="acc23-190">Um eine einzelne Vorhersage zu treffen, müssen Sie eine [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) erstellen.</span><span class="sxs-lookup"><span data-stu-id="acc23-190">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="acc23-191">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="acc23-191">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="acc23-192">Außerdem müssen Sie eine Instanz davon überall dort erstellen, wo diese in Ihrer Anwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="acc23-192">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="acc23-193">Wenn die Anwendung wächst, kann dieser Prozess ggf. nicht mehr verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="acc23-193">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="acc23-194">Für verbesserte Leistung und Threadsicherheit verwenden Sie eine Kombination aus Abhängigkeitsinjektion (Dependency Injection, DI) und dem `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) von [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="acc23-194">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

1. <span data-ttu-id="acc23-195">Installieren Sie das NuGet-Paket *Microsoft.Extensions.ML*:</span><span class="sxs-lookup"><span data-stu-id="acc23-195">Install the *Microsoft.Extensions.ML* NuGet package:</span></span>

    1. <span data-ttu-id="acc23-196">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-196">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="acc23-197">Wählen Sie als Paketquelle „nuget.org“ aus.</span><span class="sxs-lookup"><span data-stu-id="acc23-197">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="acc23-198">Wählen Sie die Registerkarte **Durchsuchen** aus, und suchen Sie nach **Microsoft.Extensions.ML**.</span><span class="sxs-lookup"><span data-stu-id="acc23-198">Select the **Browse** tab and search for **Microsoft.Extensions.ML**.</span></span>
    1. <span data-ttu-id="acc23-199">Wählen Sie das Paket in der Liste aus, und **klicken Sie auf die Schaltfläche** Installieren.</span><span class="sxs-lookup"><span data-stu-id="acc23-199">Select the package in the list, and select the **Install** button.</span></span>
    1. <span data-ttu-id="acc23-200">Klicken Sie im Dialogfeld **Vorschau der Änderungen** auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="acc23-200">Select the **OK** button on the **Preview Changes** dialog</span></span>
    1. <span data-ttu-id="acc23-201">Wählen Sie die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz**, wenn Sie mit den Lizenzbedingungen für die aufgeführten Pakete einverstanden sind.</span><span class="sxs-lookup"><span data-stu-id="acc23-201">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="acc23-202">Öffnen Sie die Datei *Startup.cs* im Projekt *SentimentRazor*.</span><span class="sxs-lookup"><span data-stu-id="acc23-202">Open the *Startup.cs* file in the *SentimentRazor* project.</span></span>
1. <span data-ttu-id="acc23-203">Fügen Sie die folgenden using-Anweisungen hinzu, um auf das NuGet-Paket *Microsoft.Extensions.ML* und auf das Projekt *SentimentRazorML.Model* zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="acc23-203">Add the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and *SentimentRazorML.Model* project:</span></span>

    ```csharp
    using System.IO;
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

1. <span data-ttu-id="acc23-204">Erstellen Sie eine globale Variable zum Speichern des Speicherorts der trainierten Modelldatei.</span><span class="sxs-lookup"><span data-stu-id="acc23-204">Create a global variable to store the location of the trained model file.</span></span>

    ```csharp
    private readonly string _modelPath;
    ```

1. <span data-ttu-id="acc23-205">Die Modelldatei wird im Buildverzeichnis zusammen mit den Assemblydateien der Anwendung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="acc23-205">The model file is stored in the build directory alongside the assembly files of your application.</span></span> <span data-ttu-id="acc23-206">Um den Zugriff zu vereinfachen, erstellen Sie eine Hilfsmethode namens `GetAbsolutePath` nach der `Configure`-Methode.</span><span class="sxs-lookup"><span data-stu-id="acc23-206">To make it easier to access, create a helper method called `GetAbsolutePath` after the `Configure` method</span></span>

    ```csharp
    public static string GetAbsolutePath(string relativePath)
    {
        FileInfo _dataRoot = new FileInfo(typeof(Program).Assembly.Location);
        string assemblyFolderPath = _dataRoot.Directory.FullName;

        string fullPath = Path.Combine(assemblyFolderPath, relativePath);
        return fullPath;
    }
    ```

1. <span data-ttu-id="acc23-207">Verwenden Sie die `GetAbsolutePath`-Methode im `Startup`-Klassenkonstruktor, um `_modelPath` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="acc23-207">Use the `GetAbsolutePath` method in the `Startup` class constructor to set the `_modelPath`.</span></span>

    ```csharp
    _modelPath = GetAbsolutePath("MLModel.zip");
    ```

1. <span data-ttu-id="acc23-208">Konfigurieren Sie den `PredictionEnginePool` für Ihre Anwendung in der `ConfigureServices`-Methode:</span><span class="sxs-lookup"><span data-stu-id="acc23-208">Configure the `PredictionEnginePool` for your application in the `ConfigureServices` method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<ModelInput, ModelOutput>()
            .FromFile(_modelPath);
    ```

### <a name="create-sentiment-analysis-handler"></a><span data-ttu-id="acc23-209">Erstellen eines Stimmungsanalysehandlers</span><span class="sxs-lookup"><span data-stu-id="acc23-209">Create sentiment analysis handler</span></span>

<span data-ttu-id="acc23-210">Vorhersagen werden auf der Hauptseite der Anwendung getroffen.</span><span class="sxs-lookup"><span data-stu-id="acc23-210">Predictions will be made inside the main page of the application.</span></span> <span data-ttu-id="acc23-211">Daher muss eine Methode, die die Benutzereingaben annimmt und `PredictionEnginePool` zum Zurückgeben einer Vorhersage verwendet, hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="acc23-211">Therefore, a method that takes the user input and uses the `PredictionEnginePool` to return a prediction needs to be added.</span></span>

1. <span data-ttu-id="acc23-212">Öffnen Sie die Datei *index.cshtml.cs* im Verzeichnis *Pages*, und fügen Sie die folgenden using-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="acc23-212">Open the *Index.cshtml.cs* file located in the *Pages* directory and add the following using statements:</span></span>

    ```csharp
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

    <span data-ttu-id="acc23-213">Um den `PredictionEnginePool` zu verwenden, der in der `Startup`-Klasse konfiguriert wurde, müssen Sie ihn in den Konstruktor des Modells einschleusen, in dem Sie ihn verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="acc23-213">In order to use the `PredictionEnginePool` configured in the `Startup` class, you have to inject it into the constructor of the model where you want to use it.</span></span>

1. <span data-ttu-id="acc23-214">Fügen Sie eine Variable hinzu, um auf den `PredictionEnginePool` in der `IndexModel`-Klasse zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="acc23-214">Add a variable to reference the `PredictionEnginePool` inside the `IndexModel` class.</span></span>

    ```csharp
    private readonly PredictionEnginePool<ModelInput, ModelOutput> _predictionEnginePool;
    ```

1. <span data-ttu-id="acc23-215">Erstellen Sie einen Konstruktor in der `IndexModel`-Klasse, und schleusen Sie den `PredictionEnginePool`-Dienst in diesen ein.</span><span class="sxs-lookup"><span data-stu-id="acc23-215">Create a constructor in the `IndexModel` class and inject the `PredictionEnginePool` service into it.</span></span>

    ```csharp
    public IndexModel(PredictionEnginePool<ModelInput, ModelOutput> predictionEnginePool)
    {
        _predictionEnginePool = predictionEnginePool;
    }
    ```

1. <span data-ttu-id="acc23-216">Erstellen Sie einen Methodenhandler, der den `PredictionEnginePool` verwendet, um Vorhersagen aus Benutzereingaben zu treffen, die von der Webseite empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="acc23-216">Create a method handler that uses the `PredictionEnginePool` to make predictions from user input received from the web page.</span></span>

    1. <span data-ttu-id="acc23-217">Erstellen Sie unter der `OnGet`-Methode eine Methode namens `OnGetAnalyzeSentiment`.</span><span class="sxs-lookup"><span data-stu-id="acc23-217">Below the `OnGet` method, create a new method called `OnGetAnalyzeSentiment`</span></span>

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. <span data-ttu-id="acc23-218">Geben Sie innerhalb der `OnGetAnalyzeSentiment`-Methode die Stimmung *Neutral* zurück, wenn die Eingabe des Benutzers leer oder NULL ist.</span><span class="sxs-lookup"><span data-stu-id="acc23-218">Inside the `OnGetAnalyzeSentiment` method, return *Neutral* sentiment if the input from the user is blank or null.</span></span>

        ```csharp
        if (String.IsNullOrEmpty(text)) return Content("Neutral");
        ```

    1. <span data-ttu-id="acc23-219">Erstellen Sie eine neue Instanz von `ModelInput`, wenn Sie über eine gültige Eingabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="acc23-219">Given a valid input, create a new instance of `ModelInput`.</span></span>

        ```csharp
        var input = new ModelInput { SentimentText = text };
        ```

    1. <span data-ttu-id="acc23-220">Verwenden Sie `PredictionEnginePool` zum Vorhersagen der Stimmung.</span><span class="sxs-lookup"><span data-stu-id="acc23-220">Use the `PredictionEnginePool` to predict sentiment.</span></span>

        ```csharp
        var prediction = _predictionEnginePool.Predict(input);
        ```

    1. <span data-ttu-id="acc23-221">Konvertieren Sie den vorhergesagten `bool`-Wert mit dem folgenden Code in „toxic“ oder „not toxic“.</span><span class="sxs-lookup"><span data-stu-id="acc23-221">Convert the predicted `bool` value into toxic or not toxic with the following code.</span></span>

        ```csharp
        var sentiment = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";
        ```

    1. <span data-ttu-id="acc23-222">Geben Sie die Stimmung schließlich zurück an die Webseite.</span><span class="sxs-lookup"><span data-stu-id="acc23-222">Finally, return the sentiment back to the web page.</span></span>

        ```csharp
        return Content(sentiment);
        ```

### <a name="configure-the-web-page"></a><span data-ttu-id="acc23-223">Konfigurieren der Webseite</span><span class="sxs-lookup"><span data-stu-id="acc23-223">Configure the web page</span></span>

<span data-ttu-id="acc23-224">Die von `OnGetAnalyzeSentiment` zurückgegebenen Ergebnisse werden dynamisch auf der `Index`-Webseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="acc23-224">The results returned by the `OnGetAnalyzeSentiment` will be dynamically displayed on the `Index` web page.</span></span>

1. <span data-ttu-id="acc23-225">Öffnen Sie die Datei *Index.cshtml* im Verzeichnis *Pages*, und ersetzen Sie deren Inhalt durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="acc23-225">Open the *Index.cshtml* file in the *Pages* directory and replace its contents with the following code:</span></span>

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. <span data-ttu-id="acc23-226">Fügen Sie nun CSS-Formatierungscode am Ende der Seite *site.css* im Verzeichnis *wwwroot\css* hinzu:</span><span class="sxs-lookup"><span data-stu-id="acc23-226">Next, add css styling code to the end of the *site.css* page in the *wwwroot\css* directory:</span></span>

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. <span data-ttu-id="acc23-227">Fügen Sie anschließend Code hinzu, um Eingaben von der Webseite an den `OnGetAnalyzeSentiment`-Handler zu senden.</span><span class="sxs-lookup"><span data-stu-id="acc23-227">After that, add code to send inputs from the web page to the `OnGetAnalyzeSentiment` handler.</span></span>

    1. <span data-ttu-id="acc23-228">Erstellen Sie in der Datei *site.js* im Verzeichnis *wwwroot\js* eine Funktion mit dem Namen `getSentiment`, um eine GET HTTP-Anforderung mit der Benutzereingabe an den `OnGetAnalyzeSentiment`-Handler auszugeben.</span><span class="sxs-lookup"><span data-stu-id="acc23-228">In the *site.js* file located in the *wwwroot\js* directory, create a function called `getSentiment` to make a GET HTTP request with the user input to the `OnGetAnalyzeSentiment` handler.</span></span>

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. <span data-ttu-id="acc23-229">Fügen Sie darunter eine weitere Funktion mit dem Namen `updateMarker` hinzu, um die Position des Markers auf der Webseite dynamisch zu aktualisieren, wenn die Stimmung vorhergesagt wird.</span><span class="sxs-lookup"><span data-stu-id="acc23-229">Below that, add another function called `updateMarker` to dynamically update the position of the marker on the web page as sentiment is predicted.</span></span>

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. <span data-ttu-id="acc23-230">Erstellen Sie eine Ereignishandlerfunktion namens `updateSentiment`, um die Eingabe vom Benutzer abzurufen, senden Sie diese mithilfe der `getSentiment`-Funktion an die `OnGetAnalyzeSentiment`-Funktion, und aktualisieren Sie den Marker mit der `updateMarker`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="acc23-230">Create an event handler function called `updateSentiment` to get the input from the user, send it to the `OnGetAnalyzeSentiment` function using the `getSentiment` function and update the marker with the `updateMarker` function.</span></span>

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. <span data-ttu-id="acc23-231">Registrieren Sie schließlich den Ereignishandler, und binden Sie ihn an das `textarea`-Element mit dem `id=Message`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="acc23-231">Finally, register the event handler and bind it to the `textarea` element with the `id=Message` attribute.</span></span>

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a><span data-ttu-id="acc23-232">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="acc23-232">Run the application</span></span>

<span data-ttu-id="acc23-233">Nachdem Sie Ihre Anwendung eingerichtet haben, führen Sie die Anwendung aus, die in Ihrem Browser gestartet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="acc23-233">Now that your application is set up, run the application which should launch in your browser.</span></span>

<span data-ttu-id="acc23-234">Wenn die Anwendung gestartet wird, geben Sie *Model Builder ist cool!*</span><span class="sxs-lookup"><span data-stu-id="acc23-234">When the application launches, enter *Model Builder is cool!*</span></span> <span data-ttu-id="acc23-235">in den Textbereich ein.</span><span class="sxs-lookup"><span data-stu-id="acc23-235">into the text area.</span></span> <span data-ttu-id="acc23-236">Die vorhergesagte Stimmung sollte *Not Toxic* sein.</span><span class="sxs-lookup"><span data-stu-id="acc23-236">The predicted sentiment displayed should be *Not Toxic*.</span></span>

![Aktuell ausgeführtes Fenster mit dem Fenster für die vorhergesagte Stimmung](./media/sentiment-analysis-model-builder/web-app.png)

<span data-ttu-id="acc23-238">Wenn Sie zu einem späteren Zeitpunkt innerhalb einer anderen Projektmappe auf die generierten Modell-Generator-Projekte verweisen müssen, finden Sie diese im Verzeichnis `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="acc23-238">If you need to reference the Model Builder generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="acc23-239">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="acc23-239">Next steps</span></span>

<span data-ttu-id="acc23-240">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="acc23-240">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="acc23-241">Erstellen einer ASP.NET Core Razor Pages-Anwendung</span><span class="sxs-lookup"><span data-stu-id="acc23-241">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="acc23-242">Vorbereiten und Verstehen der Daten</span><span class="sxs-lookup"><span data-stu-id="acc23-242">Prepare and understand the data</span></span>
> - <span data-ttu-id="acc23-243">Auswählen eines Szenarios</span><span class="sxs-lookup"><span data-stu-id="acc23-243">Choose a scenario</span></span>
> - <span data-ttu-id="acc23-244">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="acc23-244">Load the data</span></span>
> - <span data-ttu-id="acc23-245">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="acc23-245">Train the model</span></span>
> - <span data-ttu-id="acc23-246">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="acc23-246">Evaluate the model</span></span>
> - <span data-ttu-id="acc23-247">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="acc23-247">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="acc23-248">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="acc23-248">Additional Resources</span></span>

<span data-ttu-id="acc23-249">Weitere Informationen zu den in diesem Tutorial erwähnten Themen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="acc23-249">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="acc23-250">Szenarien für den Modellgenerator</span><span class="sxs-lookup"><span data-stu-id="acc23-250">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="acc23-251">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="acc23-251">Binary Classification</span></span>](../resources/glossary.md#binary-classification)
- [<span data-ttu-id="acc23-252">Metriken des Modells für binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="acc23-252">Binary Classification Model Metrics</span></span>](../resources/metrics.md#metrics-for-binary-classification)
