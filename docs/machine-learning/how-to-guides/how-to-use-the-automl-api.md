---
title: 'Gewusst wie: Verwenden der automatisierten ML-API von ML.NET'
description: Die automatisierte ML-API von ML.NET automatisiert das Erstellen von Modellen und generiert ein zur Bereitstellung geeignetes Modell. Erfahren Sie, welche Optionen Sie verwenden können, um automatisierte Machine Learning-Aufgaben zu konfigurieren.
ms.date: 04/24/2019
ms.custom: mvc,how-to
ms.openlocfilehash: a7057337fb6ff19a1e402d7bf74a766b246ea3c1
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332723"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="4e590-104">Gewusst wie: Verwenden der automatisierten ML-API von ML.NET</span><span class="sxs-lookup"><span data-stu-id="4e590-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="4e590-105">Automatisiertes Machine Learning (AutoML) automatisiert den Prozess der Anwendung von Machine Learning auf Daten.</span><span class="sxs-lookup"><span data-stu-id="4e590-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="4e590-106">Mit einem Dataset können Sie ein AutoML-**Experiment** ausführen, um unterschiedliche Datenfeaturebereitstellungen, Machine Learning-Algorithmen und Hyperparameter zu durchlaufen, um das beste Modell auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4e590-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="4e590-107">In diesem Thema wird die automatisierte Machine Learning-API für ML.NET behandelt, die sich derzeit in der Vorschauphase befindet.</span><span class="sxs-lookup"><span data-stu-id="4e590-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="4e590-108">Änderungen am Material vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="4e590-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="4e590-109">Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="4e590-109">Load data</span></span>

<span data-ttu-id="4e590-110">Automatisiertes Machine Learning unterstützt das Laden eines Datasets in eine [IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="4e590-110">Automated machine learning supports loading a dataset into an [IDataView](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="4e590-111">Daten können in Form durch Tabstopp getrennter Dateien (TSV) und durch Trennzeichen getrennter Dateien (CSV) vorliegen.</span><span class="sxs-lookup"><span data-stu-id="4e590-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="4e590-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4e590-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="4e590-113">Auswählen des Machine Learning-Aufgabentyps</span><span class="sxs-lookup"><span data-stu-id="4e590-113">Select the machine learning task type</span></span>
<span data-ttu-id="4e590-114">Bevor Sie ein Experiment erstellen, ermitteln Sie die Art des Machine Learning-Problems, das Sie lösen möchten.</span><span class="sxs-lookup"><span data-stu-id="4e590-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="4e590-115">Automatisiertes Machine Learning unterstützt die folgenden ML-Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="4e590-115">Automated machine learning supports the following ML tasks:</span></span>

* <span data-ttu-id="4e590-116">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-116">Binary Classification</span></span>
* <span data-ttu-id="4e590-117">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-117">Multiclass Classification</span></span>
* <span data-ttu-id="4e590-118">Regression</span><span class="sxs-lookup"><span data-stu-id="4e590-118">Regression</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="4e590-119">Erstellen von Experimenteinstellungen</span><span class="sxs-lookup"><span data-stu-id="4e590-119">Create experiment settings</span></span>

<span data-ttu-id="4e590-120">Erstellen Sie Experimenteinstellungen für den bestimmten ML-Aufgabentyp:</span><span class="sxs-lookup"><span data-stu-id="4e590-120">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="4e590-121">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-121">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="4e590-122">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-122">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="4e590-123">Regression</span><span class="sxs-lookup"><span data-stu-id="4e590-123">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="4e590-124">Konfigurieren von Experimenteinstellungen</span><span class="sxs-lookup"><span data-stu-id="4e590-124">Configure experiment settings</span></span>

<span data-ttu-id="4e590-125">Experimente sind hochgradig konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="4e590-125">Experiments are highly configurable.</span></span> <span data-ttu-id="4e590-126">In der [AutoML-API-Dokumentation](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet) finden Sie eine vollständige Liste der Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4e590-126">See the [AutoML API docs](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet) for a full list of configuration settings.</span></span>

<span data-ttu-id="4e590-127">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="4e590-127">Some examples include:</span></span>

1. <span data-ttu-id="4e590-128">Geben Sie die maximale Ausführungsdauer für das Experiment an.</span><span class="sxs-lookup"><span data-stu-id="4e590-128">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="4e590-129">Verwenden Sie ein Abbruchtoken, um das Experiment vor dem geplanten Endzeitpunkt abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="4e590-129">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="4e590-130">Geben Sie eine andere Optimierungsmetrik an.</span><span class="sxs-lookup"><span data-stu-id="4e590-130">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="4e590-131">Die `CacheDirectory`-Einstellung ist ein Zeiger auf ein Verzeichnis, in dem alle während der AutoML-Aufgabe trainierten Modelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4e590-131">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="4e590-132">Wenn `CacheDirectory` auf NULL festgelegt ist, werden Modelle im Arbeitsspeicher gehalten und nicht auf den Datenträger geschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e590-132">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>
 
    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="4e590-133">Weisen Sie das automatisierte ML an, bestimmte Trainer nicht zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e590-133">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="4e590-134">Je Aufgabe wird eine Standardliste mit Trainern zum Optimieren untersucht.</span><span class="sxs-lookup"><span data-stu-id="4e590-134">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="4e590-135">Diese Liste kann für jedes Experiment geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4e590-135">This list can be modified for each experiment.</span></span> <span data-ttu-id="4e590-136">Trainer, die bei Ihrem Dataset langsam ausgeführt werden, können beispielsweise aus der Liste entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="4e590-136">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="4e590-137">Rufen Sie zum Optimieren mit einem bestimmten Trainer `experimentSettings.Trainers.Clear()` auf, und fügen Sie dann den Trainer hinzu, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4e590-137">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="4e590-138">Die Liste der pro ML-Aufgabe unterstützten Trainer finden Sie unter dem entsprechenden nachstehenden Link:</span><span class="sxs-lookup"><span data-stu-id="4e590-138">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>

* [<span data-ttu-id="4e590-139">Unterstützte Algorithmen für binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-139">Supported Binary Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [<span data-ttu-id="4e590-140">Unterstützte Algorithmen für Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-140">Supported Multiclass Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [<span data-ttu-id="4e590-141">Unterstützte Regressionsalgorithmen</span><span class="sxs-lookup"><span data-stu-id="4e590-141">Supported Regression Algorithms</span></span>](xref:Microsoft.ML.AutoML.RegressionTrainer)

## <a name="optimizing-metric"></a><span data-ttu-id="4e590-142">Metrikoptimierung</span><span class="sxs-lookup"><span data-stu-id="4e590-142">Optimizing metric</span></span>

<span data-ttu-id="4e590-143">Die Metrikoptimierung, wie im obigen Beispiel dargestellt, bestimmt, welche Metrik während des Modelltrainings optimiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e590-143">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="4e590-144">Welche Metrikoptimierung Sie auswählen können, richtet sich nach der Art der ausgewählten Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="4e590-144">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="4e590-145">Es folgt eine Liste der verfügbaren Metriken.</span><span class="sxs-lookup"><span data-stu-id="4e590-145">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="4e590-146">Binäre Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-146">Binary Classification</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [<span data-ttu-id="4e590-147">Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-147">Multiclass Classification</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[<span data-ttu-id="4e590-148">Regression</span><span class="sxs-lookup"><span data-stu-id="4e590-148">Regression</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|<span data-ttu-id="4e590-149">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="4e590-149">Accuracy</span></span>| <span data-ttu-id="4e590-150">LogLoss</span><span class="sxs-lookup"><span data-stu-id="4e590-150">LogLoss</span></span> | <span data-ttu-id="4e590-151">RSquared</span><span class="sxs-lookup"><span data-stu-id="4e590-151">RSquared</span></span>
|<span data-ttu-id="4e590-152">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="4e590-152">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="4e590-153">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="4e590-153">LogLossReduction</span></span> | <span data-ttu-id="4e590-154">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="4e590-154">MeanAbsoluteError</span></span>
|<span data-ttu-id="4e590-155">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="4e590-155">AreaUnderRocCurve</span></span> | <span data-ttu-id="4e590-156">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="4e590-156">MacroAccuracy</span></span> | <span data-ttu-id="4e590-157">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="4e590-157">MeanSquaredError</span></span>
|<span data-ttu-id="4e590-158">F1Score</span><span class="sxs-lookup"><span data-stu-id="4e590-158">F1Score</span></span> | <span data-ttu-id="4e590-159">MicroAccuracy</span><span class="sxs-lookup"><span data-stu-id="4e590-159">MicroAccuracy</span></span> | <span data-ttu-id="4e590-160">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="4e590-160">RootMeanSquaredError</span></span>
|<span data-ttu-id="4e590-161">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="4e590-161">NegativePrecision</span></span> | <span data-ttu-id="4e590-162">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="4e590-162">TopKAccuracy</span></span>
|<span data-ttu-id="4e590-163">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="4e590-163">NegativeRecall</span></span> |
|<span data-ttu-id="4e590-164">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="4e590-164">PositivePrecision</span></span>
|<span data-ttu-id="4e590-165">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="4e590-165">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="4e590-166">Datenvorverarbeitung und Featurebereitstellung</span><span class="sxs-lookup"><span data-stu-id="4e590-166">Data pre-processing and featurization</span></span>

> [!NOTE]
> <span data-ttu-id="4e590-167">Die Featurespalte unterstützt nur die Typen [`Boolean`](https://docs.microsoft.com/en-us/dotnet/api/system.boolean), [`Single`](https://docs.microsoft.com/en-us/dotnet/api/system.single) und [`String`](https://docs.microsoft.com/en-us/dotnet/api/system.string).</span><span class="sxs-lookup"><span data-stu-id="4e590-167">The feature column only supported types of [`Boolean`](https://docs.microsoft.com/en-us/dotnet/api/system.boolean), [`Single`](https://docs.microsoft.com/en-us/dotnet/api/system.single), and [`String`](https://docs.microsoft.com/en-us/dotnet/api/system.string).</span></span>

<span data-ttu-id="4e590-168">Die Datenvorverarbeitung erfolgt standardmäßig, und die folgenden Schritte werden automatisch für Sie ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="4e590-168">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="4e590-169">Löschen von Features ohne nützliche Informationen</span><span class="sxs-lookup"><span data-stu-id="4e590-169">Drop features with no useful information</span></span>

    <span data-ttu-id="4e590-170">Löschen Sie Features ohne nützliche Informationen aus den Trainings- und Validierungsdatasets.</span><span class="sxs-lookup"><span data-stu-id="4e590-170">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="4e590-171">Dazu gehören Features, denen alle Werte fehlen, die denselben Wert in allen Zeilen oder eine sehr hohe Kardinalität aufweisen (z.B. Hashes, IDs oder GUIDs).</span><span class="sxs-lookup"><span data-stu-id="4e590-171">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="4e590-172">Fehlende Wertangabe und -imputation</span><span class="sxs-lookup"><span data-stu-id="4e590-172">Missing value indication and imputation</span></span>

    <span data-ttu-id="4e590-173">Füllen Sie fehlende Wertzellen mit dem Standardwert für den Datentyp auf.</span><span class="sxs-lookup"><span data-stu-id="4e590-173">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="4e590-174">Fügen Sie Indikatorfeatures mit der gleichen Anzahl von Slots wie die Eingabespalte an.</span><span class="sxs-lookup"><span data-stu-id="4e590-174">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="4e590-175">Der Wert in den angefügten Indikatorfeatures ist `1`, falls der Wert in der Eingabespalte fehlt, und andernfalls `0`.</span><span class="sxs-lookup"><span data-stu-id="4e590-175">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="4e590-176">Generieren zusätzlicher Features</span><span class="sxs-lookup"><span data-stu-id="4e590-176">Generate additional features</span></span>
    
    <span data-ttu-id="4e590-177">Für Textfeatures: Bag-of-Word-Features mit Monogrammen und Trigrammen.</span><span class="sxs-lookup"><span data-stu-id="4e590-177">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>
    
    <span data-ttu-id="4e590-178">Für kategorische Features: One-Hot-Codierung für Features mit niedriger Kardinalität Funktionen und One-Hot-Hash-Codierung für kategorische Features mit hoher Kardinalität.</span><span class="sxs-lookup"><span data-stu-id="4e590-178">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="4e590-179">Transformationen und Codierungen</span><span class="sxs-lookup"><span data-stu-id="4e590-179">Transformations and encodings</span></span>

    <span data-ttu-id="4e590-180">Textfeatures mit sehr wenigen eindeutigen Werten, transformiert in kategorische Features.</span><span class="sxs-lookup"><span data-stu-id="4e590-180">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="4e590-181">Führen Sie abhängig von der Kardinalität von kategorischen Features eine One-Hot-Codierung oder One-Hot-Hashcodierung durch.</span><span class="sxs-lookup"><span data-stu-id="4e590-181">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="4e590-182">Beendigungskriterien</span><span class="sxs-lookup"><span data-stu-id="4e590-182">Exit criteria</span></span>

<span data-ttu-id="4e590-183">Definieren Sie die Kriterien, um Ihre Aufgabe abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="4e590-183">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="4e590-184">Beenden nach einer bestimmten Zeitspanne – mit `MaxExperimentTimeInSeconds` in den Einstellungen Ihres Experiments können Sie in Sekunden definieren, wie lange eine Aufgabe noch ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e590-184">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="4e590-185">Beenden bei Abbruchtoken – Sie können ein Abbruchtoken verwenden, mit dem Sie die Aufgabe vor dem geplanten Ende abbrechen können.</span><span class="sxs-lookup"><span data-stu-id="4e590-185">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="4e590-186">Erstellen eines Experiments</span><span class="sxs-lookup"><span data-stu-id="4e590-186">Create an experiment</span></span>

<span data-ttu-id="4e590-187">Nachdem Sie die Experimenteinstellungen konfiguriert haben, können Sie das Experiment erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e590-187">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="4e590-188">Ausführen des Experiments</span><span class="sxs-lookup"><span data-stu-id="4e590-188">Run the experiment</span></span>

<span data-ttu-id="4e590-189">Das Ausführen des Experiments löst Datenvorverarbeitung, Auswahl des Lernalgorithmus und Optimieren von Hyperparametern aus.</span><span class="sxs-lookup"><span data-stu-id="4e590-189">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="4e590-190">AutoML generiert weiterhin Kombinationen von Featurebereitstellung, Lernalgorithmen und Hyperparametern, bis `MaxExperimentTimeInSeconds` erreicht ist oder das Experiment beendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e590-190">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="4e590-191">Untersuchen Sie andere Überladungen für `Execute()`, wenn Validierungsdaten, Spalteninformationen zur Angabe des Spaltenzwecks oder Prefeaturizers übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4e590-191">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="4e590-192">Trainingsmodi</span><span class="sxs-lookup"><span data-stu-id="4e590-192">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="4e590-193">Trainingsdataset</span><span class="sxs-lookup"><span data-stu-id="4e590-193">Training dataset</span></span>

<span data-ttu-id="4e590-194">AutoML bietet eine Methode zur Ausführung eines überladenen Experiments, mit der Sie Trainingsdaten bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="4e590-194">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="4e590-195">Die automatisierte ML unterteilt die Daten intern in „Trainieren-Überprüfen“-Unterteilungen.</span><span class="sxs-lookup"><span data-stu-id="4e590-195">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);   
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="4e590-196">Benutzerdefiniertes Validierungsdataset</span><span class="sxs-lookup"><span data-stu-id="4e590-196">Custom validation dataset</span></span>

<span data-ttu-id="4e590-197">Verwenden Sie benutzerdefinierte Validierungsdatasets, wenn die Zufallsaufteilung nicht akzeptabel ist, was in der Regel auf Zeitreihendaten zutrifft.</span><span class="sxs-lookup"><span data-stu-id="4e590-197">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="4e590-198">Sie können Ihr eigenes Validierungsdataset angeben.</span><span class="sxs-lookup"><span data-stu-id="4e590-198">You can specify your own validation dataset.</span></span> <span data-ttu-id="4e590-199">Das Modell wird anhand des angegebenen Validierungsdatasets anstatt eines oder mehrerer zufälliger Datasets ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4e590-199">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);   
```

## <a name="explore-model-metrics"></a><span data-ttu-id="4e590-200">Untersuchen von Modellmetriken</span><span class="sxs-lookup"><span data-stu-id="4e590-200">Explore model metrics</span></span>

<span data-ttu-id="4e590-201">Nach jeder Iteration eines ML-Experiments werden die mit dieser Aufgabe im Zusammenhang stehenden Metriken gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4e590-201">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="4e590-202">Beispielsweise können wir auf Validierungsmetriken aus der besten Ausführung zugreifen:</span><span class="sxs-lookup"><span data-stu-id="4e590-202">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="4e590-203">Im Folgenden finden Sie alle verfügbaren Metriken pro ML-Aufgabe:</span><span class="sxs-lookup"><span data-stu-id="4e590-203">The following are all the available metrics per ML task:</span></span>

* [<span data-ttu-id="4e590-204">Metriken zur binären Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-204">Binary classification metrics</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [<span data-ttu-id="4e590-205">Metriken zur Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="4e590-205">Multiclass classification metrics</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [<span data-ttu-id="4e590-206">Regressionsmetriken</span><span class="sxs-lookup"><span data-stu-id="4e590-206">Regression metrics</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a><span data-ttu-id="4e590-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e590-207">See also</span></span>

<span data-ttu-id="4e590-208">Vollständige Codebeispiele und mehr finden Sie im GitHub-Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).</span><span class="sxs-lookup"><span data-stu-id="4e590-208">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>
