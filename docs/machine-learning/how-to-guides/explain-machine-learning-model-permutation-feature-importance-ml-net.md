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
# <a name="interpret-model-predictions-using-permutation-feature-importance"></a>Interpretieren von Modellvorhersagen mit Permutation Feature Importance

In diesem Artikel erfahren Sie, wie Sie mithilfe von Permutation Feature Importance (PFI) in ML.NET Vorhersagen von Machine Learning-Modellen interpretieren können. PFI stellt Informationen dazu bereit, welchen relativen Anteil jedes Feature an einer Vorhersage hat.

Machine Learning-Modelle werden oft als Blackboxes betrachtet, die aus Eingaben eine Ausgabe generieren. Die Zwischenschritte oder Interaktionen zwischen den Features, die die Ausgabe beeinflussen, werden nur selten verstanden. Da das maschinelle Lernen in immer mehr Bereichen des täglichen Lebens, wie beispielsweise im Gesundheitswesen, zum Einsatz kommt, ist es von größter Bedeutung zu verstehen, warum ein Machine Learning-Modell die Entscheidungen trifft, die es trifft. Wenn die Diagnosen zum Beispiel durch ein Machine Learning-Modell gestellt werden, brauchen die Mediziner eine Möglichkeit, die Faktoren zu untersuchen, die bei der Erstellung dieser Diagnosen berücksichtigt wurden. Die richtige Diagnose könnte einen großen Unterschied machen, ob die Genesung eines Patienten schnell verläuft oder nicht. Je höher also der Grad der Erklärbarkeit in einem Modell ist, desto größer ist das Vertrauen der Mediziner, die die vom Modell getroffenen Entscheidungen akzeptieren oder ablehnen müssen.

Zur Erklärung von Modellen werden verschiedene Techniken verwendet, darunter PFI. PFI ist eine Technik zur Erklärung von Klassifizierungs- und Regressionsmodellen, die von [Leo Breimans Schrift *Random Forests*](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) inspiriert ist (siehe Abschnitt 10). Allgemein funktioniert die Technik so, das Daten für das gesamte Dataset einzeln zufällig gemischt werden und anschließend berechnet wird, wie stark die Leistungsmetrik von Interesse abnimmt. Je größer die Änderung, desto wichtiger ist dieses Feature.

Darüber hinaus können sich Modellersteller durch die Hervorhebung der wichtigsten Features auf die Verwendung einer Teilmenge sinnvoller Features konzentrieren, die Rauschen und Trainingszeiten reduzieren können.

## <a name="load-the-data"></a>Laden der Daten

Die Features im Dataset, das für dieses Beispiel verwendet wird, befinden sich in den Spalten 1-12. Das Ziel ist die Vorhersage von `Price`.

| Spalte | Feature | Beschreibung
| --- | --- | --- |
| 1 | CrimeRate | Pro-Kopf-Kriminalitätsrate
| 2 | ResidentialZones | Wohngebiete in der Stadt
| 3 | CommercialZones | Nicht-Wohngebiete in der Stadt
| 4 | NearWater | Nähe zu einem Gewässer
| 5 | ToxicWasteLevels | Toxizitätswerte (PPM)
| 6 | AverageRoomNumber | Durchschnittliche Anzahl von Räumen in einem Haus
| 7 | HomeAge | Alter des Hauses
| 8 | BusinessCenterDistance | Entfernung zum nächsten Geschäftsviertel
| 9 | HighwayAccess | Geografischer Nähe zu Autobahnen
| 10 | TaxRate | Grundsteuersatz
| 11 | StudentTeacherRatio | Verhältnis zwischen Schülern/Studenten und Lehrkräften
| 12 | PercentPopulationBelowPoverty | Prozentsatz der Bevölkerung, der unter der Armutsgrenze lebt
| 13 | Preis | Preis des Hauses

Ein Beispiel für das Dataset wird unten dargestellt:

```text
1,24,13,1,0.59,3,96,11,23,608,14,13,32
4,80,18,1,0.37,5,14,7,4,346,19,13,41
2,98,16,1,0.25,10,5,1,8,689,13,36,12
```

Die Daten in diesem Beispiel können durch eine Klasse wie `HousingPriceData` modelliert und in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden.

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

## <a name="train-the-model"></a>Trainieren des Modells

Das folgende Codebeispiel veranschaulicht den Prozess des Trainings eines linearen Regressionsmodells zur Vorhersage von Hauspreisen.

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

## <a name="explain-the-model-with-permutation-feature-importance-pfi"></a>Erläutern des Modells mit Permutation Feature Importance (PFI)

ML.NET verwendet die [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions)-Methode für die jeweilige Aufgabe.

```csharp
ImmutableArray<RegressionMetricsStatistics> permutationFeatureImportance =
    mlContext
        .Regression
        .PermutationFeatureImportance(sdcaModel, preprocessedTrainData, permutationCount:3);
```

Das Ergebnis der Verwendung von [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) auf das Trainingsdataset ist ein [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) von [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics)-Objekten. [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) liefert zusammenfassende Statistiken wie Mittelwert und Standardabweichung für mehrere Beobachtungen der [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics), die der Anzahl der durch den `permutationCount`-Parameter angegebenen Permutationen entsprechen.

Die Bedeutung, oder in diesem Fall die aus [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) berechnete absolute durchschnittliche Abnahme der Metrik für das Bestimmtheitsmaß, kann dann vom wichtigsten zum unwichtigsten Feature geordnet werden.

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

Wenn Sie die Werte für jedes Feature in `featureImportanceMetrics` ausdrucken, würde das in etwa wie folgt aussehen. Beachten Sie, dass mit unterschiedlichen Ergebnissen zu rechnen ist, da diese Werte je nach den Daten, die sie erhalten, variieren.

| Feature | Änderung im Bestimmtheitsmaß |
|:--|:--:|
HighwayAccess       |   -0,042731
StudentTeacherRatio |   -0,012730
BusinessCenterDistance| -0,010491
TaxRate             |   -0,008545
AverageRoomNumber   |   -0,003949
CrimeRate           |   -0,003665
CommercialZones     |   0,002749
HomeAge             |   -0,002426
ResidentialZones    |   -0,002319
NearWater           |   0,000203
PercentPopulationLivingBelowPoverty|    0,000031
ToxicWasteLevels    |   -0,000019

Wenn Sie sich die fünf wichtigsten Features dieses Datasets ansehen, wird der Preis eines Hauses, der von diesem Modell vorhergesagt wird, durch die Nähe zu Autobahnen, das Verhältnis zwischen Schülern/Studenten und Lehrkräften in der Region, die Nähe zu den wichtigsten Beschäftigungszentren, den Grundsteuersatz und die durchschnittliche Anzahl der Räume im Haus beeinflusst.
