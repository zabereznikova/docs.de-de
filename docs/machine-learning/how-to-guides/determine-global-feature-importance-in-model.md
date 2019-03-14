---
title: Bestimmen der Wichtigkeit von Modellfeatures mit Permutation Feature Importance (PFI) in ML.NET
description: Verstehen der Wichtigkeit von Modellfeatures mit Permutation Feature Importance (PFI) in ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b0457bc07168579403e5a00383864c5612e1d17f
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675549"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a>Bestimmen der Wichtigkeit von Modellfeatures mit Permutation Feature Importance (PFI) in ML.NET

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**. Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Bei der Erstellung von Machine Learning-Modellen reicht es oft nicht aus, nur Vorhersagen zu treffen. Häufig müssen Machine Learning- Entwickler, Entscheidungsträger und von den Modellen betroffene Personen erst verstehen, wie Machine Learning-Modelle Entscheidungen treffen und welche Features zu ihrer Leistung beitragen. `Permutation Feature Importance` (PFI) ist ein Modellerklärungswerkzeug, das intern bei Microsoft verwendet wird, um Entwicklern von Machine Learning-Prozessen zu helfen, die Bedeutung von Modellen besser zu verstehen.

PFI ist eine Technik zum Bestimmen der **Wichtigkeit globaler Features** in einem trainierten Machine Learning-Modell, motiviert von Breiman im [Paper „Random Forests“, Abschnitt 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf). PFI misst die Wichtigkeit von Features, indem es die Frage stellt: „Was wäre die Auswirkung auf das Modell, wenn die Werte für ein Feature auf einen zufälligen* Wert festgelegt würden?“. Der Vorteil der PFI-Methode besteht darin, dass sie modellunabhängig ist – sie arbeitet mit jedem Modell, das ausgewertet werden kann – und sie kann jeden Datensatz, nicht nur den Trainingssatz, verwenden, um die Wichtigkeit der Features zu berechnen. Sie können PFI verwenden, um die Wichtigkeit von Features wie in diesem Graph darzustellen:

![Permutation Feature Importance-Graph](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model.LastTransformer, model.Transform(data), "MedianHomeValue");

// Get the feature names from the training set
var featureNames =
    data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Write out the feature names and their importance to the model's Mean R-squared value
for (int i = 0; i < featureNames.Length;i++)
{
    Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].RSquared.Mean:G4}");
}
```

Ein Beispiel für die Verwendung von PFI zum Analysieren der Wichtigkeit von Features eines Modells finden Sie im [ dotnet/machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).

/* Nicht genau zufällig, aber über eine Gruppe von Beispielen permutiert.
