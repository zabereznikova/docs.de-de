---
title: Interpretieren von ML.NET-Modellen mit verallgemeinerten additiven Modellen
description: Verwenden von verallgemeinerten additiven Modellen und Shape-Funktionen zur Modellerklärung in ML.NET
ms.date: 01/30/2020
ms.custom: mvc,how-to
ms.openlocfilehash: 6df19eff4fec98c5815a9f8f4d8e4e9a80cba6ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "77092472"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-interpretability-in-mlnet"></a>Verwenden von verallgemeinerten additiven Modellen und Shape-Funktionen zur Modellerklärung in ML.NET

Bei der Erstellung von Machine Learning-Modellen reicht es oft nicht aus, nur Vorhersagen zu treffen. Häufig müssen Machine Learning- Entwickler, Entscheidungsträger und von den Modellen betroffene Personen erst verstehen, wie Machine Learning-Modelle Entscheidungen treffen und welche Features zu ihrer Leistung beitragen. **Verallgemeinerte additive Modelle (Generalized Additive Models, GAMs)** werden intern bei Microsoft zur Modellerklärung verwendet, um Entwickler von Machine Learning-Prozessen bei der Erstellung leistungsstarker Modelle zu unterstützen, die von anderen leicht interpretiert werden können.

GAMs sind eine Klasse von **interpretierbaren Modellen**. Dabei handelt es sich um lineare Modelle, bei denen die Benennungen nichtlineare Funktionen sind, die als „shape-Funktionen“ einer einzelnen Variablen bezeichnet werden. Als lineare Modelle sind sie leicht zu interpretieren, aber da die Modelle Funktionen von Features anstelle einer einzelnen Gewichtung lernen, können sie komplexere Beziehungen modellieren als ein einfaches lineares Modell. Der resultierende GAM-Vorhersagedienst hat einen Intercept-Term, der die durchschnittliche Vorhersage über den Trainingssatz darstellt, und shape-Funktionen, die die Abweichung von der durchschnittlichen Vorhersage darstellen. Die shape-Funktionen können visuell überprüft werden, um die Reaktion des Modells auf verschiedene Werte eines Features zu analysieren, und wie im folgenden Graph visualisiert werden, der am Ende des Codebeispiels erstellt wird. Der GAM-Trainer in ML.NET wird mithilfe einer flachen, verstärkten Verlaufsstruktur (z.B. Strukturstümpfen) implementiert, um nicht parametrische shape-Funktionen zu erlernen, und basiert auf der in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) von Lou, Caruana und Gehrke beschriebenen Methode.

```csharp
// Train the Generalized Additive Model
var fitPipeline = pipeline.Fit(data);
var gamModel = fitPipeline.LastTransformer.Model;

// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
Console.WriteLine($"Average predicted cost: {intercept:0.00}");

// Get the column names from the training set
var columnNames = data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Get the index of a variable from the training data
var myFeatureIndex = columnNames.ToList().FindIndex(str => str.Equals("MyFeature"));

// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetBinEffects(myFeatureIndex);

// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
{
    Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
}
```

![Graph für shape-Funktion eines verallgemeinerten additiven Modelles](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

Ein Beispiel zum Trainieren eines GAM-Modells und zur Überprüfung und Interpretation der Ergebnisse finden Sie im [dotnet/machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).
