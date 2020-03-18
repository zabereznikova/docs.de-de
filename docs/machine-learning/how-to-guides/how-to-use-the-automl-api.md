---
title: 'Gewusst wie: Verwenden der automatisierten ML-API von ML.NET'
description: Die automatisierte ML-API von ML.NET automatisiert das Erstellen von Modellen und generiert ein zur Bereitstellung geeignetes Modell. Erfahren Sie, welche Optionen Sie verwenden können, um automatisierte Machine Learning-Aufgaben zu konfigurieren.
ms.date: 12/18/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b322c484282d025033d747d2093f7b5b4d216fde
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75636561"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="9cf0b-104">Gewusst wie: Verwenden der automatisierten ML-API von ML.NET</span><span class="sxs-lookup"><span data-stu-id="9cf0b-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="9cf0b-105">Automatisiertes Machine Learning (AutoML) automatisiert den Prozess der Anwendung von Machine Learning auf Daten.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="9cf0b-106">Mit einem Dataset können Sie ein AutoML-**Experiment** ausführen, um unterschiedliche Datenfeaturebereitstellungen, Machine Learning-Algorithmen und Hyperparameter zu durchlaufen, um das beste Modell auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="9cf0b-107">In diesem Thema wird die automatisierte Machine Learning-API für ML.NET behandelt, die sich derzeit in der Vorschauphase befindet.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="9cf0b-108">Änderungen am Material vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="9cf0b-109">Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="9cf0b-109">Load data</span></span>

<span data-ttu-id="9cf0b-110">Automatisiertes Machine Learning unterstützt das Laden eines Datasets in eine [IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="9cf0b-110">Automated machine learning supports loading a dataset into an [IDataView](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="9cf0b-111">Daten können in Form durch Tabstopp getrennter Dateien (TSV) und durch Trennzeichen getrennter Dateien (CSV) vorliegen.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="9cf0b-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9cf0b-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="9cf0b-113">Auswählen des Machine Learning-Aufgabentyps</span><span class="sxs-lookup"><span data-stu-id="9cf0b-113">Select the machine learning task type</span></span>

<span data-ttu-id="9cf0b-114">Bevor Sie ein Experiment erstellen, ermitteln Sie die Art des Machine Learning-Problems, das Sie lösen möchten.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="9cf0b-115">Automatisiertes Machine Learning unterstützt die folgenden ML-Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="9cf0b-115">Automated machine learning supports the following ML tasks:</span></span>

* <span data-ttu-id="9cf0b-116">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-116">Binary Classification</span></span>
* <span data-ttu-id="9cf0b-117">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-117">Multiclass Classification</span></span>
* <span data-ttu-id="9cf0b-118">Regression</span><span class="sxs-lookup"><span data-stu-id="9cf0b-118">Regression</span></span>
* <span data-ttu-id="9cf0b-119">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-119">Recommendation</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="9cf0b-120">Erstellen von Experimenteinstellungen</span><span class="sxs-lookup"><span data-stu-id="9cf0b-120">Create experiment settings</span></span>

<span data-ttu-id="9cf0b-121">Erstellen Sie Experimenteinstellungen für den bestimmten ML-Aufgabentyp:</span><span class="sxs-lookup"><span data-stu-id="9cf0b-121">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="9cf0b-122">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-122">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="9cf0b-123">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-123">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="9cf0b-124">Regression</span><span class="sxs-lookup"><span data-stu-id="9cf0b-124">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

* <span data-ttu-id="9cf0b-125">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-125">Recommendation</span></span>

  ```csharp
  var experimentSettings = new RecommendationExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="9cf0b-126">Konfigurieren von Experimenteinstellungen</span><span class="sxs-lookup"><span data-stu-id="9cf0b-126">Configure experiment settings</span></span>

<span data-ttu-id="9cf0b-127">Experimente sind hochgradig konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-127">Experiments are highly configurable.</span></span> <span data-ttu-id="9cf0b-128">In der [AutoML-API-Dokumentation](https://docs.microsoft.com/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview) finden Sie eine vollständige Liste der Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-128">See the [AutoML API docs](https://docs.microsoft.com/dotnet/api/microsoft.ml.automl?view=ml-dotnet-preview) for a full list of configuration settings.</span></span>

<span data-ttu-id="9cf0b-129">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="9cf0b-129">Some examples include:</span></span>

1. <span data-ttu-id="9cf0b-130">Geben Sie die maximale Ausführungsdauer für das Experiment an.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-130">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="9cf0b-131">Verwenden Sie ein Abbruchtoken, um das Experiment vor dem geplanten Endzeitpunkt abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-131">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="9cf0b-132">Geben Sie eine andere Optimierungsmetrik an.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-132">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="9cf0b-133">Die `CacheDirectory`-Einstellung ist ein Zeiger auf ein Verzeichnis, in dem alle während der AutoML-Aufgabe trainierten Modelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-133">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="9cf0b-134">Wenn `CacheDirectory` auf NULL festgelegt ist, werden Modelle im Arbeitsspeicher gehalten und nicht auf den Datenträger geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-134">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="9cf0b-135">Weisen Sie das automatisierte ML an, bestimmte Trainer nicht zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-135">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="9cf0b-136">Je Aufgabe wird eine Standardliste mit Trainern zum Optimieren untersucht.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-136">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="9cf0b-137">Diese Liste kann für jedes Experiment geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-137">This list can be modified for each experiment.</span></span> <span data-ttu-id="9cf0b-138">Trainer, die bei Ihrem Dataset langsam ausgeführt werden, können beispielsweise aus der Liste entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-138">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="9cf0b-139">Rufen Sie zum Optimieren mit einem bestimmten Trainer `experimentSettings.Trainers.Clear()` auf, und fügen Sie dann den Trainer hinzu, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-139">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="9cf0b-140">Die Liste der pro ML-Aufgabe unterstützten Trainer finden Sie unter dem entsprechenden nachstehenden Link:</span><span class="sxs-lookup"><span data-stu-id="9cf0b-140">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>

* [<span data-ttu-id="9cf0b-141">Unterstützte Algorithmen für binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-141">Supported Binary Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [<span data-ttu-id="9cf0b-142">Unterstützte Algorithmen für Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-142">Supported Multiclass Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [<span data-ttu-id="9cf0b-143">Unterstützte Regressionsalgorithmen</span><span class="sxs-lookup"><span data-stu-id="9cf0b-143">Supported Regression Algorithms</span></span>](xref:Microsoft.ML.AutoML.RegressionTrainer)
* [<span data-ttu-id="9cf0b-144">Unterstützte Empfehlungsalgorithmen</span><span class="sxs-lookup"><span data-stu-id="9cf0b-144">Supported Recommendation Algorithms</span></span>](xref:Microsoft.ML.AutoML.RecommendationTrainer)

## <a name="optimizing-metric"></a><span data-ttu-id="9cf0b-145">Metrikoptimierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-145">Optimizing metric</span></span>

<span data-ttu-id="9cf0b-146">Die Metrikoptimierung, wie im obigen Beispiel dargestellt, bestimmt, welche Metrik während des Modelltrainings optimiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-146">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="9cf0b-147">Welche Metrikoptimierung Sie auswählen können, richtet sich nach der Art der ausgewählten Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-147">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="9cf0b-148">Es folgt eine Liste der verfügbaren Metriken.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-148">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="9cf0b-149">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-149">Binary Classification</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [<span data-ttu-id="9cf0b-150">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-150">Multiclass Classification</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[<span data-ttu-id="9cf0b-151">Regression und Empfehlung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-151">Regression & Recommendation</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|<span data-ttu-id="9cf0b-152">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="9cf0b-152">Accuracy</span></span>| <span data-ttu-id="9cf0b-153">LogLoss</span><span class="sxs-lookup"><span data-stu-id="9cf0b-153">LogLoss</span></span> | <span data-ttu-id="9cf0b-154">RSquared</span><span class="sxs-lookup"><span data-stu-id="9cf0b-154">RSquared</span></span>
|<span data-ttu-id="9cf0b-155">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="9cf0b-155">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="9cf0b-156">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="9cf0b-156">LogLossReduction</span></span> | <span data-ttu-id="9cf0b-157">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="9cf0b-157">MeanAbsoluteError</span></span>
|<span data-ttu-id="9cf0b-158">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="9cf0b-158">AreaUnderRocCurve</span></span> | <span data-ttu-id="9cf0b-159">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="9cf0b-159">MacroAccuracy</span></span> | <span data-ttu-id="9cf0b-160">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="9cf0b-160">MeanSquaredError</span></span>
|<span data-ttu-id="9cf0b-161">F1Score</span><span class="sxs-lookup"><span data-stu-id="9cf0b-161">F1Score</span></span> | <span data-ttu-id="9cf0b-162">MicroAccuracy</span><span class="sxs-lookup"><span data-stu-id="9cf0b-162">MicroAccuracy</span></span> | <span data-ttu-id="9cf0b-163">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="9cf0b-163">RootMeanSquaredError</span></span>
|<span data-ttu-id="9cf0b-164">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="9cf0b-164">NegativePrecision</span></span> | <span data-ttu-id="9cf0b-165">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="9cf0b-165">TopKAccuracy</span></span>
|<span data-ttu-id="9cf0b-166">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="9cf0b-166">NegativeRecall</span></span> |
|<span data-ttu-id="9cf0b-167">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="9cf0b-167">PositivePrecision</span></span>
|<span data-ttu-id="9cf0b-168">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="9cf0b-168">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="9cf0b-169">Datenvorverarbeitung und Featurebereitstellung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-169">Data pre-processing and featurization</span></span>

> [!NOTE]
> <span data-ttu-id="9cf0b-170">Die Featurespalte unterstützt nur die Typen <xref:System.Boolean>, <xref:System.Single> und <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-170">The feature column only supported types of <xref:System.Boolean>, <xref:System.Single>, and <xref:System.String>.</span></span>

<span data-ttu-id="9cf0b-171">Die Datenvorverarbeitung erfolgt standardmäßig, und die folgenden Schritte werden automatisch für Sie ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="9cf0b-171">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="9cf0b-172">Löschen von Features ohne nützliche Informationen</span><span class="sxs-lookup"><span data-stu-id="9cf0b-172">Drop features with no useful information</span></span>

    <span data-ttu-id="9cf0b-173">Löschen Sie Features ohne nützliche Informationen aus den Trainings- und Validierungsdatasets.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-173">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="9cf0b-174">Dazu gehören Features, denen alle Werte fehlen, die denselben Wert in allen Zeilen oder eine sehr hohe Kardinalität aufweisen (z.B. Hashes, IDs oder GUIDs).</span><span class="sxs-lookup"><span data-stu-id="9cf0b-174">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="9cf0b-175">Fehlende Wertangabe und -imputation</span><span class="sxs-lookup"><span data-stu-id="9cf0b-175">Missing value indication and imputation</span></span>

    <span data-ttu-id="9cf0b-176">Füllen Sie fehlende Wertzellen mit dem Standardwert für den Datentyp auf.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-176">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="9cf0b-177">Fügen Sie Indikatorfeatures mit der gleichen Anzahl von Slots wie die Eingabespalte an.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-177">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="9cf0b-178">Der Wert in den angefügten Indikatorfeatures ist `1`, falls der Wert in der Eingabespalte fehlt, und andernfalls `0`.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-178">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="9cf0b-179">Generieren zusätzlicher Features</span><span class="sxs-lookup"><span data-stu-id="9cf0b-179">Generate additional features</span></span>

    <span data-ttu-id="9cf0b-180">Für Textfeatures: Bag-of-Word-Features mit Monogrammen und Trigrammen.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-180">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>

    <span data-ttu-id="9cf0b-181">Für kategorische Features: One-Hot-Codierung für Features mit niedriger Kardinalität Funktionen und One-Hot-Hash-Codierung für kategorische Features mit hoher Kardinalität.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-181">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="9cf0b-182">Transformationen und Codierungen</span><span class="sxs-lookup"><span data-stu-id="9cf0b-182">Transformations and encodings</span></span>

    <span data-ttu-id="9cf0b-183">Textfeatures mit sehr wenigen eindeutigen Werten, transformiert in kategorische Features.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-183">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="9cf0b-184">Führen Sie abhängig von der Kardinalität von kategorischen Features eine One-Hot-Codierung oder One-Hot-Hashcodierung durch.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-184">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="9cf0b-185">Beendigungskriterien</span><span class="sxs-lookup"><span data-stu-id="9cf0b-185">Exit criteria</span></span>

<span data-ttu-id="9cf0b-186">Definieren Sie die Kriterien, um Ihre Aufgabe abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="9cf0b-186">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="9cf0b-187">Beenden nach einer bestimmten Zeitspanne – mit `MaxExperimentTimeInSeconds` in den Einstellungen Ihres Experiments können Sie in Sekunden definieren, wie lange eine Aufgabe noch ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-187">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="9cf0b-188">Beenden bei Abbruchtoken – Sie können ein Abbruchtoken verwenden, mit dem Sie die Aufgabe vor dem geplanten Ende abbrechen können.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-188">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="9cf0b-189">Erstellen eines Experiments</span><span class="sxs-lookup"><span data-stu-id="9cf0b-189">Create an experiment</span></span>

<span data-ttu-id="9cf0b-190">Nachdem Sie die Experimenteinstellungen konfiguriert haben, können Sie das Experiment erstellen.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-190">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="9cf0b-191">Ausführen des Experiments</span><span class="sxs-lookup"><span data-stu-id="9cf0b-191">Run the experiment</span></span>

<span data-ttu-id="9cf0b-192">Das Ausführen des Experiments löst Datenvorverarbeitung, Auswahl des Lernalgorithmus und Optimieren von Hyperparametern aus.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-192">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="9cf0b-193">AutoML generiert weiterhin Kombinationen von Featurebereitstellung, Lernalgorithmen und Hyperparametern, bis `MaxExperimentTimeInSeconds` erreicht ist oder das Experiment beendet wird.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-193">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="9cf0b-194">Untersuchen Sie andere Überladungen für `Execute()`, wenn Validierungsdaten, Spalteninformationen zur Angabe des Spaltenzwecks oder Prefeaturizers übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-194">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="9cf0b-195">Trainingsmodi</span><span class="sxs-lookup"><span data-stu-id="9cf0b-195">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="9cf0b-196">Trainingsdataset</span><span class="sxs-lookup"><span data-stu-id="9cf0b-196">Training dataset</span></span>

<span data-ttu-id="9cf0b-197">AutoML bietet eine Methode zur Ausführung eines überladenen Experiments, mit der Sie Trainingsdaten bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-197">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="9cf0b-198">Die automatisierte ML unterteilt die Daten intern in „Trainieren-Überprüfen“-Unterteilungen.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-198">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="9cf0b-199">Benutzerdefiniertes Validierungsdataset</span><span class="sxs-lookup"><span data-stu-id="9cf0b-199">Custom validation dataset</span></span>

<span data-ttu-id="9cf0b-200">Verwenden Sie benutzerdefinierte Validierungsdatasets, wenn die Zufallsaufteilung nicht akzeptabel ist, was in der Regel auf Zeitreihendaten zutrifft.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-200">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="9cf0b-201">Sie können Ihr eigenes Validierungsdataset angeben.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-201">You can specify your own validation dataset.</span></span> <span data-ttu-id="9cf0b-202">Das Modell wird anhand des angegebenen Validierungsdatasets anstatt eines oder mehrerer zufälliger Datasets ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-202">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a><span data-ttu-id="9cf0b-203">Untersuchen von Modellmetriken</span><span class="sxs-lookup"><span data-stu-id="9cf0b-203">Explore model metrics</span></span>

<span data-ttu-id="9cf0b-204">Nach jeder Iteration eines ML-Experiments werden die mit dieser Aufgabe im Zusammenhang stehenden Metriken gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9cf0b-204">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="9cf0b-205">Beispielsweise können wir auf Validierungsmetriken aus der besten Ausführung zugreifen:</span><span class="sxs-lookup"><span data-stu-id="9cf0b-205">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="9cf0b-206">Im Folgenden finden Sie alle verfügbaren Metriken pro ML-Aufgabe:</span><span class="sxs-lookup"><span data-stu-id="9cf0b-206">The following are all the available metrics per ML task:</span></span>

* [<span data-ttu-id="9cf0b-207">Metriken zur binären Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-207">Binary classification metrics</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [<span data-ttu-id="9cf0b-208">Metriken zur Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="9cf0b-208">Multiclass classification metrics</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [<span data-ttu-id="9cf0b-209">Regression und Empfehlungsmetriken</span><span class="sxs-lookup"><span data-stu-id="9cf0b-209">Regression & recommendation metrics</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a><span data-ttu-id="9cf0b-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cf0b-210">See also</span></span>

<span data-ttu-id="9cf0b-211">Vollständige Codebeispiele und mehr finden Sie im GitHub-Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).</span><span class="sxs-lookup"><span data-stu-id="9cf0b-211">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>
