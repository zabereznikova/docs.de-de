---
title: Was ist der Modell-Generator und wie funktioniert er?
description: Erfahren Sie mehr über die Verwendung des ML.NET-Modell-Generators zum automatischen Trainieren eines Machine Learning-Modells.
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: 77fe56dba3532617ad9fb0c89bfaac7c8e031ce7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971521"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="d2449-103">Was ist der Modell-Generator und wie funktioniert er?</span><span class="sxs-lookup"><span data-stu-id="d2449-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="d2449-104">Der ML.NET-Modell-Generator ist eine intuitive grafische Visual Studio-Erweiterung zum Erstellen, Trainieren und Bereitstellen von benutzerdefinierten Machine Learning-Modellen.</span><span class="sxs-lookup"><span data-stu-id="d2449-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="d2449-105">Der Modell-Generator verwendet automatisiertes maschinelles Lernen (AutoML), um verschiedene Machine Learning-Algorithmen und Einstellungen zu untersuchen, damit Sie die optimalen Einstellungen für Ihr Szenario ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="d2449-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="d2449-106">Für die Verwendung des Modell-Generators sind keine Machine Learning-Kenntnisse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d2449-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="d2449-107">Sie benötigen lediglich einige Daten und ein Problem, das Sie lösen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2449-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="d2449-108">Modell-Generator generiert den Code, um das Modell zur Ihrer .NET-Anwendung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d2449-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![Animation der Benutzeroberfläche der Visual Studio-Erweiterung für den Modell-Generator](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="d2449-110">Der Modell-Generator befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="d2449-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="d2449-111">Szenarien</span><span class="sxs-lookup"><span data-stu-id="d2449-111">Scenarios</span></span>

<span data-ttu-id="d2449-112">Sie können viele verschiedene Szenarien in den Modell-Generator einbinden, um ein Machine Learning-Modell für Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2449-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="d2449-113">Ein Szenario ist eine Beschreibung der Art der Vorhersage, die Sie mit Ihren Daten treffen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2449-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="d2449-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d2449-114">For example:</span></span>

- <span data-ttu-id="d2449-115">Vorhersagen des zukünftigen Produktabsatzes auf der Grundlage historischer Verkaufsdaten</span><span class="sxs-lookup"><span data-stu-id="d2449-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="d2449-116">Klassifizieren der Stimmungen als positiv oder negativ anhand von Kundenrezensionen</span><span class="sxs-lookup"><span data-stu-id="d2449-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="d2449-117">Erkennen einer betrügerischen Banktransaktion</span><span class="sxs-lookup"><span data-stu-id="d2449-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="d2449-118">Weiterleiten von Problemen beim Kundenfeedback an das richtige Team in Ihrem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d2449-118">route customer feedback issues to the correct team in your company</span></span>

## <a name="choose-a-model-type"></a><span data-ttu-id="d2449-119">Auswählen eines Modelltyps</span><span class="sxs-lookup"><span data-stu-id="d2449-119">Choose a model type</span></span>

<span data-ttu-id="d2449-120">Sie müssen einen Machine-Learning-Modelltyp im Modellgenerator auswählen.</span><span class="sxs-lookup"><span data-stu-id="d2449-120">In Model Builder, you need to select a machine learning model type.</span></span> <span data-ttu-id="d2449-121">Der Modelltyp hängt davon ab, welche Art von Vorhersage Sie erzielen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2449-121">The type of model depends on what sort of prediction you are trying to make.</span></span>

<span data-ttu-id="d2449-122">Für Szenarios, bei denen Sie eine Zahl vorhersagen möchten, lautet der Machine-Learning-Modelltyp `regression`.</span><span class="sxs-lookup"><span data-stu-id="d2449-122">For scenarios that predict a number, the machine learning model type is called `regression`.</span></span>

<span data-ttu-id="d2449-123">Für Szenarios, bei denen Sie eine Kategorie vorhersagen möchten, lautet der Machine-Learning-Modelltyp `classification`.</span><span class="sxs-lookup"><span data-stu-id="d2449-123">For scenarios that predict a category, the model type is `classification`.</span></span> <span data-ttu-id="d2449-124">Es gibt zwei Arten von Klassifizierung:</span><span class="sxs-lookup"><span data-stu-id="d2449-124">There are two types of classification:</span></span>

- <span data-ttu-id="d2449-125">Klassifizierungen mit nur zwei Kategorien: `binary classification`.</span><span class="sxs-lookup"><span data-stu-id="d2449-125">where there are only 2 categories: `binary classification`.</span></span>
- <span data-ttu-id="d2449-126">Klassifizierungen mit drei oder mehr Kategorien: `multiclass classification`.</span><span class="sxs-lookup"><span data-stu-id="d2449-126">where there are three or more categories: `multiclass classification`.</span></span>

### <a name="which-model-type-is-right-for-me"></a><span data-ttu-id="d2449-127">Welches Modell eignet sich für mich?</span><span class="sxs-lookup"><span data-stu-id="d2449-127">Which model type is right for me?</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="d2449-128">Vorhersagen einer Kategorie (wenn nur zwei Kategorien vorliegen)</span><span class="sxs-lookup"><span data-stu-id="d2449-128">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="d2449-129">Die binäre Klassifizierung wird verwendet, um Daten in zwei Kategorien zu unterteilen (ja/nein; Erfolg/Fehler; wahr/falsch; positiv/negativ).</span><span class="sxs-lookup"><span data-stu-id="d2449-129">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![Diagramm mit Beispielen für die binäre Klassifizierung, einschließlich Betrugserkennung, Risikominderung und Bewerbungsüberprüfung](media/binary-classification-examples.png)

<span data-ttu-id="d2449-131">Die Standpunktanalyse kann verwendet werden, um positive oder negative Stimmungen im Kundenfeedback vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="d2449-131">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="d2449-132">Dies ist ein Beispiel für einen binären Klassifizierungsmodelltyp.</span><span class="sxs-lookup"><span data-stu-id="d2449-132">It is an example of a binary classification model type.</span></span>

<span data-ttu-id="d2449-133">Wenn Ihr Szenario eine Klassifizierung in zwei Kategorien erfordert, können Sie diese Vorlage mit einem eigenen Dataset verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2449-133">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="d2449-134">Vorhersagen einer Kategorie (wenn drei oder mehr Kategorien vorliegen)</span><span class="sxs-lookup"><span data-stu-id="d2449-134">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="d2449-135">Die Multiklassenklassifizierung kann für die Kategorisierung von Daten in drei oder mehr Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2449-135">Multiclass classification can be used to categorize data into three or more classes.</span></span>

![Beispiele für die Mehrklassenklassifizierung, einschließlich Dokument- und Produktklassifizierung, Supportticketweiterleitung und Kundenproblempriorisierung](media/multiclass-classification-examples.png)

<span data-ttu-id="d2449-137">Die Fehlerklassifizierung kann verwendet werden, um Kundenfeedback (z.B. zu GitHub) anhand des Problemtitels und der Beschreibung zu kategorisieren.</span><span class="sxs-lookup"><span data-stu-id="d2449-137">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="d2449-138">Dies ist ein Beispiel für den Modelltyp für Multiklassenklassifizierung.</span><span class="sxs-lookup"><span data-stu-id="d2449-138">It is an example of the multi-class classification model type.</span></span>

<span data-ttu-id="d2449-139">Sie können die Vorlage für die Fehlerklassifizierung für Ihr Szenario verwenden, wenn Sie Daten in drei oder mehr Kategorien einteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2449-139">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="d2449-140">Vorhersagen einer Zahl</span><span class="sxs-lookup"><span data-stu-id="d2449-140">Predict a number</span></span>

<span data-ttu-id="d2449-141">Die Regression wird verwendet, um Zahlen vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="d2449-141">Regression is used to predict numbers.</span></span>

![Diagramm mit Regressionsbeispielen wie Preisvorhersagen, Umsatzvorhersagen und Predictive Maintenance](media/regression-examples.png)

<span data-ttu-id="d2449-143">Die Preisvorhersage kann verwendet werden, um Hauspreise anhand von Lage, Größe und anderen Merkmalen des Hauses vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="d2449-143">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="d2449-144">Dies ist ein Beispiel für den Regressionsmodelltyp.</span><span class="sxs-lookup"><span data-stu-id="d2449-144">It is an example of a regression model type.</span></span>

<span data-ttu-id="d2449-145">Sie können die Vorlage für die Preisvorhersage für Ihr Szenario verwenden, wenn Sie einen Zahlenwert mit einem eigenen Dataset vorhersagen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2449-145">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-model-type"></a><span data-ttu-id="d2449-146">Benutzerdefiniertes Szenario (wählen Sie Ihren Modelltyp aus)</span><span class="sxs-lookup"><span data-stu-id="d2449-146">Custom scenario (choose your model type)</span></span>

<span data-ttu-id="d2449-147">Im benutzerdefinierten Szenario können Sie Ihren Modelltyp manuell auswählen.</span><span class="sxs-lookup"><span data-stu-id="d2449-147">The custom scenario allows you to manually choose your model type.</span></span>

## <a name="data"></a><span data-ttu-id="d2449-148">Daten</span><span class="sxs-lookup"><span data-stu-id="d2449-148">Data</span></span>

<span data-ttu-id="d2449-149">Sobald Sie Ihren Modelltyp ausgewählt haben, fordert der Modellgenerator Sie auf, ein Dataset bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d2449-149">Once you have chosen your model type, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="d2449-150">Die Daten werden verwendet, um das beste Modell für Ihr Szenario zu trainieren, zu evaluieren und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d2449-150">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![Diagramm mit dem Schritten im Modellgenerator](media/model-builder-steps.png)

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="d2449-152">Auswählen der Ausgabe für die Vorhersage (Bezeichnung)</span><span class="sxs-lookup"><span data-stu-id="d2449-152">Choose the output to predict (label)</span></span>

<span data-ttu-id="d2449-153">Ein Dataset ist eine Tabelle mit Zeilen mit Trainingsbeispielen und Spalten mit Attributen.</span><span class="sxs-lookup"><span data-stu-id="d2449-153">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="d2449-154">Jede Zeile enthält:</span><span class="sxs-lookup"><span data-stu-id="d2449-154">Each row has:</span></span>

- <span data-ttu-id="d2449-155">eine **Bezeichnung** (das Attribut, das Sie vorhersagen möchten)</span><span class="sxs-lookup"><span data-stu-id="d2449-155">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="d2449-156">**Features** (Attribute, die als Eingaben verwendet werden, um die Bezeichnung vorherzusagen).</span><span class="sxs-lookup"><span data-stu-id="d2449-156">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="d2449-157">Für das Szenario der Hauspreisvorhersage könnten folgende Features verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d2449-157">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="d2449-158">die Quadratmeterzahl des Hauses</span><span class="sxs-lookup"><span data-stu-id="d2449-158">the square footage of the house</span></span>
- <span data-ttu-id="d2449-159">die Anzahl an Schlafzimmern und Badezimmern</span><span class="sxs-lookup"><span data-stu-id="d2449-159">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="d2449-160">die Postleitzahl</span><span class="sxs-lookup"><span data-stu-id="d2449-160">the zip code</span></span>

<span data-ttu-id="d2449-161">Die Bezeichnung ist der historische Hauspreis für diese Zeile mit den Werten für die Quadratmeterzahl, Schlafzimmer- und Badezimmeranzahl und Postleitzahl.</span><span class="sxs-lookup"><span data-stu-id="d2449-161">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![Tabelle mit Zeilen und Spalten mit Hauspreisdaten mit Features bestehend aus Größe, Räumen, Postleitzahl und Preisangabe](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="d2449-163">Beispieldatasets</span><span class="sxs-lookup"><span data-stu-id="d2449-163">Example datasets</span></span>

<span data-ttu-id="d2449-164">Wenn Sie noch keine eigenen Daten haben, probieren Sie eines dieser Datasets aus:</span><span class="sxs-lookup"><span data-stu-id="d2449-164">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="d2449-165">Szenario</span><span class="sxs-lookup"><span data-stu-id="d2449-165">Scenario</span></span>|<span data-ttu-id="d2449-166">Modelltyp</span><span class="sxs-lookup"><span data-stu-id="d2449-166">Model Type</span></span>|<span data-ttu-id="d2449-167">Daten</span><span class="sxs-lookup"><span data-stu-id="d2449-167">Data</span></span>|<span data-ttu-id="d2449-168">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="d2449-168">Label</span></span>|<span data-ttu-id="d2449-169">Features</span><span class="sxs-lookup"><span data-stu-id="d2449-169">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="d2449-170">Preisvorhersage</span><span class="sxs-lookup"><span data-stu-id="d2449-170">Price prediction</span></span>|<span data-ttu-id="d2449-171">Regression</span><span class="sxs-lookup"><span data-stu-id="d2449-171">regression</span></span>|[<span data-ttu-id="d2449-172">taxi fare data</span><span class="sxs-lookup"><span data-stu-id="d2449-172">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="d2449-173">Preis</span><span class="sxs-lookup"><span data-stu-id="d2449-173">Fare</span></span>|<span data-ttu-id="d2449-174">Fahrtzeit, Strecke</span><span class="sxs-lookup"><span data-stu-id="d2449-174">Trip time, distance</span></span>|
|<span data-ttu-id="d2449-175">Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="d2449-175">Anomaly detection</span></span>|<span data-ttu-id="d2449-176">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="d2449-176">binary classification</span></span>|[<span data-ttu-id="d2449-177">product sales data</span><span class="sxs-lookup"><span data-stu-id="d2449-177">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="d2449-178">Produktverkäufe</span><span class="sxs-lookup"><span data-stu-id="d2449-178">Product Sales</span></span>|<span data-ttu-id="d2449-179">Monat</span><span class="sxs-lookup"><span data-stu-id="d2449-179">Month</span></span>|
|<span data-ttu-id="d2449-180">Stimmungsanalyse</span><span class="sxs-lookup"><span data-stu-id="d2449-180">Sentiment analysis</span></span>|<span data-ttu-id="d2449-181">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="d2449-181">binary classification</span></span>|[<span data-ttu-id="d2449-182">website comment data</span><span class="sxs-lookup"><span data-stu-id="d2449-182">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="d2449-183">Bezeichnung (0 bei negativer Stimmung, 1, wenn positiv)</span><span class="sxs-lookup"><span data-stu-id="d2449-183">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="d2449-184">Kommentar, Jahr</span><span class="sxs-lookup"><span data-stu-id="d2449-184">Comment, Year</span></span>|
|<span data-ttu-id="d2449-185">Betrugserkennung</span><span class="sxs-lookup"><span data-stu-id="d2449-185">Fraud detection</span></span>|<span data-ttu-id="d2449-186">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="d2449-186">binary classification</span></span>|[<span data-ttu-id="d2449-187">credit card data</span><span class="sxs-lookup"><span data-stu-id="d2449-187">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="d2449-188">Klasse (1, wenn betrügerisch, andernfalls 0)</span><span class="sxs-lookup"><span data-stu-id="d2449-188">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="d2449-189">Betrag, V1-V28 (anonymisierte Features)</span><span class="sxs-lookup"><span data-stu-id="d2449-189">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="d2449-190">Textklassifizierung</span><span class="sxs-lookup"><span data-stu-id="d2449-190">Text classification</span></span>|<span data-ttu-id="d2449-191">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="d2449-191">multiclass classification</span></span>|[<span data-ttu-id="d2449-192">GitHub issue data</span><span class="sxs-lookup"><span data-stu-id="d2449-192">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="d2449-193">Bereich</span><span class="sxs-lookup"><span data-stu-id="d2449-193">Area</span></span>|<span data-ttu-id="d2449-194">Titel, Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2449-194">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="d2449-195">Trainieren</span><span class="sxs-lookup"><span data-stu-id="d2449-195">Train</span></span>

<span data-ttu-id="d2449-196">Sobald Sie Ihr Szenario, Ihre Daten und Ihre Bezeichnung ausgewählt haben, trainiert der Modell-Generator das Modell.</span><span class="sxs-lookup"><span data-stu-id="d2449-196">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="d2449-197">Was bedeutet Training?</span><span class="sxs-lookup"><span data-stu-id="d2449-197">What is training?</span></span>

<span data-ttu-id="d2449-198">Das Training ist ein automatischer Prozess, bei dem der Modellgenerator dem Modell beibringt, wie es Fragen für Ihr Szenario beantworten kann.</span><span class="sxs-lookup"><span data-stu-id="d2449-198">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="d2449-199">Nach dem Training kann Ihr Modell Vorhersagen mit ihm bisher unbekannten Eingabedaten treffen.</span><span class="sxs-lookup"><span data-stu-id="d2449-199">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="d2449-200">Wenn Sie zum Beispiel die Hauspreise vorhersagen und ein neues Haus auf den Markt kommt, können Sie seinen Verkaufspreis vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="d2449-200">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="d2449-201">Da der Modell-Generator automatisiertes maschinelles Lernen (AutoML) verwendet, ist während des Trainings keine Eingabe oder Anpassung durch Sie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d2449-201">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

## <a name="evaluate"></a><span data-ttu-id="d2449-202">Auswerten</span><span class="sxs-lookup"><span data-stu-id="d2449-202">Evaluate</span></span>

<span data-ttu-id="d2449-203">Unter Evaluierung versteht man den Prozess, bei dem mit dem trainierten Modell Vorhersagen mit neuen Testdaten getroffen werden und anschließend gemessen wird, wie gut die Vorhersagen sind.</span><span class="sxs-lookup"><span data-stu-id="d2449-203">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="d2449-204">Der Modell-Generator unterteilt die Trainingsdaten in einen Trainingssatz und einen Testsatz.</span><span class="sxs-lookup"><span data-stu-id="d2449-204">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="d2449-205">Die Trainingsdaten (80 %) werden zum Trainieren Ihres Modells verwendet, und die Testdaten (20 %) zur Evaluierung Ihres Modells zurückgehalten.</span><span class="sxs-lookup"><span data-stu-id="d2449-205">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> <span data-ttu-id="d2449-206">Der Modellgenerator verwendet Metriken, um zu messen, wie gut das Modell ist.</span><span class="sxs-lookup"><span data-stu-id="d2449-206">Model Builder uses metrics to measure how good the model is.</span></span> <span data-ttu-id="d2449-207">Welche spezifischen Metriken verwendet werden, hängt vom Modelltyp ab.</span><span class="sxs-lookup"><span data-stu-id="d2449-207">The specific metrics used are dependent on the type of model.</span></span> <span data-ttu-id="d2449-208">Weitere Informationen finden Sie unter [Metriken für die Modellevaluierung](resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="d2449-208">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="d2449-209">Verbessern</span><span class="sxs-lookup"><span data-stu-id="d2449-209">Improve</span></span>

<span data-ttu-id="d2449-210">Wenn Ihr Modellleistungswert nicht so gut ist, wie Sie es sich wünschen, haben Sie die folgenden Möglichkeit:</span><span class="sxs-lookup"><span data-stu-id="d2449-210">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="d2449-211">Längeres Trainieren.</span><span class="sxs-lookup"><span data-stu-id="d2449-211">Train for a longer period of time.</span></span> <span data-ttu-id="d2449-212">Mit mehr Zeit kann die automatisierte Machine Learning-Engine mehrere Algorithmen und Einstellungen auszuprobieren.</span><span class="sxs-lookup"><span data-stu-id="d2449-212">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="d2449-213">Weitere Daten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d2449-213">Add more data.</span></span> <span data-ttu-id="d2449-214">Manchmal reicht die Datenmenge nicht aus, um ein hochwertiges Machine Learning-Modell zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="d2449-214">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="d2449-215">Ihre Daten ausgleichen.</span><span class="sxs-lookup"><span data-stu-id="d2449-215">Balance your data.</span></span> <span data-ttu-id="d2449-216">Achten Sie bei Klassifizierungsaufgaben darauf, dass der Trainingssatz über die Kategorien hinweg gleichmäßig verteilt ist.</span><span class="sxs-lookup"><span data-stu-id="d2449-216">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="d2449-217">Wenn Sie beispielsweise vier Klassen für 100 Trainingsbeispiele haben und die beiden ersten Klassen (tag1 und tag2) für 90 Datensätze verwendet werden, die anderen beiden (tag3 und tag4) aber nur für die restlichen 10 Datensätze, kann das dazu führen, dass Ihr Modell Schwierigkeiten hat, tag3 oder tag4 korrekt vorherzusagen, da die Daten nicht gleichmäßig verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="d2449-217">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="d2449-218">Code</span><span class="sxs-lookup"><span data-stu-id="d2449-218">Code</span></span>

<span data-ttu-id="d2449-219">Nach der Evaluierungsphase gibt der Modell-Generator eine Modelldatei und einen Code aus, mit dem Sie das Modell zur Ihrer Anwendung hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d2449-219">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="d2449-220">ML.NET-Modelle werden als Zip-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d2449-220">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="d2449-221">Der Code zum Laden und Verwenden Ihres Modells wird als neues Projekt in Ihrer Projektmappe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d2449-221">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="d2449-222">Der Modell-Generator fügt auch eine Beispiel-Konsolen-App hinzu, die Sie ausführen können, um Ihr Modell in Aktion zu sehen.</span><span class="sxs-lookup"><span data-stu-id="d2449-222">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="d2449-223">Darüber hinaus gibt der Modell-Generator den Code aus, der das Modell generiert hat, sodass Sie die Schritte zur Generierung des Modells nachvollziehen können.</span><span class="sxs-lookup"><span data-stu-id="d2449-223">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="d2449-224">Sie können den Modelltrainingscode auch verwenden, um Ihr Modell mit neuen Daten zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="d2449-224">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="d2449-225">Ausblick</span><span class="sxs-lookup"><span data-stu-id="d2449-225">What's next?</span></span>

<span data-ttu-id="d2449-226">[Installieren](how-to-guides/install-model-builder.md) Sie die Modellgeneratorerweiterung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d2449-226">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="d2449-227">Probieren Sie ein [Szenario für die Preisvorhersage oder Regression](tutorials/predict-prices-with-model-builder.md) aus.</span><span class="sxs-lookup"><span data-stu-id="d2449-227">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
