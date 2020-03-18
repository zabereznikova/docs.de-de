---
title: Interpretieren von ML.NET-Modellen mit Permutation Feature Importance
description: Verstehen der Wichtigkeit von Modellfeatures mit Permutation Feature Importance (PFI) in ML.NET
ms.date: 01/30/2020
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: c1163a41cd2feb0e8785ae9d4c6a71dfbedf3f12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "77092615"
---
# <a name="interpret-model-predictions-using-permutation-feature-importance"></a><span data-ttu-id="13198-103">Interpretieren von Modellvorhersagen mit Permutation Feature Importance</span><span class="sxs-lookup"><span data-stu-id="13198-103">Interpret model predictions using Permutation Feature Importance</span></span>

<span data-ttu-id="13198-104">In diesem Artikel erfahren Sie, wie Sie mithilfe von Permutation Feature Importance (PFI) in ML.NET Vorhersagen von Machine Learning-Modellen interpretieren können.</span><span class="sxs-lookup"><span data-stu-id="13198-104">Using Permutation Feature Importance (PFI), learn how to interpret ML.NET machine learning model predictions.</span></span> <span data-ttu-id="13198-105">PFI stellt Informationen dazu bereit, welchen relativen Anteil jedes Feature an einer Vorhersage hat.</span><span class="sxs-lookup"><span data-stu-id="13198-105">PFI gives the relative contribution each feature makes to a prediction.</span></span>

<span data-ttu-id="13198-106">Machine Learning-Modelle werden oft als Blackboxes betrachtet, die aus Eingaben eine Ausgabe generieren.</span><span class="sxs-lookup"><span data-stu-id="13198-106">Machine learning models are often thought of as black boxes that take inputs and generate an output.</span></span> <span data-ttu-id="13198-107">Die Zwischenschritte oder Interaktionen zwischen den Features, die die Ausgabe beeinflussen, werden nur selten verstanden.</span><span class="sxs-lookup"><span data-stu-id="13198-107">The intermediate steps or interactions among the features that influence the output are rarely understood.</span></span> <span data-ttu-id="13198-108">Da das maschinelle Lernen in immer mehr Bereichen des täglichen Lebens, wie beispielsweise im Gesundheitswesen, zum Einsatz kommt, ist es von größter Bedeutung zu verstehen, warum ein Machine Learning-Modell die Entscheidungen trifft, die es trifft.</span><span class="sxs-lookup"><span data-stu-id="13198-108">As machine learning is introduced into more aspects of everyday life such as healthcare, it's of utmost importance to understand why a machine learning model makes the decisions it does.</span></span> <span data-ttu-id="13198-109">Wenn die Diagnosen zum Beispiel durch ein Machine Learning-Modell gestellt werden, brauchen die Mediziner eine Möglichkeit, die Faktoren zu untersuchen, die bei der Erstellung dieser Diagnosen berücksichtigt wurden.</span><span class="sxs-lookup"><span data-stu-id="13198-109">For example, if diagnoses are made by a machine learning model, healthcare professionals need a way to look into the factors that went into making that diagnoses.</span></span> <span data-ttu-id="13198-110">Die richtige Diagnose könnte einen großen Unterschied machen, ob die Genesung eines Patienten schnell verläuft oder nicht.</span><span class="sxs-lookup"><span data-stu-id="13198-110">Providing the right diagnosis could make a great difference on whether a patient has a speedy recovery or not.</span></span> <span data-ttu-id="13198-111">Je höher also der Grad der Erklärbarkeit in einem Modell ist, desto größer ist das Vertrauen der Mediziner, die die vom Modell getroffenen Entscheidungen akzeptieren oder ablehnen müssen.</span><span class="sxs-lookup"><span data-stu-id="13198-111">Therefore the higher the level of explainability in a model, the greater confidence healthcare professionals have to accept or reject the decisions made by the model.</span></span>

<span data-ttu-id="13198-112">Zur Erklärung von Modellen werden verschiedene Techniken verwendet, darunter PFI.</span><span class="sxs-lookup"><span data-stu-id="13198-112">Various techniques are used to explain models, one of which is PFI.</span></span> <span data-ttu-id="13198-113">PFI ist eine Technik zur Erklärung von Klassifizierungs- und Regressionsmodellen, die von [Leo Breimans Schrift *Random Forests*](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) inspiriert ist (siehe Abschnitt 10).</span><span class="sxs-lookup"><span data-stu-id="13198-113">PFI is a technique used to explain classification and regression models that is inspired by [Breiman's *Random Forests* paper](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (see section 10).</span></span> <span data-ttu-id="13198-114">Allgemein funktioniert die Technik so, das Daten für das gesamte Dataset einzeln zufällig gemischt werden und anschließend berechnet wird, wie stark die Leistungsmetrik von Interesse abnimmt.</span><span class="sxs-lookup"><span data-stu-id="13198-114">At a high level, the way it works is by randomly shuffling data one feature at a time for the entire dataset and calculating how much the performance metric of interest decreases.</span></span> <span data-ttu-id="13198-115">Je größer die Änderung, desto wichtiger ist dieses Feature.</span><span class="sxs-lookup"><span data-stu-id="13198-115">The larger the change, the more important that feature is.</span></span>

<span data-ttu-id="13198-116">Darüber hinaus können sich Modellersteller durch die Hervorhebung der wichtigsten Features auf die Verwendung einer Teilmenge sinnvoller Features konzentrieren, die Rauschen und Trainingszeiten reduzieren können.</span><span class="sxs-lookup"><span data-stu-id="13198-116">Additionally, by highlighting the most important features, model builders can focus on using a subset of more meaningful features which can potentially reduce noise and training time.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="13198-117">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="13198-117">Load the data</span></span>

<span data-ttu-id="13198-118">Die Features im Dataset, das für dieses Beispiel verwendet wird, befinden sich in den Spalten 1-12.</span><span class="sxs-lookup"><span data-stu-id="13198-118">The features in the dataset being used for this sample are in columns 1-12.</span></span> <span data-ttu-id="13198-119">Das Ziel ist die Vorhersage von `Price`.</span><span class="sxs-lookup"><span data-stu-id="13198-119">The goal is to predict `Price`.</span></span>

| <span data-ttu-id="13198-120">Spalte</span><span class="sxs-lookup"><span data-stu-id="13198-120">Column</span></span> | <span data-ttu-id="13198-121">Feature</span><span class="sxs-lookup"><span data-stu-id="13198-121">Feature</span></span> | <span data-ttu-id="13198-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13198-122">Description</span></span>
| --- | --- | --- |
| <span data-ttu-id="13198-123">1</span><span class="sxs-lookup"><span data-stu-id="13198-123">1</span></span> | <span data-ttu-id="13198-124">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="13198-124">CrimeRate</span></span> | <span data-ttu-id="13198-125">Pro-Kopf-Kriminalitätsrate</span><span class="sxs-lookup"><span data-stu-id="13198-125">Per capita crime rate</span></span>
| <span data-ttu-id="13198-126">2</span><span class="sxs-lookup"><span data-stu-id="13198-126">2</span></span> | <span data-ttu-id="13198-127">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="13198-127">ResidentialZones</span></span> | <span data-ttu-id="13198-128">Wohngebiete in der Stadt</span><span class="sxs-lookup"><span data-stu-id="13198-128">Residential zones in town</span></span>
| <span data-ttu-id="13198-129">3</span><span class="sxs-lookup"><span data-stu-id="13198-129">3</span></span> | <span data-ttu-id="13198-130">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="13198-130">CommercialZones</span></span> | <span data-ttu-id="13198-131">Nicht-Wohngebiete in der Stadt</span><span class="sxs-lookup"><span data-stu-id="13198-131">Non-residential zones in town</span></span>
| <span data-ttu-id="13198-132">4</span><span class="sxs-lookup"><span data-stu-id="13198-132">4</span></span> | <span data-ttu-id="13198-133">NearWater</span><span class="sxs-lookup"><span data-stu-id="13198-133">NearWater</span></span> | <span data-ttu-id="13198-134">Nähe zu einem Gewässer</span><span class="sxs-lookup"><span data-stu-id="13198-134">Proximity to body of water</span></span>
| <span data-ttu-id="13198-135">5</span><span class="sxs-lookup"><span data-stu-id="13198-135">5</span></span> | <span data-ttu-id="13198-136">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="13198-136">ToxicWasteLevels</span></span> | <span data-ttu-id="13198-137">Toxizitätswerte (PPM)</span><span class="sxs-lookup"><span data-stu-id="13198-137">Toxicity levels (PPM)</span></span>
| <span data-ttu-id="13198-138">6</span><span class="sxs-lookup"><span data-stu-id="13198-138">6</span></span> | <span data-ttu-id="13198-139">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="13198-139">AverageRoomNumber</span></span> | <span data-ttu-id="13198-140">Durchschnittliche Anzahl von Räumen in einem Haus</span><span class="sxs-lookup"><span data-stu-id="13198-140">Average number of rooms in house</span></span>
| <span data-ttu-id="13198-141">7</span><span class="sxs-lookup"><span data-stu-id="13198-141">7</span></span> | <span data-ttu-id="13198-142">HomeAge</span><span class="sxs-lookup"><span data-stu-id="13198-142">HomeAge</span></span> | <span data-ttu-id="13198-143">Alter des Hauses</span><span class="sxs-lookup"><span data-stu-id="13198-143">Age of home</span></span>
| <span data-ttu-id="13198-144">8</span><span class="sxs-lookup"><span data-stu-id="13198-144">8</span></span> | <span data-ttu-id="13198-145">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="13198-145">BusinessCenterDistance</span></span> | <span data-ttu-id="13198-146">Entfernung zum nächsten Geschäftsviertel</span><span class="sxs-lookup"><span data-stu-id="13198-146">Distance to nearest business district</span></span>
| <span data-ttu-id="13198-147">9</span><span class="sxs-lookup"><span data-stu-id="13198-147">9</span></span> | <span data-ttu-id="13198-148">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="13198-148">HighwayAccess</span></span> | <span data-ttu-id="13198-149">Geografischer Nähe zu Autobahnen</span><span class="sxs-lookup"><span data-stu-id="13198-149">Proximity to highways</span></span>
| <span data-ttu-id="13198-150">10</span><span class="sxs-lookup"><span data-stu-id="13198-150">10</span></span> | <span data-ttu-id="13198-151">TaxRate</span><span class="sxs-lookup"><span data-stu-id="13198-151">TaxRate</span></span> | <span data-ttu-id="13198-152">Grundsteuersatz</span><span class="sxs-lookup"><span data-stu-id="13198-152">Property tax rate</span></span>
| <span data-ttu-id="13198-153">11</span><span class="sxs-lookup"><span data-stu-id="13198-153">11</span></span> | <span data-ttu-id="13198-154">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="13198-154">StudentTeacherRatio</span></span> | <span data-ttu-id="13198-155">Verhältnis zwischen Schülern/Studenten und Lehrkräften</span><span class="sxs-lookup"><span data-stu-id="13198-155">Ratio of students to teachers</span></span>
| <span data-ttu-id="13198-156">12</span><span class="sxs-lookup"><span data-stu-id="13198-156">12</span></span> | <span data-ttu-id="13198-157">PercentPopulationBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="13198-157">PercentPopulationBelowPoverty</span></span> | <span data-ttu-id="13198-158">Prozentsatz der Bevölkerung, der unter der Armutsgrenze lebt</span><span class="sxs-lookup"><span data-stu-id="13198-158">Percent of population living below poverty</span></span>
| <span data-ttu-id="13198-159">13</span><span class="sxs-lookup"><span data-stu-id="13198-159">13</span></span> | <span data-ttu-id="13198-160">Preis</span><span class="sxs-lookup"><span data-stu-id="13198-160">Price</span></span> | <span data-ttu-id="13198-161">Preis des Hauses</span><span class="sxs-lookup"><span data-stu-id="13198-161">Price of the home</span></span>

<span data-ttu-id="13198-162">Ein Beispiel für das Dataset wird unten dargestellt:</span><span class="sxs-lookup"><span data-stu-id="13198-162">A sample of the dataset is shown below:</span></span>

```text
1,24,13,1,0.59,3,96,11,23,608,14,13,32
4,80,18,1,0.37,5,14,7,4,346,19,13,41
2,98,16,1,0.25,10,5,1,8,689,13,36,12
```

<span data-ttu-id="13198-163">Die Daten in diesem Beispiel können durch eine Klasse wie `HousingPriceData` modelliert und in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden.</span><span class="sxs-lookup"><span data-stu-id="13198-163">The data in this sample can be modeled by a class like `HousingPriceData` and loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

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

## <a name="train-the-model"></a><span data-ttu-id="13198-164">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="13198-164">Train the model</span></span>

<span data-ttu-id="13198-165">Das folgende Codebeispiel veranschaulicht den Prozess des Trainings eines linearen Regressionsmodells zur Vorhersage von Hauspreisen.</span><span class="sxs-lookup"><span data-stu-id="13198-165">The code sample below illustrates the process of training a linear regression model to predict house prices.</span></span>

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

## <a name="explain-the-model-with-permutation-feature-importance-pfi"></a><span data-ttu-id="13198-166">Erläutern des Modells mit Permutation Feature Importance (PFI)</span><span class="sxs-lookup"><span data-stu-id="13198-166">Explain the model with Permutation Feature Importance (PFI)</span></span>

<span data-ttu-id="13198-167">ML.NET verwendet die [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions)-Methode für die jeweilige Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="13198-167">In ML.NET use the [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) method for your respective task.</span></span>

```csharp
ImmutableArray<RegressionMetricsStatistics> permutationFeatureImportance =
    mlContext
        .Regression
        .PermutationFeatureImportance(sdcaModel, preprocessedTrainData, permutationCount:3);
```

<span data-ttu-id="13198-168">Das Ergebnis der Verwendung von [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) auf das Trainingsdataset ist ein [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) von [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics)-Objekten.</span><span class="sxs-lookup"><span data-stu-id="13198-168">The result of using [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) on the training dataset is an [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) of [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) objects.</span></span> <span data-ttu-id="13198-169">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) liefert zusammenfassende Statistiken wie Mittelwert und Standardabweichung für mehrere Beobachtungen der [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics), die der Anzahl der durch den `permutationCount`-Parameter angegebenen Permutationen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="13198-169">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) provides summary statistics like mean and standard deviation for multiple observations of [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics) equal to the number of permutations specified by the `permutationCount` parameter.</span></span>

<span data-ttu-id="13198-170">Die Bedeutung, oder in diesem Fall die aus [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) berechnete absolute durchschnittliche Abnahme der Metrik für das Bestimmtheitsmaß, kann dann vom wichtigsten zum unwichtigsten Feature geordnet werden.</span><span class="sxs-lookup"><span data-stu-id="13198-170">The importance, or in this case, the absolute average decrease in R-squared metric calculated by [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) can then be ordered from most important to least important.</span></span>

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

<span data-ttu-id="13198-171">Wenn Sie die Werte für jedes Feature in `featureImportanceMetrics` ausdrucken, würde das in etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="13198-171">Printing the values for each of the features in `featureImportanceMetrics` would generate output similar to that below.</span></span> <span data-ttu-id="13198-172">Beachten Sie, dass mit unterschiedlichen Ergebnissen zu rechnen ist, da diese Werte je nach den Daten, die sie erhalten, variieren.</span><span class="sxs-lookup"><span data-stu-id="13198-172">Keep in mind that you should expect to see different results because these values vary based on the data that they are given.</span></span>

| <span data-ttu-id="13198-173">Feature</span><span class="sxs-lookup"><span data-stu-id="13198-173">Feature</span></span> | <span data-ttu-id="13198-174">Änderung im Bestimmtheitsmaß</span><span class="sxs-lookup"><span data-stu-id="13198-174">Change to R-Squared</span></span> |
|:--|:--:|
<span data-ttu-id="13198-175">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="13198-175">HighwayAccess</span></span>       |   <span data-ttu-id="13198-176">-0,042731</span><span class="sxs-lookup"><span data-stu-id="13198-176">-0.042731</span></span>
<span data-ttu-id="13198-177">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="13198-177">StudentTeacherRatio</span></span> |   <span data-ttu-id="13198-178">-0,012730</span><span class="sxs-lookup"><span data-stu-id="13198-178">-0.012730</span></span>
<span data-ttu-id="13198-179">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="13198-179">BusinessCenterDistance</span></span>| <span data-ttu-id="13198-180">-0,010491</span><span class="sxs-lookup"><span data-stu-id="13198-180">-0.010491</span></span>
<span data-ttu-id="13198-181">TaxRate</span><span class="sxs-lookup"><span data-stu-id="13198-181">TaxRate</span></span>             |   <span data-ttu-id="13198-182">-0,008545</span><span class="sxs-lookup"><span data-stu-id="13198-182">-0.008545</span></span>
<span data-ttu-id="13198-183">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="13198-183">AverageRoomNumber</span></span>   |   <span data-ttu-id="13198-184">-0,003949</span><span class="sxs-lookup"><span data-stu-id="13198-184">-0.003949</span></span>
<span data-ttu-id="13198-185">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="13198-185">CrimeRate</span></span>           |   <span data-ttu-id="13198-186">-0,003665</span><span class="sxs-lookup"><span data-stu-id="13198-186">-0.003665</span></span>
<span data-ttu-id="13198-187">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="13198-187">CommercialZones</span></span>     |   <span data-ttu-id="13198-188">0,002749</span><span class="sxs-lookup"><span data-stu-id="13198-188">0.002749</span></span>
<span data-ttu-id="13198-189">HomeAge</span><span class="sxs-lookup"><span data-stu-id="13198-189">HomeAge</span></span>             |   <span data-ttu-id="13198-190">-0,002426</span><span class="sxs-lookup"><span data-stu-id="13198-190">-0.002426</span></span>
<span data-ttu-id="13198-191">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="13198-191">ResidentialZones</span></span>    |   <span data-ttu-id="13198-192">-0,002319</span><span class="sxs-lookup"><span data-stu-id="13198-192">-0.002319</span></span>
<span data-ttu-id="13198-193">NearWater</span><span class="sxs-lookup"><span data-stu-id="13198-193">NearWater</span></span>           |   <span data-ttu-id="13198-194">0,000203</span><span class="sxs-lookup"><span data-stu-id="13198-194">0.000203</span></span>
<span data-ttu-id="13198-195">PercentPopulationLivingBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="13198-195">PercentPopulationLivingBelowPoverty</span></span>|    <span data-ttu-id="13198-196">0,000031</span><span class="sxs-lookup"><span data-stu-id="13198-196">0.000031</span></span>
<span data-ttu-id="13198-197">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="13198-197">ToxicWasteLevels</span></span>    |   <span data-ttu-id="13198-198">-0,000019</span><span class="sxs-lookup"><span data-stu-id="13198-198">-0.000019</span></span>

<span data-ttu-id="13198-199">Wenn Sie sich die fünf wichtigsten Features dieses Datasets ansehen, wird der Preis eines Hauses, der von diesem Modell vorhergesagt wird, durch die Nähe zu Autobahnen, das Verhältnis zwischen Schülern/Studenten und Lehrkräften in der Region, die Nähe zu den wichtigsten Beschäftigungszentren, den Grundsteuersatz und die durchschnittliche Anzahl der Räume im Haus beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="13198-199">Taking a look at the five most important features for this dataset, the price of a house predicted by this model is influenced by its proximity to highways, student teacher ratio of schools in the area, proximity to major employment centers, property tax rate and average number of rooms in the home.</span></span>
