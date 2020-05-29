---
title: Was ist der Modell-Generator und wie funktioniert er?
description: Erfahren Sie mehr über die Verwendung des ML.NET-Modell-Generators zum automatischen Trainieren eines Machine Learning-Modells.
ms.date: 03/25/2020
ms.custom: overview, mlnet-tooling
ms.openlocfilehash: 4afdbfd1682a30647b09d05d51a5c73c214fe2bd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616928"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="c15bd-103">Was ist der Modell-Generator und wie funktioniert er?</span><span class="sxs-lookup"><span data-stu-id="c15bd-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="c15bd-104">Der ML.NET-Modell-Generator ist eine intuitive grafische Visual Studio-Erweiterung zum Erstellen, Trainieren und Bereitstellen von benutzerdefinierten Machine Learning-Modellen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="c15bd-105">Der Modell-Generator verwendet automatisiertes maschinelles Lernen (AutoML), um verschiedene Machine Learning-Algorithmen und Einstellungen zu untersuchen, damit Sie die optimalen Einstellungen für Ihr Szenario ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="c15bd-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="c15bd-106">Für die Verwendung des Modell-Generators sind keine Machine Learning-Kenntnisse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c15bd-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="c15bd-107">Sie benötigen lediglich einige Daten und ein Problem, das Sie lösen möchten.</span><span class="sxs-lookup"><span data-stu-id="c15bd-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="c15bd-108">Modell-Generator generiert den Code, um das Modell zur Ihrer .NET-Anwendung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![Animation der Benutzeroberfläche der Visual Studio-Erweiterung für den Modell-Generator](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="c15bd-110">Der Modell-Generator befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="c15bd-110">Model Builder is currently in Preview.</span></span>

## <a name="scenario"></a><span data-ttu-id="c15bd-111">Szenario</span><span class="sxs-lookup"><span data-stu-id="c15bd-111">Scenario</span></span>

<span data-ttu-id="c15bd-112">Sie können viele verschiedene Szenarien in den Modell-Generator einbinden, um ein Machine Learning-Modell für Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="c15bd-113">Ein Szenario ist eine Beschreibung der Art der Vorhersage, die Sie mit Ihren Daten treffen möchten.</span><span class="sxs-lookup"><span data-stu-id="c15bd-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="c15bd-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c15bd-114">For example:</span></span>

- <span data-ttu-id="c15bd-115">Vorhersagen des zukünftigen Produktabsatzes auf der Grundlage historischer Verkaufsdaten</span><span class="sxs-lookup"><span data-stu-id="c15bd-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="c15bd-116">Klassifizieren der Stimmungen als positiv oder negativ anhand von Kundenrezensionen</span><span class="sxs-lookup"><span data-stu-id="c15bd-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="c15bd-117">Erkennen einer betrügerischen Banktransaktion</span><span class="sxs-lookup"><span data-stu-id="c15bd-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="c15bd-118">Weiterleiten von Problemen beim Kundenfeedback an das richtige Team in Ihrem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="c15bd-118">route customer feedback issues to the correct team in your company</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="c15bd-119">Welches Machine Learning-Szenario ist für mich geeignet?</span><span class="sxs-lookup"><span data-stu-id="c15bd-119">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="c15bd-120">Im Modell-Generator müssen Sie ein Szenario auswählen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-120">In Model Builder, you need to select a scenario.</span></span> <span data-ttu-id="c15bd-121">Der Typ des Szenarios hängt davon ab, welchen Typ von Vorhersage Sie treffen möchten.</span><span class="sxs-lookup"><span data-stu-id="c15bd-121">The type of scenario depends on what type of prediction you are trying to make.</span></span>

#### <a name="text-classification"></a><span data-ttu-id="c15bd-122">Textklassifizierung</span><span class="sxs-lookup"><span data-stu-id="c15bd-122">Text classification</span></span>

<span data-ttu-id="c15bd-123">Die Klassifizierung dient der Unterteilung von Daten in Kategorien.</span><span class="sxs-lookup"><span data-stu-id="c15bd-123">Classification is used to categorize data into categories.</span></span>

![Diagramm mit Beispielen für die binäre Klassifizierung, einschließlich Betrugserkennung, Risikominderung und Bewerbungsüberprüfung](media/binary-classification-examples.png)

![Beispiele für die Mehrklassenklassifizierung, einschließlich Dokument- und Produktklassifizierung, Supportticketweiterleitung und Kundenproblempriorisierung](media/multiclass-classification-examples.png)

#### <a name="value-prediction"></a><span data-ttu-id="c15bd-126">Wertvorhersage</span><span class="sxs-lookup"><span data-stu-id="c15bd-126">Value prediction</span></span>

<span data-ttu-id="c15bd-127">Die Regression wird verwendet, um Zahlen vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-127">Regression is used to predict numbers.</span></span>

![Diagramm mit Regressionsbeispielen wie Preisvorhersagen, Umsatzvorhersagen und Predictive Maintenance](media/regression-examples.png)

#### <a name="image-classification"></a><span data-ttu-id="c15bd-129">Bildklassifizierung</span><span class="sxs-lookup"><span data-stu-id="c15bd-129">Image classification</span></span>

<span data-ttu-id="c15bd-130">Bildklassifizierung kann verwendet werden, um Bilder unterschiedlicher Kategorien zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c15bd-130">Image classification can be used to identify images of different categories.</span></span> <span data-ttu-id="c15bd-131">Beispiele hierfür sind unterschiedliche Arten von Gelände, Tieren oder Fertigungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="c15bd-131">For example, different types of terrain or animals or manufacturing defects.</span></span>

<span data-ttu-id="c15bd-132">Sie können das Szenario für die Bildklassifizierung verwenden, wenn Sie über einen Satz von Bildern verfügen und die Bilder in verschiedene Kategorien klassifizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c15bd-132">You can use the image classification scenario if you have a set of images, and you want to classify the images into different categories.</span></span>

#### <a name="recommendation"></a><span data-ttu-id="c15bd-133">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="c15bd-133">Recommendation</span></span>

<span data-ttu-id="c15bd-134">Mit dem Empfehlungsszenario wird eine Liste vorgeschlagener Elemente für einen bestimmten Benutzer vorhergesagt. Die Vorhersage basiert darauf, wie stark ihre „Gefällt mir“- und „Gefällt nicht“-Angaben denen anderer Benutzer ähneln.</span><span class="sxs-lookup"><span data-stu-id="c15bd-134">The recommendation scenario predicts a list of suggested items for a particular user, based on how similar their likes and dislikes are to other users'.</span></span>

<span data-ttu-id="c15bd-135">Sie können das Empfehlungsszenario verwenden, wenn Sie über einen Satz mit Benutzern und einen Satz mit „Produkten“ – z. B. Kaufartikel, Filme, Bücher oder TV-Sendungen – sowie über einen Satz mit Benutzerbewertungen dieser Produkte verfügen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-135">You can use the recommendation scenario when you have a set of users and a set of "products", such as items to purchase, movies, books, or TV shows, along with a set of users' "ratings" of those products.</span></span>

## <a name="environment"></a><span data-ttu-id="c15bd-136">Umgebung</span><span class="sxs-lookup"><span data-stu-id="c15bd-136">Environment</span></span>

<span data-ttu-id="c15bd-137">Sie können Ihr Machine Learning-Modell lokal auf Ihrem Computer oder in der Cloud in Azure trainieren.</span><span class="sxs-lookup"><span data-stu-id="c15bd-137">You can train your machine learning model locally on your machine or in the cloud on Azure.</span></span>

<span data-ttu-id="c15bd-138">Wenn Sie ein lokales Training durchführen, arbeiten Sie innerhalb der Grenzen Ihrer Computerressourcen (CPU, Arbeitsspeicher und Datenträger).</span><span class="sxs-lookup"><span data-stu-id="c15bd-138">When you train locally, you work within the constraints of your computer resources (CPU, memory, and disk).</span></span> <span data-ttu-id="c15bd-139">Wenn Sie das Training in der Cloud durchführen, können Sie Ihre Ressourcen in Abstimmung auf die Anforderungen Ihres Szenarios hochskalieren, insbesondere für große Datasets.</span><span class="sxs-lookup"><span data-stu-id="c15bd-139">When you train in the cloud, you can scale up your resources to meet the demands of your scenario, especially for large datasets.</span></span>

<span data-ttu-id="c15bd-140">Das lokale Training wird für alle Szenarien unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c15bd-140">Local training is supported for all scenarios.</span></span>

<span data-ttu-id="c15bd-141">Das Azure-Training wird für die Bildklassifizierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c15bd-141">Azure training is supported for Image Classification.</span></span>

## <a name="data"></a><span data-ttu-id="c15bd-142">Daten</span><span class="sxs-lookup"><span data-stu-id="c15bd-142">Data</span></span>

<span data-ttu-id="c15bd-143">Sobald Sie Ihr Szenario ausgewählt haben, fordert der Modell-Generator Sie auf, ein Dataset bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-143">Once you have chosen your scenario, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="c15bd-144">Die Daten werden verwendet, um das beste Modell für Ihr Szenario zu trainieren, zu evaluieren und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-144">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![Diagramm mit dem Schritten im Modellgenerator](media/model-builder-steps.png)

<span data-ttu-id="c15bd-146">Der Modell-Generator unterstützt Datasets im TSV-, CSV- und TXT-Format sowie im SQL-Datenbankformat.</span><span class="sxs-lookup"><span data-stu-id="c15bd-146">Model Builder supports datasets in .tsv, .csv, .txt formats, as well as SQL database format.</span></span> <span data-ttu-id="c15bd-147">Wenn Sie über eine TXT-Datei verfügen, müssen die Spalten durch `,`, `;` oder `/t` getrennt werden, und die Datei muss eine Kopfzeile aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-147">If you have a .txt file, columns should be separated with `,`, `;` or `/t` and the file must have a header row.</span></span>

<span data-ttu-id="c15bd-148">Wenn das Dataset aus Bildern besteht, sind die unterstützten Dateitypen `.jpg` und `.png`.</span><span class="sxs-lookup"><span data-stu-id="c15bd-148">If the dataset is made up of images, the supported file types are `.jpg` and `.png`.</span></span>

<span data-ttu-id="c15bd-149">Weitere Informationen finden Sie unter [Laden von Trainingsdaten in den Modell-Generator](how-to-guides/load-data-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c15bd-149">For more information, see [Load training data into Model Builder](how-to-guides/load-data-model-builder.md).</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="c15bd-150">Auswählen der Ausgabe für die Vorhersage (Bezeichnung)</span><span class="sxs-lookup"><span data-stu-id="c15bd-150">Choose the output to predict (label)</span></span>

<span data-ttu-id="c15bd-151">Ein Dataset ist eine Tabelle mit Zeilen mit Trainingsbeispielen und Spalten mit Attributen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-151">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="c15bd-152">Jede Zeile enthält:</span><span class="sxs-lookup"><span data-stu-id="c15bd-152">Each row has:</span></span>

- <span data-ttu-id="c15bd-153">eine **Bezeichnung** (das Attribut, das Sie vorhersagen möchten)</span><span class="sxs-lookup"><span data-stu-id="c15bd-153">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="c15bd-154">**Features** (Attribute, die als Eingaben verwendet werden, um die Bezeichnung vorherzusagen).</span><span class="sxs-lookup"><span data-stu-id="c15bd-154">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="c15bd-155">Für das Szenario der Hauspreisvorhersage könnten folgende Features verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c15bd-155">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="c15bd-156">die Quadratmeterzahl des Hauses</span><span class="sxs-lookup"><span data-stu-id="c15bd-156">the square footage of the house</span></span>
- <span data-ttu-id="c15bd-157">die Anzahl an Schlafzimmern und Badezimmern</span><span class="sxs-lookup"><span data-stu-id="c15bd-157">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="c15bd-158">die Postleitzahl</span><span class="sxs-lookup"><span data-stu-id="c15bd-158">the zip code</span></span>

<span data-ttu-id="c15bd-159">Die Bezeichnung ist der historische Hauspreis für diese Zeile mit den Werten für die Quadratmeterzahl, Schlafzimmer- und Badezimmeranzahl und Postleitzahl.</span><span class="sxs-lookup"><span data-stu-id="c15bd-159">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![Tabelle mit Zeilen und Spalten mit Hauspreisdaten mit Features bestehend aus Größe, Räumen, Postleitzahl und Preisangabe](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="c15bd-161">Beispieldatasets</span><span class="sxs-lookup"><span data-stu-id="c15bd-161">Example datasets</span></span>

<span data-ttu-id="c15bd-162">Wenn Sie noch keine eigenen Daten haben, probieren Sie eines dieser Datasets aus:</span><span class="sxs-lookup"><span data-stu-id="c15bd-162">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="c15bd-163">Szenario</span><span class="sxs-lookup"><span data-stu-id="c15bd-163">Scenario</span></span>|<span data-ttu-id="c15bd-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c15bd-164">Example</span></span>|<span data-ttu-id="c15bd-165">Daten</span><span class="sxs-lookup"><span data-stu-id="c15bd-165">Data</span></span>|<span data-ttu-id="c15bd-166">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="c15bd-166">Label</span></span>|<span data-ttu-id="c15bd-167">Features</span><span class="sxs-lookup"><span data-stu-id="c15bd-167">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="c15bd-168">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="c15bd-168">Classification</span></span>|<span data-ttu-id="c15bd-169">Vorhersage von Umsatzanomalien</span><span class="sxs-lookup"><span data-stu-id="c15bd-169">Predict sales anomalies</span></span>|[<span data-ttu-id="c15bd-170">product sales data</span><span class="sxs-lookup"><span data-stu-id="c15bd-170">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="c15bd-171">Produktverkäufe</span><span class="sxs-lookup"><span data-stu-id="c15bd-171">Product Sales</span></span>|<span data-ttu-id="c15bd-172">Monat</span><span class="sxs-lookup"><span data-stu-id="c15bd-172">Month</span></span>|
||<span data-ttu-id="c15bd-173">Stimmungsvorhersage für Websitekommentare</span><span class="sxs-lookup"><span data-stu-id="c15bd-173">Predict sentiment of website comments</span></span>|[<span data-ttu-id="c15bd-174">website comment data</span><span class="sxs-lookup"><span data-stu-id="c15bd-174">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="c15bd-175">Bezeichnung (0 bei negativer Stimmung, 1, wenn positiv)</span><span class="sxs-lookup"><span data-stu-id="c15bd-175">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="c15bd-176">Kommentar, Jahr</span><span class="sxs-lookup"><span data-stu-id="c15bd-176">Comment, Year</span></span>|
||<span data-ttu-id="c15bd-177">Vorhersage betrügerischer Kreditkartentransaktionen</span><span class="sxs-lookup"><span data-stu-id="c15bd-177">Predict fraudulent credit card transactions</span></span>|[<span data-ttu-id="c15bd-178">credit card data</span><span class="sxs-lookup"><span data-stu-id="c15bd-178">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="c15bd-179">Klasse (1, wenn betrügerisch, andernfalls 0)</span><span class="sxs-lookup"><span data-stu-id="c15bd-179">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="c15bd-180">Betrag, V1-V28 (anonymisierte Features)</span><span class="sxs-lookup"><span data-stu-id="c15bd-180">Amount, V1-V28 (anonymized features)</span></span>|
||<span data-ttu-id="c15bd-181">Vorhersage des Issuetyps in einem GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="c15bd-181">Predict the type of issue in a GitHub repository</span></span>|[<span data-ttu-id="c15bd-182">GitHub issue data</span><span class="sxs-lookup"><span data-stu-id="c15bd-182">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="c15bd-183">Bereich</span><span class="sxs-lookup"><span data-stu-id="c15bd-183">Area</span></span>|<span data-ttu-id="c15bd-184">Titel, Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c15bd-184">Title, Description</span></span>|
|<span data-ttu-id="c15bd-185">Wertvorhersage</span><span class="sxs-lookup"><span data-stu-id="c15bd-185">Value prediction</span></span>|<span data-ttu-id="c15bd-186">Vorhersage des Preises für eine Taxifahrt</span><span class="sxs-lookup"><span data-stu-id="c15bd-186">Predict taxi fare price</span></span>|[<span data-ttu-id="c15bd-187">taxi fare data</span><span class="sxs-lookup"><span data-stu-id="c15bd-187">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="c15bd-188">Preis</span><span class="sxs-lookup"><span data-stu-id="c15bd-188">Fare</span></span>|<span data-ttu-id="c15bd-189">Fahrtzeit, Strecke</span><span class="sxs-lookup"><span data-stu-id="c15bd-189">Trip time, distance</span></span>|
|<span data-ttu-id="c15bd-190">Bildklassifizierung</span><span class="sxs-lookup"><span data-stu-id="c15bd-190">Image classification</span></span>|<span data-ttu-id="c15bd-191">Vorhersage der Kategorie einer Blume</span><span class="sxs-lookup"><span data-stu-id="c15bd-191">Predict the category of a flower</span></span> |[<span data-ttu-id="c15bd-192">flower images</span><span class="sxs-lookup"><span data-stu-id="c15bd-192">flower images</span></span>](http://download.tensorflow.org/example_images/flower_photos.tgz)|<span data-ttu-id="c15bd-193">Der Typ Blume: Gänseblümchen, Löwenzahn, Rosen, Sonnenblumen, Tulpen</span><span class="sxs-lookup"><span data-stu-id="c15bd-193">The type of flower: daisy, dandelion, roses, sunflowers, tulips</span></span>|<span data-ttu-id="c15bd-194">Die Bilddaten selbst</span><span class="sxs-lookup"><span data-stu-id="c15bd-194">The image data itself</span></span>|
|<span data-ttu-id="c15bd-195">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="c15bd-195">Recommendation</span></span>|<span data-ttu-id="c15bd-196">Vorhersage von Filmen, die einer Person gefallen</span><span class="sxs-lookup"><span data-stu-id="c15bd-196">Predict movies that someone will like</span></span>|[<span data-ttu-id="c15bd-197">movie ratings</span><span class="sxs-lookup"><span data-stu-id="c15bd-197">movie ratings</span></span>](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip)|<span data-ttu-id="c15bd-198">Benutzer, Filme</span><span class="sxs-lookup"><span data-stu-id="c15bd-198">Users, Movies</span></span>|<span data-ttu-id="c15bd-199">Altersfreigabe</span><span class="sxs-lookup"><span data-stu-id="c15bd-199">Ratings</span></span>|

## <a name="train"></a><span data-ttu-id="c15bd-200">Training</span><span class="sxs-lookup"><span data-stu-id="c15bd-200">Train</span></span>

<span data-ttu-id="c15bd-201">Sobald Sie Ihr Szenario, Ihre Daten und Ihre Bezeichnung ausgewählt haben, trainiert der Modell-Generator das Modell.</span><span class="sxs-lookup"><span data-stu-id="c15bd-201">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="c15bd-202">Was bedeutet Training?</span><span class="sxs-lookup"><span data-stu-id="c15bd-202">What is training?</span></span>

<span data-ttu-id="c15bd-203">Das Training ist ein automatischer Prozess, bei dem der Modellgenerator dem Modell beibringt, wie es Fragen für Ihr Szenario beantworten kann.</span><span class="sxs-lookup"><span data-stu-id="c15bd-203">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="c15bd-204">Nach dem Training kann Ihr Modell Vorhersagen mit ihm bisher unbekannten Eingabedaten treffen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-204">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="c15bd-205">Wenn Sie zum Beispiel die Hauspreise vorhersagen und ein neues Haus auf den Markt kommt, können Sie seinen Verkaufspreis vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-205">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="c15bd-206">Da der Modell-Generator automatisiertes maschinelles Lernen (AutoML) verwendet, ist während des Trainings keine Eingabe oder Anpassung durch Sie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c15bd-206">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="c15bd-207">Wie lange sollte ich das Modell trainieren?</span><span class="sxs-lookup"><span data-stu-id="c15bd-207">How long should I train for?</span></span>

<span data-ttu-id="c15bd-208">Der Modell-Generator verwendet AutoML zum Untersuchen mehrerer Modelle, um das Modell mit der besten Leistung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c15bd-208">Model Builder uses AutoML to explore multiple models to find you the best performing model.</span></span>

<span data-ttu-id="c15bd-209">Längere Trainingszeiträume ermöglichen es AutoML, mehr Modelle mit einer breiteren Palette von Einstellungen zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-209">Longer training periods allow AutoML to explore more models with a wider range of settings.</span></span>

<span data-ttu-id="c15bd-210">In der folgenden Tabelle wird die durchschnittliche Zeit zusammengefasst, die benötigt wird, um eine gute Leistung für eine Suite von Beispieldatasets auf einem lokalen Computer zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-210">The table below summarizes the average time taken to get good performance for a suite of example datasets, on a local machine.</span></span>

|<span data-ttu-id="c15bd-211">Datasetgröße</span><span class="sxs-lookup"><span data-stu-id="c15bd-211">Dataset size</span></span>|<span data-ttu-id="c15bd-212">Durchschnittliche Trainingszeit</span><span class="sxs-lookup"><span data-stu-id="c15bd-212">Average time to train</span></span>|
|------------|---------------------|
|<span data-ttu-id="c15bd-213">0 bis 10 MB</span><span class="sxs-lookup"><span data-stu-id="c15bd-213">0 - 10 MB</span></span>|<span data-ttu-id="c15bd-214">10 Sek.</span><span class="sxs-lookup"><span data-stu-id="c15bd-214">10 sec</span></span>|
|<span data-ttu-id="c15bd-215">10 bis 100 MB</span><span class="sxs-lookup"><span data-stu-id="c15bd-215">10 - 100 MB</span></span>|<span data-ttu-id="c15bd-216">10 Min.</span><span class="sxs-lookup"><span data-stu-id="c15bd-216">10 min</span></span>|
|<span data-ttu-id="c15bd-217">100 bis 500 MB</span><span class="sxs-lookup"><span data-stu-id="c15bd-217">100 - 500 MB</span></span>|<span data-ttu-id="c15bd-218">30 Min.</span><span class="sxs-lookup"><span data-stu-id="c15bd-218">30 min</span></span>|
|<span data-ttu-id="c15bd-219">500 MB bis 1 GB</span><span class="sxs-lookup"><span data-stu-id="c15bd-219">500 - 1 GB</span></span>|<span data-ttu-id="c15bd-220">60 Min.</span><span class="sxs-lookup"><span data-stu-id="c15bd-220">60 min</span></span>|
|<span data-ttu-id="c15bd-221">Mehr als 1 GB</span><span class="sxs-lookup"><span data-stu-id="c15bd-221">1 GB+</span></span>|<span data-ttu-id="c15bd-222">Mehr als 3 Stunden</span><span class="sxs-lookup"><span data-stu-id="c15bd-222">3+ hours</span></span>|

<span data-ttu-id="c15bd-223">Diese Zahlen sind nur eine Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="c15bd-223">These numbers are a guide only.</span></span> <span data-ttu-id="c15bd-224">Die genaue Trainingsdauer ist abhängig von:</span><span class="sxs-lookup"><span data-stu-id="c15bd-224">The exact length of training is dependent on:</span></span>

- <span data-ttu-id="c15bd-225">Anzahl der Merkmale (Spalten), die als Eingabe für das Modell verwendet werden</span><span class="sxs-lookup"><span data-stu-id="c15bd-225">the number of features (columns) being used to as input to the model</span></span>
- <span data-ttu-id="c15bd-226">Typ der Spalten</span><span class="sxs-lookup"><span data-stu-id="c15bd-226">the type of columns</span></span>
- <span data-ttu-id="c15bd-227">ML-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="c15bd-227">the ML task</span></span>
- <span data-ttu-id="c15bd-228">CPU-, Datenträger- und Arbeitsspeicherleistung des zum Training verwendeten Computers</span><span class="sxs-lookup"><span data-stu-id="c15bd-228">the CPU, disk, and memory performance of the machine used for training</span></span>

## <a name="evaluate"></a><span data-ttu-id="c15bd-229">Auswerten</span><span class="sxs-lookup"><span data-stu-id="c15bd-229">Evaluate</span></span>

<span data-ttu-id="c15bd-230">Auswertung ist der Prozess, bei dem gemessen wird, wie gut das Modell ist.</span><span class="sxs-lookup"><span data-stu-id="c15bd-230">Evaluation is the process of measuring how good your model is.</span></span> <span data-ttu-id="c15bd-231">Der Modell-Generator verwendet das trainierte Modell, um Vorhersagen mit neuen Testdaten zu treffen und anschließend zu messen, wie gut die Vorhersagen sind.</span><span class="sxs-lookup"><span data-stu-id="c15bd-231">Model Builder uses the trained model to make predictions with new test data, and then measures how good the predictions are.</span></span>

<span data-ttu-id="c15bd-232">Der Modell-Generator unterteilt die Trainingsdaten in einen Trainingssatz und einen Testsatz.</span><span class="sxs-lookup"><span data-stu-id="c15bd-232">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="c15bd-233">Die Trainingsdaten (80 %) werden zum Trainieren Ihres Modells verwendet, und die Testdaten (20 %) zur Evaluierung Ihres Modells zurückgehalten.</span><span class="sxs-lookup"><span data-stu-id="c15bd-233">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span>

### <a name="how-do-i-understand-my-model-performance"></a><span data-ttu-id="c15bd-234">Wie gewinne ich ein Verständnis für die Modellleistung?</span><span class="sxs-lookup"><span data-stu-id="c15bd-234">How do I understand my model performance?</span></span>

<span data-ttu-id="c15bd-235">Ein Szenario wird einer Machine Learning-Aufgabe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c15bd-235">A scenario maps to a machine learning task.</span></span> <span data-ttu-id="c15bd-236">Jede ML-Aufgabe verfügt über einen eigenen Satz von Auswertungsmetriken.</span><span class="sxs-lookup"><span data-stu-id="c15bd-236">Each ML task has its own set of evaluation metrics.</span></span>

#### <a name="value-prediction"></a><span data-ttu-id="c15bd-237">Wertvorhersage</span><span class="sxs-lookup"><span data-stu-id="c15bd-237">Value prediction</span></span>

<span data-ttu-id="c15bd-238">Die Standardmetrik für Wertvorhersageprobleme ist RSquared. Der Wert von RSquared liegt zwischen 0 und 1.</span><span class="sxs-lookup"><span data-stu-id="c15bd-238">The default metric for value prediction problems is RSquared, the value of RSquared ranges between 0 and 1.</span></span> <span data-ttu-id="c15bd-239">1 ist der bestmögliche Wert, d. h. je näher der Wert von RSquared bei 1 liegt, desto besser ist die Leistung Ihres Modells.</span><span class="sxs-lookup"><span data-stu-id="c15bd-239">1 is the best possible value or in other words the closer the value of RSquared to 1 the better your model is performing.</span></span>

<span data-ttu-id="c15bd-240">Andere erfasste Metriken wie „absolute-loss“, „squared-loss“ und „RMS-loss“ sind zusätzliche Metriken, die verwendet werden können, um die Leistung Ihres Modells zu verstehen und es mit anderen Wertvorhersagemodellen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-240">Other metrics reported such as absolute-loss, squared-loss, and RMS loss are additional metrics, which can be used to understand how your model is performing and comparing it against other value prediction models.</span></span>

#### <a name="classification-2-categories"></a><span data-ttu-id="c15bd-241">Klassifizierung (2 Kategorien)</span><span class="sxs-lookup"><span data-stu-id="c15bd-241">Classification (2 categories)</span></span>

<span data-ttu-id="c15bd-242">Die Standardmetrik für binäre Klassifizierungsprobleme ist „accuracy“ (Genauigkeit).</span><span class="sxs-lookup"><span data-stu-id="c15bd-242">The default metric for classification problems is accuracy.</span></span> <span data-ttu-id="c15bd-243">Sie definiert den Anteil an genauen Vorhersagen, die Ihr Modell anhand des Testdatasets trifft.</span><span class="sxs-lookup"><span data-stu-id="c15bd-243">Accuracy defines the proportion of correct predictions your model is making over the test dataset.</span></span> <span data-ttu-id="c15bd-244">Je näher der Wert bei 100 % oder 1,0 liegt, desto besser ist das Modell.</span><span class="sxs-lookup"><span data-stu-id="c15bd-244">The closer to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="c15bd-245">Andere gemeldete Metriken wie AUC (Area under the curve, Fläche unter der Kurve), die den Anteil der tatsächlich positiven Ergebnisse mit dem Anteil der falsch positiven Ergebnisse abgleicht, sollten größer als 0,50 sein, damit Modelle akzeptabel sind.</span><span class="sxs-lookup"><span data-stu-id="c15bd-245">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate should be greater than 0.50 for models to be acceptable.</span></span>

<span data-ttu-id="c15bd-246">Zusätzliche Metriken wie die F1-Bewertung können verwendet werden, um das Gleichgewicht zwischen Genauigkeit und Rückruf zu steuern.</span><span class="sxs-lookup"><span data-stu-id="c15bd-246">Additional metrics like F1 score can be used to control the balance between Precision and Recall.</span></span>

#### <a name="classification-3-categories"></a><span data-ttu-id="c15bd-247">Klassifizierung (3 Kategorien und mehr)</span><span class="sxs-lookup"><span data-stu-id="c15bd-247">Classification (3+ categories)</span></span>

<span data-ttu-id="c15bd-248">Die Standardmetrik für mehrklassige Klassifizierung ist „Micro Accuracy“.</span><span class="sxs-lookup"><span data-stu-id="c15bd-248">The default metric for Multi-class classification is Micro Accuracy.</span></span> <span data-ttu-id="c15bd-249">Je näher „Mico Accuracy“ bei 100 % oder 1,0 liegt, desto besser ist das Modell.</span><span class="sxs-lookup"><span data-stu-id="c15bd-249">The closer the Micro Accuracy to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="c15bd-250">Eine weitere wichtige Metrik für die mehrklassige Klassifizierung ist „Macro-accuracy“. Ähnlich wie bei „Micro-accuracy“ ist das Modell umso besser, je näher der Wert bei 1,0 liegt.</span><span class="sxs-lookup"><span data-stu-id="c15bd-250">Another important metric for Multi-class classification is Macro-accuracy, similar to Micro-accuracy the closer to 1.0 the better it is.</span></span> <span data-ttu-id="c15bd-251">Eine gute Möglichkeit, diese beiden Genauigkeitstypen zu unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="c15bd-251">A good way to think about these two types of accuracy is:</span></span>

- <span data-ttu-id="c15bd-252">Micro-accuracy: Wie oft wird ein eingehendes Ticket dem richtigen Team zugeordnet?</span><span class="sxs-lookup"><span data-stu-id="c15bd-252">Micro-accuracy: How often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="c15bd-253">Macro-accuracy: Wie oft ist für ein durchschnittliches Team ein eingehendes Ticket das richtige Ticket für das Team?</span><span class="sxs-lookup"><span data-stu-id="c15bd-253">Macro-accuracy: For an average team, how often is an incoming ticket correct for their team?</span></span>

### <a name="more-information-on-evaluation-metrics"></a><span data-ttu-id="c15bd-254">Weitere Informationen zu Auswertungsmetriken</span><span class="sxs-lookup"><span data-stu-id="c15bd-254">More information on evaluation metrics</span></span>

<span data-ttu-id="c15bd-255">Weitere Informationen finden Sie unter [Metriken für die Modellevaluierung](resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="c15bd-255">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="c15bd-256">Verbessern</span><span class="sxs-lookup"><span data-stu-id="c15bd-256">Improve</span></span>

<span data-ttu-id="c15bd-257">Wenn Ihr Modellleistungswert nicht so gut ist, wie Sie es sich wünschen, haben Sie die folgenden Möglichkeit:</span><span class="sxs-lookup"><span data-stu-id="c15bd-257">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="c15bd-258">Längeres Trainieren.</span><span class="sxs-lookup"><span data-stu-id="c15bd-258">Train for a longer period of time.</span></span> <span data-ttu-id="c15bd-259">Je mehr Zeit einer automatisierten Machine Learning-Engine zum Trainieren zur Verfügung steht, desto mehr Algorithmen und Einstellungen kann sie ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="c15bd-259">With more time, the automated machine learning engine experiments with more algorithms and settings.</span></span>

- <span data-ttu-id="c15bd-260">Weitere Daten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-260">Add more data.</span></span> <span data-ttu-id="c15bd-261">Manchmal reicht die Datenmenge nicht aus, um ein hochwertiges Machine Learning-Modell zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="c15bd-261">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="c15bd-262">Ihre Daten ausgleichen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-262">Balance your data.</span></span> <span data-ttu-id="c15bd-263">Achten Sie bei Klassifizierungsaufgaben darauf, dass der Trainingssatz über die Kategorien hinweg gleichmäßig verteilt ist.</span><span class="sxs-lookup"><span data-stu-id="c15bd-263">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="c15bd-264">Wenn Sie beispielsweise vier Klassen für 100 Trainingsbeispiele haben und die beiden ersten Klassen (tag1 und tag2) für 90 Datensätze verwendet werden, die anderen beiden (tag3 und tag4) aber nur für die restlichen 10 Datensätze, kann das dazu führen, dass Ihr Modell Schwierigkeiten hat, tag3 oder tag4 korrekt vorherzusagen, da die Daten nicht gleichmäßig verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="c15bd-264">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="c15bd-265">Code</span><span class="sxs-lookup"><span data-stu-id="c15bd-265">Code</span></span>

<span data-ttu-id="c15bd-266">Nach der Evaluierungsphase gibt der Modell-Generator eine Modelldatei und einen Code aus, mit dem Sie das Modell zur Ihrer Anwendung hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="c15bd-266">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="c15bd-267">ML.NET-Modelle werden als Zip-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c15bd-267">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="c15bd-268">Der Code zum Laden und Verwenden Ihres Modells wird als neues Projekt in Ihrer Projektmappe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c15bd-268">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="c15bd-269">Der Modell-Generator fügt auch eine Beispiel-Konsolen-App hinzu, die Sie ausführen können, um Ihr Modell in Aktion zu sehen.</span><span class="sxs-lookup"><span data-stu-id="c15bd-269">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="c15bd-270">Darüber hinaus gibt der Modell-Generator den Code aus, der das Modell generiert hat, sodass Sie die Schritte zur Generierung des Modells nachvollziehen können.</span><span class="sxs-lookup"><span data-stu-id="c15bd-270">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="c15bd-271">Sie können den Modelltrainingscode auch verwenden, um Ihr Modell mit neuen Daten zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="c15bd-271">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="c15bd-272">Ausblick</span><span class="sxs-lookup"><span data-stu-id="c15bd-272">What's next?</span></span>

<span data-ttu-id="c15bd-273">[Installieren](how-to-guides/install-model-builder.md) Sie die Modellgeneratorerweiterung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c15bd-273">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="c15bd-274">Probieren Sie ein [Szenario für die Preisvorhersage oder Regression](tutorials/predict-prices-with-model-builder.md) aus.</span><span class="sxs-lookup"><span data-stu-id="c15bd-274">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
