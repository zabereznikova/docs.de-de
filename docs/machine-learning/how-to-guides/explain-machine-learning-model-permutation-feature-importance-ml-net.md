---
title: Erläutern von Modellvorhersagen mit Permutation Feature Importance
description: Verstehen der Wichtigkeit von Modellfeatures mit Permutation Feature Importance (PFI) in ML.NET
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: 8090e4565a7e55aaa9cc9939e61eb728a169de8d
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736872"
---
# <a name="explain-model-predictions-using-permutation-feature-importance"></a><span data-ttu-id="98d4f-103">Erläutern von Modellvorhersagen mit Permutation Feature Importance</span><span class="sxs-lookup"><span data-stu-id="98d4f-103">Explain model predictions using Permutation Feature Importance</span></span>

<span data-ttu-id="98d4f-104">Erfahren Sie, wie Sie ML.NET-Vorhersagen für Machine Learning-Modelle erklären können, indem Sie die Beitragsfeatures für Vorhersagen mit Permutation Feature Importance (PFI) verstehen.</span><span class="sxs-lookup"><span data-stu-id="98d4f-104">Learn how to explain ML.NET machine learning model predictions by understanding the contribution features have to predictions using Permutation Feature Importance (PFI).</span></span>

<span data-ttu-id="98d4f-105">Machine Learning-Modelle werden oft als Blackboxes betrachtet, die aus Eingaben eine Ausgabe generieren.</span><span class="sxs-lookup"><span data-stu-id="98d4f-105">Machine learning models are often thought of as black boxes that take inputs and generate an output.</span></span> <span data-ttu-id="98d4f-106">Die Zwischenschritte oder Interaktionen zwischen den Features, die die Ausgabe beeinflussen, werden nur selten verstanden.</span><span class="sxs-lookup"><span data-stu-id="98d4f-106">The intermediate steps or interactions among the features that influence the output are rarely understood.</span></span> <span data-ttu-id="98d4f-107">Da das maschinelle Lernen in immer mehr Bereichen des täglichen Lebens, wie beispielsweise im Gesundheitswesen, zum Einsatz kommt, ist es von größter Bedeutung zu verstehen, warum ein Machine Learning-Modell die Entscheidungen trifft, die es trifft.</span><span class="sxs-lookup"><span data-stu-id="98d4f-107">As machine learning is introduced into more aspects of everyday life such as healthcare, it's of utmost importance to understand why a machine learning model makes the decisions it does.</span></span> <span data-ttu-id="98d4f-108">Wenn die Diagnosen zum Beispiel durch ein Machine Learning-Modell gestellt werden, brauchen die Mediziner eine Möglichkeit, die Faktoren zu untersuchen, die bei der Erstellung dieser Diagnosen berücksichtigt wurden.</span><span class="sxs-lookup"><span data-stu-id="98d4f-108">For example, if diagnoses are made by a machine learning model, healthcare professionals need a way to look into the factors that went into making that diagnoses.</span></span> <span data-ttu-id="98d4f-109">Die richtige Diagnose könnte einen großen Unterschied machen, ob die Genesung eines Patienten schnell verläuft oder nicht.</span><span class="sxs-lookup"><span data-stu-id="98d4f-109">Providing the right diagnosis could make a great difference on whether a patient has a speedy recovery or not.</span></span> <span data-ttu-id="98d4f-110">Je höher also der Grad der Erklärbarkeit in einem Modell ist, desto größer ist das Vertrauen der Mediziner, die die vom Modell getroffenen Entscheidungen akzeptieren oder ablehnen müssen.</span><span class="sxs-lookup"><span data-stu-id="98d4f-110">Therefore the higher the level of explainability in a model, the greater confidence healthcare professionals have to accept or reject the decisions made by the model.</span></span>

<span data-ttu-id="98d4f-111">Zur Erklärung von Modellen werden verschiedene Techniken verwendet, darunter PFI.</span><span class="sxs-lookup"><span data-stu-id="98d4f-111">Various techniques are used to explain models, one of which is PFI.</span></span> <span data-ttu-id="98d4f-112">PFI ist eine Technik zur Erklärung von Klassifizierungs- und Regressionsmodellen, die von [Leo Breimans Schrift *Random Forests*](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) inspiriert ist (siehe Abschnitt 10).</span><span class="sxs-lookup"><span data-stu-id="98d4f-112">PFI is a technique used to explain classification and regression models that is inspired by [Breiman's *Random Forests* paper](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (see section 10).</span></span> <span data-ttu-id="98d4f-113">Die grobe Funktionsweise besteht darin, dass nach dem Zufallsprinzip die Daten des gesamten Datasets für jeweils ein Feature vermischt werden und dann berechnet wird, wie stark sich die gewünschte Leistungsmetrik verringert.</span><span class="sxs-lookup"><span data-stu-id="98d4f-113">At a high level, the way it works is by randomly shuffling data one feature at a time for the entire dataset and calculating how much the performance metric of interest decreases.</span></span> <span data-ttu-id="98d4f-114">Je größer die Änderung, desto wichtiger ist dieses Feature.</span><span class="sxs-lookup"><span data-stu-id="98d4f-114">The larger the change, the more important that feature is.</span></span> 

<span data-ttu-id="98d4f-115">Darüber hinaus können sich Modellersteller durch die Hervorhebung der wichtigsten Features auf die Verwendung einer Teilmenge sinnvoller Features konzentrieren, die Rauschen und Trainingszeiten reduzieren können.</span><span class="sxs-lookup"><span data-stu-id="98d4f-115">Additionally, by highlighting the most important features, model builders can focus on using a subset of more meaningful features which can potentially reduce noise and training time.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="98d4f-116">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="98d4f-116">Load the data</span></span>

<span data-ttu-id="98d4f-117">Die Features im Dataset, das für dieses Beispiel verwendet wird, befinden sich in den Spalten 1-12.</span><span class="sxs-lookup"><span data-stu-id="98d4f-117">The features in the dataset being used for this sample are in columns 1-12.</span></span> <span data-ttu-id="98d4f-118">Das Ziel ist die Vorhersage von `Price`.</span><span class="sxs-lookup"><span data-stu-id="98d4f-118">The goal is to predict `Price`.</span></span> 

| <span data-ttu-id="98d4f-119">Column</span><span class="sxs-lookup"><span data-stu-id="98d4f-119">Column</span></span> | <span data-ttu-id="98d4f-120">Feature</span><span class="sxs-lookup"><span data-stu-id="98d4f-120">Feature</span></span> | <span data-ttu-id="98d4f-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="98d4f-121">Description</span></span> 
| --- | --- | --- |
| <span data-ttu-id="98d4f-122">1</span><span class="sxs-lookup"><span data-stu-id="98d4f-122">1</span></span> | <span data-ttu-id="98d4f-123">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="98d4f-123">CrimeRate</span></span> | <span data-ttu-id="98d4f-124">Pro-Kopf-Kriminalitätsrate</span><span class="sxs-lookup"><span data-stu-id="98d4f-124">Per capita crime rate</span></span>
| <span data-ttu-id="98d4f-125">2</span><span class="sxs-lookup"><span data-stu-id="98d4f-125">2</span></span> | <span data-ttu-id="98d4f-126">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="98d4f-126">ResidentialZones</span></span> | <span data-ttu-id="98d4f-127">Wohngebiete in der Stadt</span><span class="sxs-lookup"><span data-stu-id="98d4f-127">Residential zones in town</span></span>
| <span data-ttu-id="98d4f-128">3</span><span class="sxs-lookup"><span data-stu-id="98d4f-128">3</span></span> | <span data-ttu-id="98d4f-129">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="98d4f-129">CommercialZones</span></span> | <span data-ttu-id="98d4f-130">Nicht-Wohngebiete in der Stadt</span><span class="sxs-lookup"><span data-stu-id="98d4f-130">Non-residential zones in town</span></span>
| <span data-ttu-id="98d4f-131">4</span><span class="sxs-lookup"><span data-stu-id="98d4f-131">4</span></span> | <span data-ttu-id="98d4f-132">NearWater</span><span class="sxs-lookup"><span data-stu-id="98d4f-132">NearWater</span></span> | <span data-ttu-id="98d4f-133">Nähe zu einem Gewässer</span><span class="sxs-lookup"><span data-stu-id="98d4f-133">Proximity to body of water</span></span>
| <span data-ttu-id="98d4f-134">5</span><span class="sxs-lookup"><span data-stu-id="98d4f-134">5</span></span> | <span data-ttu-id="98d4f-135">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="98d4f-135">ToxicWasteLevels</span></span> | <span data-ttu-id="98d4f-136">Toxizitätswerte (PPM)</span><span class="sxs-lookup"><span data-stu-id="98d4f-136">Toxicity levels (PPM)</span></span>
| <span data-ttu-id="98d4f-137">6</span><span class="sxs-lookup"><span data-stu-id="98d4f-137">6</span></span> | <span data-ttu-id="98d4f-138">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="98d4f-138">AverageRoomNumber</span></span> | <span data-ttu-id="98d4f-139">Durchschnittliche Anzahl von Räumen in einem Haus</span><span class="sxs-lookup"><span data-stu-id="98d4f-139">Average number of rooms in house</span></span>
| <span data-ttu-id="98d4f-140">7</span><span class="sxs-lookup"><span data-stu-id="98d4f-140">7</span></span> | <span data-ttu-id="98d4f-141">HomeAge</span><span class="sxs-lookup"><span data-stu-id="98d4f-141">HomeAge</span></span> | <span data-ttu-id="98d4f-142">Alter des Hauses</span><span class="sxs-lookup"><span data-stu-id="98d4f-142">Age of home</span></span>
| <span data-ttu-id="98d4f-143">8</span><span class="sxs-lookup"><span data-stu-id="98d4f-143">8</span></span> | <span data-ttu-id="98d4f-144">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="98d4f-144">BusinessCenterDistance</span></span> | <span data-ttu-id="98d4f-145">Entfernung zum nächsten Geschäftsviertel</span><span class="sxs-lookup"><span data-stu-id="98d4f-145">Distance to nearest business district</span></span>
| <span data-ttu-id="98d4f-146">9</span><span class="sxs-lookup"><span data-stu-id="98d4f-146">9</span></span> | <span data-ttu-id="98d4f-147">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="98d4f-147">HighwayAccess</span></span> | <span data-ttu-id="98d4f-148">Geografischer Nähe zu Autobahnen</span><span class="sxs-lookup"><span data-stu-id="98d4f-148">Proximity to highways</span></span>
| <span data-ttu-id="98d4f-149">10</span><span class="sxs-lookup"><span data-stu-id="98d4f-149">10</span></span> | <span data-ttu-id="98d4f-150">TaxRate</span><span class="sxs-lookup"><span data-stu-id="98d4f-150">TaxRate</span></span> | <span data-ttu-id="98d4f-151">Grundsteuersatz</span><span class="sxs-lookup"><span data-stu-id="98d4f-151">Property tax rate</span></span>
| <span data-ttu-id="98d4f-152">11</span><span class="sxs-lookup"><span data-stu-id="98d4f-152">11</span></span> | <span data-ttu-id="98d4f-153">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="98d4f-153">StudentTeacherRatio</span></span> | <span data-ttu-id="98d4f-154">Verhältnis zwischen Schülern/Studenten und Lehrkräften</span><span class="sxs-lookup"><span data-stu-id="98d4f-154">Ratio of students to teachers</span></span>
| <span data-ttu-id="98d4f-155">12</span><span class="sxs-lookup"><span data-stu-id="98d4f-155">12</span></span> | <span data-ttu-id="98d4f-156">PercentPopulationBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="98d4f-156">PercentPopulationBelowPoverty</span></span> | <span data-ttu-id="98d4f-157">Prozentsatz der Bevölkerung, der unter der Armutsgrenze lebt</span><span class="sxs-lookup"><span data-stu-id="98d4f-157">Percent of population living below poverty</span></span>
| <span data-ttu-id="98d4f-158">13</span><span class="sxs-lookup"><span data-stu-id="98d4f-158">13</span></span> | <span data-ttu-id="98d4f-159">Preis</span><span class="sxs-lookup"><span data-stu-id="98d4f-159">Price</span></span> | <span data-ttu-id="98d4f-160">Preis des Hauses</span><span class="sxs-lookup"><span data-stu-id="98d4f-160">Price of the home</span></span>

<span data-ttu-id="98d4f-161">Ein Beispiel für das Dataset wird unten dargestellt:</span><span class="sxs-lookup"><span data-stu-id="98d4f-161">A sample of the dataset is shown below:</span></span>

```text
1,24,13,1,0.59,3,96,11,23,608,14,13,32
4,80,18,1,0.37,5,14,7,4,346,19,13,41
2,98,16,1,0.25,10,5,1,8,689,13,36,12
```

<span data-ttu-id="98d4f-162">Die Daten in diesem Beispiel können durch eine Klasse wie `HousingPriceData` modelliert und in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden.</span><span class="sxs-lookup"><span data-stu-id="98d4f-162">The data in this sample can be modeled by a class like `HousingPriceData` and loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
class HousingPriceData
{
    [LoadColumn(0)]
    public float CrimeRate { get; set; }

    [LoadColumn(1)]
    public float ResidentialZones { get; set; }

    [LoadColumn(2)]
    public float CommercialZones { get; set; }

    [LoadColumn(3)]
    public float NearWater { get; set; }

    [LoadColumn(4)]
    public float ToxicWasteLevels { get; set; }

    [LoadColumn(5)]
    public float AverageRoomNumber { get; set; }

    [LoadColumn(6)]
    public float HomeAge { get; set; }

    [LoadColumn(7)]
    public float BusinessCenterDistance { get; set; }

    [LoadColumn(8)]
    public float HighwayAccess { get; set; }

    [LoadColumn(9)]
    public float TaxRate { get; set; }

    [LoadColumn(10)]
    public float StudentTeacherRatio { get; set; }

    [LoadColumn(11)]
    public float PercentPopulationBelowPoverty { get; set; }

    [LoadColumn(12)]
    [ColumnName("Label")]
    public float Price { get; set; }
}
```

## <a name="train-the-model"></a><span data-ttu-id="98d4f-163">Modelltraining</span><span class="sxs-lookup"><span data-stu-id="98d4f-163">Train the model</span></span>

<span data-ttu-id="98d4f-164">Das folgende Codebeispiel veranschaulicht den Prozess des Trainings eines linearen Regressionsmodells zur Vorhersage von Hauspreisen.</span><span class="sxs-lookup"><span data-stu-id="98d4f-164">The code sample below illustrates the process of training a linear regression model to predict house prices.</span></span>

```csharp
// 1. Get the column name of input features.
string[] featureColumnNames = 
    data.Schema
        .Select(column => column.Name)
        .Where(columnName => columnName != "Label").ToArray();

// 2. Define estimator with data pre-processing steps
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", featureColumnNames)
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// 3. Create transformer using the data pre-processing estimator
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// 4. Pre-process the training data
IDataView preprocessedTrainData = dataPrepTransformer.Transform(data);

// 5. Define Stochastic Dual Coordinate Ascent machine learning estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// 6. Train machine learning model
var sdcaModel = sdcaEstimator.Fit(preprocessedTrainData);
```

## <a name="explain-the-model-with-permutation-feature-importance-pfi"></a><span data-ttu-id="98d4f-165">Erläutern des Modells mit Permutation Feature Importance (PFI)</span><span class="sxs-lookup"><span data-stu-id="98d4f-165">Explain the model with Permutation Feature Importance (PFI)</span></span>

<span data-ttu-id="98d4f-166">ML.NET verwendet die [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions)-Methode für die jeweilige Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="98d4f-166">In ML.NET use the [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) method for your respective task.</span></span>

```csharp
ImmutableArray<RegressionMetricsStatistics> permutationFeatureImportance = 
    mlContext
        .Regression
        .PermutationFeatureImportance(sdcaModel, preprocessedTrainData, permutationCount:3);
```

<span data-ttu-id="98d4f-167">Das Ergebnis der Verwendung von [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) auf das Trainingsdataset ist ein [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) von [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics)-Objekten.</span><span class="sxs-lookup"><span data-stu-id="98d4f-167">The result of using [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) on the training dataset is an [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) of [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) objects.</span></span> <span data-ttu-id="98d4f-168">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) liefert zusammenfassende Statistiken wie Mittelwert und Standardabweichung für mehrere Beobachtungen der [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics), die der Anzahl der durch den `permutationCount`-Parameter angegebenen Permutationen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="98d4f-168">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) provides summary statistics like mean and standard deviation for multiple observations of [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics) equal to the number of permutations specified by the `permutationCount` parameter.</span></span>

<span data-ttu-id="98d4f-169">Die Bedeutung, oder in diesem Fall die aus [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) berechnete absolute durchschnittliche Abnahme der Metrik für das Bestimmtheitsmaß, kann dann vom wichtigsten zum unwichtigsten Feature geordnet werden.</span><span class="sxs-lookup"><span data-stu-id="98d4f-169">The importance, or in this case, the absolute average decrease in R-squared metric calculated by [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) can then be ordered from most important to least important.</span></span>  

```csharp
// Order features by importance
var featureImportanceMetrics =
    permutationFeatureImportance
        .Select((metric, index) => new { index, metric.RSquared })
        .OrderByDescending(myFeatures => Math.Abs(myFeatures.RSquared.Mean));

Console.WriteLine("Feature\tPFI");

foreach (var feature in featureImportanceMetrics)
{
    Console.WriteLine($"{featureColumnNames[feature.index],-20}|\t{feature.RSquared.Mean:F6}");
}
```

<span data-ttu-id="98d4f-170">Wenn Sie die Werte für jedes Feature in `featureImportanceMetrics` ausdrucken, würde das in etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="98d4f-170">Printing the values for each of the features in `featureImportanceMetrics` would generate output similar to that below.</span></span> <span data-ttu-id="98d4f-171">Beachten Sie, dass mit unterschiedlichen Ergebnissen zu rechnen ist, da diese Werte je nach den Daten, die sie erhalten, variieren.</span><span class="sxs-lookup"><span data-stu-id="98d4f-171">Keep in mind that you should expect to see different results because these values vary based on the data that they are given.</span></span>  

| <span data-ttu-id="98d4f-172">Feature</span><span class="sxs-lookup"><span data-stu-id="98d4f-172">Feature</span></span> | <span data-ttu-id="98d4f-173">Änderung im Bestimmtheitsmaß</span><span class="sxs-lookup"><span data-stu-id="98d4f-173">Change to R-Squared</span></span> |
|:--|:--:|
<span data-ttu-id="98d4f-174">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="98d4f-174">HighwayAccess</span></span>       |   <span data-ttu-id="98d4f-175">-0,042731</span><span class="sxs-lookup"><span data-stu-id="98d4f-175">-0.042731</span></span>
<span data-ttu-id="98d4f-176">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="98d4f-176">StudentTeacherRatio</span></span> |   <span data-ttu-id="98d4f-177">-0,012730</span><span class="sxs-lookup"><span data-stu-id="98d4f-177">-0.012730</span></span>
<span data-ttu-id="98d4f-178">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="98d4f-178">BusinessCenterDistance</span></span>| <span data-ttu-id="98d4f-179">-0,010491</span><span class="sxs-lookup"><span data-stu-id="98d4f-179">-0.010491</span></span>
<span data-ttu-id="98d4f-180">TaxRate</span><span class="sxs-lookup"><span data-stu-id="98d4f-180">TaxRate</span></span>             |   <span data-ttu-id="98d4f-181">-0,008545</span><span class="sxs-lookup"><span data-stu-id="98d4f-181">-0.008545</span></span>
<span data-ttu-id="98d4f-182">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="98d4f-182">AverageRoomNumber</span></span>   |   <span data-ttu-id="98d4f-183">-0,003949</span><span class="sxs-lookup"><span data-stu-id="98d4f-183">-0.003949</span></span>
<span data-ttu-id="98d4f-184">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="98d4f-184">CrimeRate</span></span>           |   <span data-ttu-id="98d4f-185">-0,003665</span><span class="sxs-lookup"><span data-stu-id="98d4f-185">-0.003665</span></span>
<span data-ttu-id="98d4f-186">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="98d4f-186">CommercialZones</span></span>     |   <span data-ttu-id="98d4f-187">0,002749</span><span class="sxs-lookup"><span data-stu-id="98d4f-187">0.002749</span></span>
<span data-ttu-id="98d4f-188">HomeAge</span><span class="sxs-lookup"><span data-stu-id="98d4f-188">HomeAge</span></span>             |   <span data-ttu-id="98d4f-189">-0,002426</span><span class="sxs-lookup"><span data-stu-id="98d4f-189">-0.002426</span></span>
<span data-ttu-id="98d4f-190">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="98d4f-190">ResidentialZones</span></span>    |   <span data-ttu-id="98d4f-191">-0,002319</span><span class="sxs-lookup"><span data-stu-id="98d4f-191">-0.002319</span></span>
<span data-ttu-id="98d4f-192">NearWater</span><span class="sxs-lookup"><span data-stu-id="98d4f-192">NearWater</span></span>           |   <span data-ttu-id="98d4f-193">0,000203</span><span class="sxs-lookup"><span data-stu-id="98d4f-193">0.000203</span></span>
<span data-ttu-id="98d4f-194">PercentPopulationLivingBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="98d4f-194">PercentPopulationLivingBelowPoverty</span></span>|    <span data-ttu-id="98d4f-195">0,000031</span><span class="sxs-lookup"><span data-stu-id="98d4f-195">0.000031</span></span>
<span data-ttu-id="98d4f-196">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="98d4f-196">ToxicWasteLevels</span></span>    |   <span data-ttu-id="98d4f-197">-0,000019</span><span class="sxs-lookup"><span data-stu-id="98d4f-197">-0.000019</span></span>

<span data-ttu-id="98d4f-198">Wenn Sie sich die fünf wichtigsten Features dieses Datasets ansehen, wird der Preis eines Hauses, der von diesem Modell vorhergesagt wird, durch die Nähe zu Autobahnen, das Verhältnis zwischen Schülern/Studenten und Lehrkräften in der Region, die Nähe zu den wichtigsten Beschäftigungszentren, den Grundsteuersatz und die durchschnittliche Anzahl der Räume im Haus beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="98d4f-198">Taking a look at the five most important features for this dataset, the price of a house predicted by this model is influenced by its proximity to highways, student teacher ratio of schools in the area, proximity to major employment centers, property tax rate and average number of rooms in the home.</span></span>
