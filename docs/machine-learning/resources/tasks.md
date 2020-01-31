---
title: Machine Learning-Aufgaben
description: Untersuchen Sie die anderen in ML.NET unterstützten Machine Learning-Aufgaben und zugehörigen Aufgaben.
ms.date: 12/23/2019
ms.openlocfilehash: 6cd41065e668375537b9816ef7a208a65e0a523b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745102"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="698be-103">Machine Learning-Aufgaben in ML.NET</span><span class="sxs-lookup"><span data-stu-id="698be-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="698be-104">Bei einer Machine Learning-Aufgabe handelt es sich um den Typ der Vorhersage oder Rückschlüsse, basierend auf dem Problem oder der Frage, das bzw. die gestellt wird, und den verfügbaren Daten.</span><span class="sxs-lookup"><span data-stu-id="698be-104">A machine learning task is the type of prediction or inference being made, based on the problem or question that is being asked, and the available data.</span></span> <span data-ttu-id="698be-105">Beispielsweise ordnet die Klassifizierungsaufgabe Daten Kategorien zu, und die Clusteringaufgabe gruppiert Daten nach ihrer Ähnlichkeit.</span><span class="sxs-lookup"><span data-stu-id="698be-105">For example, the classification task assigns data to categories, and the clustering task groups data according to similarity.</span></span>

<span data-ttu-id="698be-106">Machine Learning-Aufgaben basieren auf Mustern in den Daten, anstatt explizit programmiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="698be-106">Machine learning tasks rely on patterns in the data rather than being explicitly programmed.</span></span>

<span data-ttu-id="698be-107">In diesem Artikel werden die verschiedenen Machine Learning-Aufgaben beschrieben, unter denen Sie in ML.NET auswählen können, sowie einige häufige Anwendungsfälle.</span><span class="sxs-lookup"><span data-stu-id="698be-107">This article describes the different machine learning tasks that you can choose from in ML.NET and some common use cases.</span></span>

<span data-ttu-id="698be-108">Nachdem Sie entschieden haben, welche Aufgabe auf Ihr Szenario zutrifft, müssen Sie den besten Algorithmus zum Trainieren Ihres Modells auswählen.</span><span class="sxs-lookup"><span data-stu-id="698be-108">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="698be-109">Die verfügbaren Algorithmen sind im Abschnitt zur jeweiligen Aufgabe aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="698be-109">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="698be-110">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="698be-110">Binary classification</span></span>

<span data-ttu-id="698be-111">Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um vorherzusagen, zu welcher von zwei Klassen (Kategorien) eine Dateninstanz gehört.</span><span class="sxs-lookup"><span data-stu-id="698be-111">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="698be-112">Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele, wo jede Bezeichnung entweder die Ganzzahl 0 oder 1 ist.</span><span class="sxs-lookup"><span data-stu-id="698be-112">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="698be-113">Die Ausgabe eines binären Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="698be-113">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="698be-114">Zu den Beispielen binärer Klassifizierungsszenarien zählen:</span><span class="sxs-lookup"><span data-stu-id="698be-114">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="698be-115">[Verstehen des Standpunkts in Twitter-Kommentaren](../tutorials/sentiment-analysis.md) als „positiv“ oder „negativ“.</span><span class="sxs-lookup"><span data-stu-id="698be-115">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="698be-116">Diagnostizieren, ob bei einem Patienten eine bestimmte Krankheit vorliegt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="698be-116">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="698be-117">Treffen einer Entscheidung, um eine E-Mail-Nachricht als „Spam“ zu markieren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="698be-117">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="698be-118">Ermitteln, ob ein Foto ein bestimmtes Element, z. B. einen Hund oder eine Frucht, enthält oder nicht</span><span class="sxs-lookup"><span data-stu-id="698be-118">Determining if a photo contains a particular item or not, such as a dog or fruit.</span></span>

<span data-ttu-id="698be-119">Weitere Informationen finden Sie auf Wikipedia im Artikel zur [binären Klassifizierung](https://en.wikipedia.org/wiki/Binary_classification).</span><span class="sxs-lookup"><span data-stu-id="698be-119">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="698be-120">Trainer für die binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="698be-120">Binary classification trainers</span></span>

<span data-ttu-id="698be-121">Sie können ein binäres Klassifizierungsmodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="698be-121">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="698be-122">Eingaben und Ausgaben für die binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="698be-122">Binary classification inputs and outputs</span></span>

<span data-ttu-id="698be-123">Für optimale Ergebnisse bei der binären Klassifizierung sollten die Trainingsdaten ausgeglichen sein (d.h. eine gleiche Anzahl von positiven und negativen Trainingsdaten).</span><span class="sxs-lookup"><span data-stu-id="698be-123">For best results with binary classification, the training data should be balanced (that is, equal numbers of positive and negative training data).</span></span> <span data-ttu-id="698be-124">Fehlende Werte sollten vor dem Training bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="698be-124">Missing values should be handled before training.</span></span>

<span data-ttu-id="698be-125">Die Daten in der Spalte für die Eingabezeichnung müssen <xref:System.Boolean> sein.</span><span class="sxs-lookup"><span data-stu-id="698be-125">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="698be-126">Die Daten in der Spalte für die Eingabefeatures müssen ein Vektor fester Größe von <xref:System.Single> sein.</span><span class="sxs-lookup"><span data-stu-id="698be-126">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="698be-127">Diese Trainer geben die folgenden Spalten aus:</span><span class="sxs-lookup"><span data-stu-id="698be-127">These trainers output the following columns:</span></span>

| <span data-ttu-id="698be-128">Name der Ausgabespalte</span><span class="sxs-lookup"><span data-stu-id="698be-128">Output Column Name</span></span> | <span data-ttu-id="698be-129">Spaltentyp</span><span class="sxs-lookup"><span data-stu-id="698be-129">Column Type</span></span> | <span data-ttu-id="698be-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="698be-130">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="698be-131">Die vom Modell berechnete unformatierte Bewertung</span><span class="sxs-lookup"><span data-stu-id="698be-131">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="698be-132">Der vorhergesagte Bezeichnung, basierend auf dem Abzeichnen der Bewertung.</span><span class="sxs-lookup"><span data-stu-id="698be-132">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="698be-133">Eine negative Bewertung wird `false` und eine positive Bewertung wird `true` zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="698be-133">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="698be-134">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="698be-134">Multiclass classification</span></span>

<span data-ttu-id="698be-135">Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um die Klasse (Kategorie) einer Dateninstanz vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="698be-135">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="698be-136">Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele.</span><span class="sxs-lookup"><span data-stu-id="698be-136">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="698be-137">Jede Bezeichnung beginnt normalerweise als Text.</span><span class="sxs-lookup"><span data-stu-id="698be-137">Each label normally starts as text.</span></span> <span data-ttu-id="698be-138">Sie wird dann über TermTransform ausgeführt, wodurch sie in den (numerischen) Schlüsseltyp konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="698be-138">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="698be-139">Die Ausgabe eines Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="698be-139">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="698be-140">Zu den Beispielen für Multiklassen-Klassifizierungsszenarien zählen:</span><span class="sxs-lookup"><span data-stu-id="698be-140">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="698be-141">Ermitteln der Rasse eines Hundes als „Sibirischer Husky“, „Golden Retriever“, „Pudel“ usw.</span><span class="sxs-lookup"><span data-stu-id="698be-141">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="698be-142">Verstehen von Filmkritiken als „positiv“, „neutral“ oder „negativ“.</span><span class="sxs-lookup"><span data-stu-id="698be-142">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="698be-143">Kategorisieren von Hoteltests in „Lage“, „Preis“, „Sauberkeit“ usw.</span><span class="sxs-lookup"><span data-stu-id="698be-143">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="698be-144">Weitere Informationen finden Sie auf Wikipedia im Artikel zur [Multiklassenklassifizierung](https://en.wikipedia.org/wiki/Multiclass_classification).</span><span class="sxs-lookup"><span data-stu-id="698be-144">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="698be-145">One-vs-All (OvA) aktualisiert alle [Binärklassifizierungs-Lernmodule](#binary-classification), sodass sie Multiklassendatasets bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="698be-145">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="698be-146">Weitere Informationen finden Sie in [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span><span class="sxs-lookup"><span data-stu-id="698be-146">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="698be-147">Trainer für die Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="698be-147">Multiclass classification trainers</span></span>

<span data-ttu-id="698be-148">Sie können ein Modell zur Multiklassenklassifizierung mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="698be-148">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>
* <xref:Microsoft.ML.Vision.ImageClassificationTrainer>

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="698be-149">Eingaben und Ausgaben für die Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="698be-149">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="698be-150">Die Daten in der Spalte für die Eingabezeichnung müssen vom Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) sein.</span><span class="sxs-lookup"><span data-stu-id="698be-150">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="698be-151">Die Featurespalte muss ein Vektor fester Größe von <xref:System.Single> sein.</span><span class="sxs-lookup"><span data-stu-id="698be-151">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="698be-152">Der Trainer gibt folgende Daten aus:</span><span class="sxs-lookup"><span data-stu-id="698be-152">This trainer outputs the following:</span></span>

| <span data-ttu-id="698be-153">Ausgabename</span><span class="sxs-lookup"><span data-stu-id="698be-153">Output Name</span></span> | <span data-ttu-id="698be-154">Typ</span><span class="sxs-lookup"><span data-stu-id="698be-154">Type</span></span> | <span data-ttu-id="698be-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="698be-155">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="698be-156">Vektor von <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="698be-156">Vector of <xref:System.Single></span></span> | <span data-ttu-id="698be-157">Die Bewertungen aller Klassen.</span><span class="sxs-lookup"><span data-stu-id="698be-157">The scores of all classes.</span></span> <span data-ttu-id="698be-158">Ein höherer Wert bedeutet eine höhere Wahrscheinlichkeit, in die zugehörige Klasse zu fallen.</span><span class="sxs-lookup"><span data-stu-id="698be-158">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="698be-159">Wenn das i-te Element den größten Wert hat, wäre der vorhergesagte Bezeichnungsindex i.</span><span class="sxs-lookup"><span data-stu-id="698be-159">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="698be-160">Beachten Sie, dass „i“ ein nullbasierter Index ist.</span><span class="sxs-lookup"><span data-stu-id="698be-160">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="698be-161">Typ [key](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="698be-161">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="698be-162">Der Index der vorhergesagten Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="698be-162">The predicted label's index.</span></span> <span data-ttu-id="698be-163">Wenn sein Wert i ist, wäre die eigentliche Bezeichnung die i-te Kategorie des Typs der Schlüssel-Wert-Eingabebezeichnung.</span><span class="sxs-lookup"><span data-stu-id="698be-163">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="698be-164">Regression</span><span class="sxs-lookup"><span data-stu-id="698be-164">Regression</span></span>

<span data-ttu-id="698be-165">Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, die verwendet wird, um den Wert der Bezeichnung aus einem Satz verwandter Features vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="698be-165">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="698be-166">Die Bezeichnung kann einen realen Wert haben und stammt nicht aus einem endlichen Satz von Werten wie bei Klassifizierungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="698be-166">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="698be-167">Regressionsalgorithmen modellieren die Abhängigkeit der Bezeichnung von den zugehörigen verwandten Features, um zu bestimmen, wie sich die Bezeichnung ändert, wenn die Werte der Features variiert werden.</span><span class="sxs-lookup"><span data-stu-id="698be-167">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="698be-168">Die Eingabe eines Regressionsalgorithmus ist eine Reihe von Beispielen mit Bezeichnungen bekannter Werte.</span><span class="sxs-lookup"><span data-stu-id="698be-168">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="698be-169">Die Ausgabe eines Regressionsalgorithmus ist eine Funktion, die Sie verwenden können, um den Bezeichnungswert für einen neuen Satz von Eingabefeatures vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="698be-169">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="698be-170">Beispiele für Regressionsszenarien sind:</span><span class="sxs-lookup"><span data-stu-id="698be-170">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="698be-171">Hauspreisvorhersagen basierend auf Hausattributen wie der Anzahl von Schlafzimmern, Lage und Größe.</span><span class="sxs-lookup"><span data-stu-id="698be-171">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="698be-172">Vorhersagen zukünftiger Aktienkurse basierend auf historischen Daten und aktuellen Markttrends.</span><span class="sxs-lookup"><span data-stu-id="698be-172">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="698be-173">Vorhersagen für den Verkauf eines Produkts basierend auf Werbebudgets.</span><span class="sxs-lookup"><span data-stu-id="698be-173">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="698be-174">Regressionstrainer</span><span class="sxs-lookup"><span data-stu-id="698be-174">Regression trainers</span></span>

<span data-ttu-id="698be-175">Sie können ein Regressionsmodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="698be-175">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="698be-176">Eingaben und Ausgaben für die Regression</span><span class="sxs-lookup"><span data-stu-id="698be-176">Regression inputs and outputs</span></span>

<span data-ttu-id="698be-177">Die Daten in der Spalte für die Eingabezeichnung müssen <xref:System.Single> sein.</span><span class="sxs-lookup"><span data-stu-id="698be-177">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="698be-178">Die Trainer für diese Ausgabe geben folgende Daten aus:</span><span class="sxs-lookup"><span data-stu-id="698be-178">The trainers for this task output the following:</span></span>

| <span data-ttu-id="698be-179">Ausgabename</span><span class="sxs-lookup"><span data-stu-id="698be-179">Output Name</span></span> | <span data-ttu-id="698be-180">Typ</span><span class="sxs-lookup"><span data-stu-id="698be-180">Type</span></span> | <span data-ttu-id="698be-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="698be-181">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="698be-182">Die vom Modell vorhergesagte unformatierte Bewertung</span><span class="sxs-lookup"><span data-stu-id="698be-182">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="698be-183">Clusterbildung</span><span class="sxs-lookup"><span data-stu-id="698be-183">Clustering</span></span>

<span data-ttu-id="698be-184">Eine [nicht überwachte Machine Learning](glossary.md#unsupervised-machine-learning)-Aufgabe, die verwendet wird, um Instanzen von Daten in Clustern zu gruppieren, die ähnliche Merkmale aufweisen.</span><span class="sxs-lookup"><span data-stu-id="698be-184">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="698be-185">Die Clusterbildung kann auch zum Identifizieren von Beziehungen in einem Dataset verwendet werden, die Sie möglicherweise nicht logisch durch Durchsuchen oder einfache Beobachtung ableiten können.</span><span class="sxs-lookup"><span data-stu-id="698be-185">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="698be-186">Die Eingaben und Ausgaben eines Clusterbildungsalgorithmus hängen von der ausgewählten Methodik ab.</span><span class="sxs-lookup"><span data-stu-id="698be-186">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="698be-187">Sie können einen verteilungs-, schwerpunkt-, konnektivitäts- oder dichtebasierten Ansatz wählen.</span><span class="sxs-lookup"><span data-stu-id="698be-187">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="698be-188">ML.NET unterstützt derzeit einen schwerpunktbasierten Ansatz bei Verwendung der K-Means-Clusterbildung.</span><span class="sxs-lookup"><span data-stu-id="698be-188">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="698be-189">Beispiele für Clusterbildungsszenarien sind:</span><span class="sxs-lookup"><span data-stu-id="698be-189">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="698be-190">Grundlegendes zu Segmenten von Hotelgästen basierend auf Gewohnheiten und Merkmalen der Hotelauswahl.</span><span class="sxs-lookup"><span data-stu-id="698be-190">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="698be-191">Identifizieren von Kundensegmenten und demografischen Daten, um gezielte Werbekampagnen erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="698be-191">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="698be-192">Kategorisieren des Lagerbestands basierend auf Produktionsmetriken.</span><span class="sxs-lookup"><span data-stu-id="698be-192">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="698be-193">Trainerclustering</span><span class="sxs-lookup"><span data-stu-id="698be-193">Clustering trainer</span></span>

<span data-ttu-id="698be-194">Sie können ein Modell zur Clusterbildung mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="698be-194">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="698be-195">Eingaben und Ausgaben für das Clustering</span><span class="sxs-lookup"><span data-stu-id="698be-195">Clustering inputs and outputs</span></span>

<span data-ttu-id="698be-196">Die Daten der Eingabefeatures müssen <xref:System.Single> sein.</span><span class="sxs-lookup"><span data-stu-id="698be-196">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="698be-197">Es sind keine Bezeichnungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="698be-197">No labels are needed.</span></span>

<span data-ttu-id="698be-198">Der Trainer gibt folgende Daten aus:</span><span class="sxs-lookup"><span data-stu-id="698be-198">This trainer outputs the following:</span></span>

| <span data-ttu-id="698be-199">Ausgabename</span><span class="sxs-lookup"><span data-stu-id="698be-199">Output Name</span></span> | <span data-ttu-id="698be-200">Typ</span><span class="sxs-lookup"><span data-stu-id="698be-200">Type</span></span> | <span data-ttu-id="698be-201">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="698be-201">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="698be-202">Vektor von <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="698be-202">vector of <xref:System.Single></span></span> | <span data-ttu-id="698be-203">Die Abstände der angegebenen Daten weisen auf die Schwerpunkte aller Cluster hin.</span><span class="sxs-lookup"><span data-stu-id="698be-203">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="698be-204">Typ [key](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="698be-204">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="698be-205">Der Index des nächsten Clusters, der durch das Modell vorhergesagt wird.</span><span class="sxs-lookup"><span data-stu-id="698be-205">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="698be-206">Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="698be-206">Anomaly detection</span></span>

<span data-ttu-id="698be-207">Diese Aufgabe erstellt ein Anomalieerkennungsmodell mithilfe der Principal Component Analysis (PCA).</span><span class="sxs-lookup"><span data-stu-id="698be-207">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="698be-208">Die Anomalieerkennung auf PCA-Basis unterstützt Sie beim Erstellen eines Modells in Szenarien, in denen mühelos Trainingsdaten aus einer Klasse, z.B. gültige Transaktionen, aber nur schwer ausreichende Beispiele für die gesuchten Anomalien zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="698be-208">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="698be-209">Als bewährtes Verfahren im Machine Learning wird PCA häufig in der explorativen Datenanalyse verwendet, da es die innere Struktur der Daten zeigt und die Abweichung in den Daten erläutert.</span><span class="sxs-lookup"><span data-stu-id="698be-209">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="698be-210">PCA arbeitet mit der Analyse von Daten, die mehrere Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="698be-210">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="698be-211">Das Verfahren sucht nach Korrelationen zwischen den Variablen und bestimmt die Kombination der Werte, die am besten Unterschiede in den Ergebnissen erfassen.</span><span class="sxs-lookup"><span data-stu-id="698be-211">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="698be-212">Mit diesen kombinierten Featurewerten wird ein kompakterer Featurebereich erstellt, der als „Hauptkomponenten“ bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="698be-212">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="698be-213">Die Anomalieerkennung umfasst viele wichtige Machine Learning-Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="698be-213">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="698be-214">Identifizieren potenziell betrügerischer Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="698be-214">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="698be-215">Erlernen von Mustern, die anzeigen, dass der Versuch unternommen wurde, in das Netzwerk einzudringen.</span><span class="sxs-lookup"><span data-stu-id="698be-215">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="698be-216">Finden anomaler Patientencluster.</span><span class="sxs-lookup"><span data-stu-id="698be-216">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="698be-217">Überprüfen von Werten, die in ein System eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="698be-217">Checking values entered into a system.</span></span>

<span data-ttu-id="698be-218">Da Anomalien laut Definition selten sind, kann es schwierig sein, eine repräsentative Stichprobe von Daten zu sammeln, die für die Modellierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="698be-218">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="698be-219">Die Algorithmen, die zu dieser Kategorie gehören, wurden insbesondere daraufhin konzipiert, den wesentlichen Herausforderungen beim Erstellen und Trainieren von Modellen mithilfe von unausgeglichenen Datasets gerecht zu werden.</span><span class="sxs-lookup"><span data-stu-id="698be-219">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="698be-220">Trainer für die Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="698be-220">Anomaly detection trainer</span></span>

<span data-ttu-id="698be-221">Sie können ein Anomalieerkennungsmodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="698be-221">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="698be-222">Eingaben und Ausgaben für die Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="698be-222">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="698be-223">Die Eingabefeatures müssen ein Vektor fester Größe von <xref:System.Single> sein.</span><span class="sxs-lookup"><span data-stu-id="698be-223">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="698be-224">Der Trainer gibt folgende Daten aus:</span><span class="sxs-lookup"><span data-stu-id="698be-224">This trainer outputs the following:</span></span>

| <span data-ttu-id="698be-225">Ausgabename</span><span class="sxs-lookup"><span data-stu-id="698be-225">Output Name</span></span> | <span data-ttu-id="698be-226">Typ</span><span class="sxs-lookup"><span data-stu-id="698be-226">Type</span></span> | <span data-ttu-id="698be-227">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="698be-227">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="698be-228">Die nicht-negative, unbegrenzte Bewertung, die durch das Anomalieerkennungsmodell berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="698be-228">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="698be-229">Ein TRUE/FALSE-Wert, der angibt, ob es sich bei der Eingabe um eine Anomalie (PredictedLabel=true) oder um keine Anomalie (PredictedLabel=false) handelt.</span><span class="sxs-lookup"><span data-stu-id="698be-229">A true/false value representing whether the input is an anomaly (PredictedLabel=true) or not (PredictedLabel=false)</span></span> |

## <a name="ranking"></a><span data-ttu-id="698be-230">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="698be-230">Ranking</span></span>

<span data-ttu-id="698be-231">Eine Rangfolgenaufgabe erstellt für einen Satz bezeichneter Beispiele eine Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="698be-231">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="698be-232">Dieser Beispielsatz besteht aus Instanzengruppen, die nach bestimmten Kriterien bewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="698be-232">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="698be-233">Die Rangfolgenbezeichnungen sind {0, 1, 2, 3, 4} für jede Instanz.</span><span class="sxs-lookup"><span data-stu-id="698be-233">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="698be-234">Die Rangfolgenfunktion wird dafür trainiert, neue Instanzengruppen mit unbekannten Bewertungen für jede Instanz in die Rangfolge einzuordnen.</span><span class="sxs-lookup"><span data-stu-id="698be-234">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="698be-235">ML.NET-Rangfolgen-Lernmodule basieren auf [Machine Learning-Rangfolge](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="698be-235">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="698be-236">Trainingsalgorithmen für Rangfolge</span><span class="sxs-lookup"><span data-stu-id="698be-236">Ranking training algorithms</span></span>

<span data-ttu-id="698be-237">Sie können ein Rangfolgemodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="698be-237">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="698be-238">Eingaben und Ausgaben für die Rangfolge</span><span class="sxs-lookup"><span data-stu-id="698be-238">Ranking input and outputs</span></span>

<span data-ttu-id="698be-239">Der Datentyp für die Eingabebezeichnung muss ein Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) oder <xref:System.Single> sein.</span><span class="sxs-lookup"><span data-stu-id="698be-239">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="698be-240">Der Wert der Bezeichnung bestimmt die Relevanz, wobei höhere Werte eine höhere Relevanz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="698be-240">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="698be-241">Wenn die Bezeichnung vom Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) ist, dann ist der Schlüsselindex der Relevanzwert, wobei der kleinste Index der am wenigsten relevante ist.</span><span class="sxs-lookup"><span data-stu-id="698be-241">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="698be-242">Wenn die Bezeichnung ein <xref:System.Single> ist, zeigen höhere Werte eine höhere Relevanz an.</span><span class="sxs-lookup"><span data-stu-id="698be-242">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="698be-243">Die Featuredaten müssen ein Vektor mit fester Größe von <xref:System.Single> sein, und die Gruppenspalte der Eingabezeilen muss vom Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) sein.</span><span class="sxs-lookup"><span data-stu-id="698be-243">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="698be-244">Der Trainer gibt folgende Daten aus:</span><span class="sxs-lookup"><span data-stu-id="698be-244">This trainer outputs the following:</span></span>

| <span data-ttu-id="698be-245">Ausgabename</span><span class="sxs-lookup"><span data-stu-id="698be-245">Output Name</span></span> | <span data-ttu-id="698be-246">Typ</span><span class="sxs-lookup"><span data-stu-id="698be-246">Type</span></span> | <span data-ttu-id="698be-247">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="698be-247">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="698be-248">Die unbegrenzte Bewertung, die vom Modell berechnet wurde, um die Vorhersage zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="698be-248">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="698be-249">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="698be-249">Recommendation</span></span>

<span data-ttu-id="698be-250">Mit einer Empfehlungsaufgabe kann eine Liste empfohlener Produkte oder Dienste erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="698be-250">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="698be-251">ML.NET verwendet für Empfehlungen [Matrixfaktorisierung (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), einen Algorithmus für [kollaboratives Filtern](https://en.wikipedia.org/wiki/Collaborative_filtering), wenn Ihr Katalog Verlaufsproduktbewertungs-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="698be-251">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="698be-252">Ihnen liegen z.B. Verlaufsfilmbewertungs-Daten Ihrer Benutzer vor, und Sie möchten andere Filme empfehlen, die sie wahrscheinlich als Nächstes sehen möchten.</span><span class="sxs-lookup"><span data-stu-id="698be-252">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="698be-253">Trainingsalgorithmen für Empfehlung</span><span class="sxs-lookup"><span data-stu-id="698be-253">Recommendation training algorithms</span></span>

<span data-ttu-id="698be-254">Sie können ein Empfehlungsmodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="698be-254">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>

## <a name="forecasting"></a><span data-ttu-id="698be-255">Vorhersage</span><span class="sxs-lookup"><span data-stu-id="698be-255">Forecasting</span></span>

<span data-ttu-id="698be-256">Bei der Aufgabe „Vorhersage“ werden anhand von Daten aus vergangenen Zeitreihen Vorhersagen über zukünftiges Verhalten getroffen.</span><span class="sxs-lookup"><span data-stu-id="698be-256">The forecasting task use past time-series data to make predictions about future behavior.</span></span> <span data-ttu-id="698be-257">Sie eignet sich unter anderem für Wettervorhersagen, Vorhersagen zum Saisonumsatz und Predictive Maintenance.</span><span class="sxs-lookup"><span data-stu-id="698be-257">Scenarios applicable to forecasting include weather forecasting, seasonal sales predictions, and predictive maintenance,</span></span>

### <a name="forecasting-trainers"></a><span data-ttu-id="698be-258">Trainer für die Aufgabe „Vorhersage“</span><span class="sxs-lookup"><span data-stu-id="698be-258">Forecasting trainers</span></span>

<span data-ttu-id="698be-259">Sie können ein Vorhersagemodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="698be-259">You can train a forecasting model with the following algorithm:</span></span>

<xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa*>
