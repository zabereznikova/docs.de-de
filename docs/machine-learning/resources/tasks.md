---
title: Machine Learning-Aufgaben – ML.NET
description: Untersuchen Sie die anderen in ML.NET unterstützten Machine Learning-Aufgaben und zugehörigen Aufgaben.
ms.custom: seodec18
ms.date: 04/12/2019
author: natke
ms.openlocfilehash: bfed9cf12f8d539c4327549e5305415ce096e022
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613160"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="27737-103">Machine Learning-Aufgaben in ML.NET</span><span class="sxs-lookup"><span data-stu-id="27737-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="27737-104">Wenn Sie ein Machine Learning-Modell erstellen, müssen Sie zuerst definieren, was Sie mit Ihren Daten erreichen möchten.</span><span class="sxs-lookup"><span data-stu-id="27737-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="27737-105">Dadurch können Sie die richtige Machine Learning-Aufgabe für Ihren Zweck auswählen.</span><span class="sxs-lookup"><span data-stu-id="27737-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="27737-106">In der folgenden Liste werden die verschiedenen Machine Learning-Aufgaben beschrieben, unter denen Sie auswählen können, und einige häufige Anwendungsfälle.</span><span class="sxs-lookup"><span data-stu-id="27737-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="27737-107">Nachdem Sie entschieden haben, welche Aufgabe auf Ihr Szenario zutrifft, müssen Sie den besten Algorithmus zum Trainieren Ihres Modells auswählen.</span><span class="sxs-lookup"><span data-stu-id="27737-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="27737-108">Die verfügbaren Algorithmen sind im Abschnitt zur jeweiligen Aufgabe aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="27737-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="27737-109">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="27737-109">Binary classification</span></span>

<span data-ttu-id="27737-110">Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um vorherzusagen, zu welcher von zwei Klassen (Kategorien) eine Dateninstanz gehört.</span><span class="sxs-lookup"><span data-stu-id="27737-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="27737-111">Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele, wo jede Bezeichnung entweder die Ganzzahl 0 oder 1 ist.</span><span class="sxs-lookup"><span data-stu-id="27737-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="27737-112">Die Ausgabe eines binären Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="27737-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="27737-113">Zu den Beispielen binärer Klassifizierungsszenarien zählen:</span><span class="sxs-lookup"><span data-stu-id="27737-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="27737-114">[Verstehen des Standpunkts in Twitter-Kommentaren](../tutorials/sentiment-analysis.md) als „positiv“ oder „negativ“.</span><span class="sxs-lookup"><span data-stu-id="27737-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="27737-115">Diagnostizieren, ob bei einem Patienten eine bestimmte Krankheit vorliegt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="27737-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="27737-116">Treffen einer Entscheidung, um eine E-Mail-Nachricht als „Spam“ zu markieren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="27737-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="27737-117">Bestimmen, ob ein Foto einen Hund oder Obst zeigt.</span><span class="sxs-lookup"><span data-stu-id="27737-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="27737-118">Weitere Informationen finden Sie auf Wikipedia im Artikel zur [binären Klassifizierung](https://en.wikipedia.org/wiki/Binary_classification).</span><span class="sxs-lookup"><span data-stu-id="27737-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-training-algorithms"></a><span data-ttu-id="27737-119">Trainingsalgorithmen für binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="27737-119">Binary Classification Training Algorithms</span></span>

<span data-ttu-id="27737-120">Sie können ein binäres Klassifizierungsmodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="27737-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>

## <a name="multiclass-classification"></a><span data-ttu-id="27737-121">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="27737-121">Multiclass classification</span></span>

<span data-ttu-id="27737-122">Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um die Klasse (Kategorie) einer Dateninstanz vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="27737-122">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="27737-123">Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele.</span><span class="sxs-lookup"><span data-stu-id="27737-123">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="27737-124">Jede Bezeichnung beginnt normalerweise als Text.</span><span class="sxs-lookup"><span data-stu-id="27737-124">Each label normally starts as text.</span></span> <span data-ttu-id="27737-125">Sie wird dann über TermTransform ausgeführt, wodurch sie in den (numerischen) Schlüsseltyp konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="27737-125">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="27737-126">Die Ausgabe eines Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="27737-126">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="27737-127">Zu den Beispielen für Multiklassen-Klassifizierungsszenarien zählen:</span><span class="sxs-lookup"><span data-stu-id="27737-127">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="27737-128">Ermitteln der Rasse eines Hundes als „Sibirischer Husky“, „Golden Retriever“, „Pudel“ usw.</span><span class="sxs-lookup"><span data-stu-id="27737-128">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="27737-129">Verstehen von Filmkritiken als „positiv“, „neutral“ oder „negativ“.</span><span class="sxs-lookup"><span data-stu-id="27737-129">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="27737-130">Kategorisieren von Hoteltests in „Lage“, „Preis“, „Sauberkeit“ usw.</span><span class="sxs-lookup"><span data-stu-id="27737-130">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="27737-131">Weitere Informationen finden Sie auf Wikipedia im Artikel zur [Multiklassenklassifizierung](https://en.wikipedia.org/wiki/Multiclass_classification).</span><span class="sxs-lookup"><span data-stu-id="27737-131">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="27737-132">One-vs-All (OvA) aktualisiert alle [Binärklassifizierungs-Lernmodule](#binary-classification), sodass sie Multiklassendatasets bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="27737-132">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="27737-133">Weitere Informationen finden Sie in [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span><span class="sxs-lookup"><span data-stu-id="27737-133">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-training-algorithms"></a><span data-ttu-id="27737-134">Trainingsalgorithmen für Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="27737-134">Multiclass Classification training algorithms</span></span>

<span data-ttu-id="27737-135">Sie können ein Modell zur Multiklassenklassifizierung mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="27737-135">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

## <a name="regression"></a><span data-ttu-id="27737-136">Regression</span><span class="sxs-lookup"><span data-stu-id="27737-136">Regression</span></span>

<span data-ttu-id="27737-137">Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, die verwendet wird, um den Wert der Bezeichnung aus einem Satz verwandter Features vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="27737-137">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="27737-138">Die Bezeichnung kann einen realen Wert haben und stammt nicht aus einem endlichen Satz von Werten wie bei Klassifizierungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="27737-138">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="27737-139">Regressionsalgorithmen modellieren die Abhängigkeit der Bezeichnung von den zugehörigen verwandten Features, um zu bestimmen, wie sich die Bezeichnung ändert, wenn die Werte der Features variiert werden.</span><span class="sxs-lookup"><span data-stu-id="27737-139">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="27737-140">Die Eingabe eines Regressionsalgorithmus ist eine Reihe von Beispielen mit Bezeichnungen bekannter Werte.</span><span class="sxs-lookup"><span data-stu-id="27737-140">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="27737-141">Die Ausgabe eines Regressionsalgorithmus ist eine Funktion, die Sie verwenden können, um den Bezeichnungswert für einen neuen Satz von Eingabefeatures vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="27737-141">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="27737-142">Beispiele für Regressionsszenarien sind:</span><span class="sxs-lookup"><span data-stu-id="27737-142">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="27737-143">Hauspreisvorhersagen basierend auf Hausattributen wie der Anzahl von Schlafzimmern, Lage und Größe.</span><span class="sxs-lookup"><span data-stu-id="27737-143">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="27737-144">Vorhersagen zukünftiger Aktienkurse basierend auf historischen Daten und aktuellen Markttrends.</span><span class="sxs-lookup"><span data-stu-id="27737-144">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="27737-145">Vorhersagen für den Verkauf eines Produkts basierend auf Werbebudgets.</span><span class="sxs-lookup"><span data-stu-id="27737-145">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-training-algorithms"></a><span data-ttu-id="27737-146">Trainingsalgorithmen für Regression</span><span class="sxs-lookup"><span data-stu-id="27737-146">Regression training algorithms</span></span>

<span data-ttu-id="27737-147">Sie können ein Regressionsmodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="27737-147">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>

## <a name="clustering"></a><span data-ttu-id="27737-148">Clusterbildung</span><span class="sxs-lookup"><span data-stu-id="27737-148">Clustering</span></span>

<span data-ttu-id="27737-149">Eine [nicht überwachte Machine Learning](glossary.md#unsupervised-machine-learning)-Aufgabe, die verwendet wird, um Instanzen von Daten in Clustern zu gruppieren, die ähnliche Merkmale aufweisen.</span><span class="sxs-lookup"><span data-stu-id="27737-149">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="27737-150">Die Clusterbildung kann auch zum Identifizieren von Beziehungen in einem Dataset verwendet werden, die Sie möglicherweise nicht logisch durch Durchsuchen oder einfache Beobachtung ableiten können.</span><span class="sxs-lookup"><span data-stu-id="27737-150">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="27737-151">Die Eingaben und Ausgaben eines Clusterbildungsalgorithmus hängen von der ausgewählten Methodik ab.</span><span class="sxs-lookup"><span data-stu-id="27737-151">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="27737-152">Sie können einen verteilungs-, schwerpunkt-, konnektivitäts- oder dichtebasierten Ansatz wählen.</span><span class="sxs-lookup"><span data-stu-id="27737-152">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="27737-153">ML.NET unterstützt derzeit einen schwerpunktbasierten Ansatz bei Verwendung der K-Means-Clusterbildung.</span><span class="sxs-lookup"><span data-stu-id="27737-153">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="27737-154">Beispiele für Clusterbildungsszenarien sind:</span><span class="sxs-lookup"><span data-stu-id="27737-154">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="27737-155">Grundlegendes zu Segmenten von Hotelgästen basierend auf Gewohnheiten und Merkmalen der Hotelauswahl.</span><span class="sxs-lookup"><span data-stu-id="27737-155">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="27737-156">Identifizieren von Kundensegmenten und demografischen Daten, um gezielte Werbekampagnen erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="27737-156">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="27737-157">Kategorisieren des Lagerbestands basierend auf Produktionsmetriken.</span><span class="sxs-lookup"><span data-stu-id="27737-157">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-training-algorithms"></a><span data-ttu-id="27737-158">Trainingsalgorithmen für Clusterbildung</span><span class="sxs-lookup"><span data-stu-id="27737-158">Clustering training algorithms</span></span>

<span data-ttu-id="27737-159">Sie können ein Modell zur Clusterbildung mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="27737-159">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

## <a name="anomaly-detection"></a><span data-ttu-id="27737-160">Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="27737-160">Anomaly detection</span></span>

<span data-ttu-id="27737-161">Diese Aufgabe erstellt ein Anomalieerkennungsmodell mithilfe der Principal Component Analysis (PCA).</span><span class="sxs-lookup"><span data-stu-id="27737-161">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="27737-162">Die Anomalieerkennung auf PCA-Basis unterstützt Sie beim Erstellen eines Modells in Szenarien, in denen mühelos Trainingsdaten aus einer Klasse, z.B. gültige Transaktionen, aber nur schwer ausreichende Beispiele für die gesuchten Anomalien zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="27737-162">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="27737-163">Als bewährtes Verfahren im Machine Learning wird PCA häufig in der explorativen Datenanalyse verwendet, da es die innere Struktur der Daten zeigt und die Abweichung in den Daten erläutert.</span><span class="sxs-lookup"><span data-stu-id="27737-163">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="27737-164">PCA arbeitet mit der Analyse von Daten, die mehrere Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="27737-164">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="27737-165">Das Verfahren sucht nach Korrelationen zwischen den Variablen und bestimmt die Kombination der Werte, die am besten Unterschiede in den Ergebnissen erfassen.</span><span class="sxs-lookup"><span data-stu-id="27737-165">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="27737-166">Mit diesen kombinierten Featurewerten wird ein kompakterer Featurebereich erstellt, der als „Hauptkomponenten“ bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="27737-166">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="27737-167">Die Anomalieerkennung umfasst viele wichtige Machine Learning-Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="27737-167">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="27737-168">Identifizieren potenziell betrügerischer Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="27737-168">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="27737-169">Erlernen von Mustern, die anzeigen, dass der Versuch unternommen wurde, in das Netzwerk einzudringen.</span><span class="sxs-lookup"><span data-stu-id="27737-169">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="27737-170">Finden anomaler Patientencluster.</span><span class="sxs-lookup"><span data-stu-id="27737-170">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="27737-171">Überprüfen von Werten, die in ein System eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="27737-171">Checking values entered into a system.</span></span>

<span data-ttu-id="27737-172">Da Anomalien laut Definition selten sind, kann es schwierig sein, eine repräsentative Stichprobe von Daten zu sammeln, die für die Modellierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="27737-172">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="27737-173">Die Algorithmen, die zu dieser Kategorie gehören, wurden insbesondere daraufhin konzipiert, den wesentlichen Herausforderungen beim Erstellen und Trainieren von Modellen mithilfe von unausgeglichenen Datasets gerecht zu werden.</span><span class="sxs-lookup"><span data-stu-id="27737-173">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-training-algorithms"></a><span data-ttu-id="27737-174">Trainingsalgorithmen zur Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="27737-174">Anomaly detection training algorithms</span></span>

<span data-ttu-id="27737-175">Sie können ein Anomalieerkennungsmodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="27737-175">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

## <a name="ranking"></a><span data-ttu-id="27737-176">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="27737-176">Ranking</span></span>

<span data-ttu-id="27737-177">Eine Rangfolgenaufgabe erstellt für einen Satz bezeichneter Beispiele eine Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="27737-177">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="27737-178">Dieser Beispielsatz besteht aus Instanzengruppen, die nach bestimmten Kriterien bewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="27737-178">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="27737-179">Die Rangfolgenbezeichnungen sind {0, 1, 2, 3, 4} für jede Instanz.</span><span class="sxs-lookup"><span data-stu-id="27737-179">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="27737-180">Die Rangfolgenfunktion wird dafür trainiert, neue Instanzengruppen mit unbekannten Bewertungen für jede Instanz in die Rangfolge einzuordnen.</span><span class="sxs-lookup"><span data-stu-id="27737-180">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="27737-181">ML.NET-Rangfolgen-Lernmodule basieren auf [Machine Learning-Rangfolge](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="27737-181">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="27737-182">Trainingsalgorithmen für Rangfolge</span><span class="sxs-lookup"><span data-stu-id="27737-182">Ranking training algorithms</span></span>

<span data-ttu-id="27737-183">Sie können ein Rangfolgemodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="27737-183">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>

## <a name="recommendation"></a><span data-ttu-id="27737-184">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="27737-184">Recommendation</span></span>

<span data-ttu-id="27737-185">Mit einer Empfehlungsaufgabe kann eine Liste empfohlener Produkte oder Dienste erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="27737-185">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="27737-186">ML.NET verwendet für Empfehlungen [Matrixfaktorisierung (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), einen Algorithmus für [kollaboratives Filtern](https://en.wikipedia.org/wiki/Collaborative_filtering), wenn Ihr Katalog Verlaufsproduktbewertungs-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="27737-186">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="27737-187">Ihnen liegen z.B. Verlaufsfilmbewertungs-Daten Ihrer Benutzer vor, und Sie möchten andere Filme empfehlen, die sie wahrscheinlich als Nächstes sehen möchten.</span><span class="sxs-lookup"><span data-stu-id="27737-187">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="27737-188">Trainingsalgorithmen für Empfehlung</span><span class="sxs-lookup"><span data-stu-id="27737-188">Recommendation training algorithms</span></span>

<span data-ttu-id="27737-189">Sie können ein Empfehlungsmodell mithilfe der folgenden Algorithmen trainieren:</span><span class="sxs-lookup"><span data-stu-id="27737-189">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
