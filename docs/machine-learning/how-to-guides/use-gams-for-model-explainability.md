---
title: Einsatz von verallgemeinerten additiven Modellen und shape-Funktionen zur Modellerklärung
description: Einsatz von verallgemeinerten additiven Modellen und shape-Funktionen zur Modellerklärung in ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: c58cf823007196c35da093fab7423c1e40ba1158
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855606"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a><span data-ttu-id="f91b6-103">Einsatz von verallgemeinerten additiven Modellen und shape-Funktionen zur Modellerklärung in ML.NET</span><span class="sxs-lookup"><span data-stu-id="f91b6-103">Use Generalized Additive Models and shape functions for model explainability in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="f91b6-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f91b6-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="f91b6-105">Weitere Informationen finden Sie auf der Seite [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f91b6-105">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="f91b6-106">Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**.</span><span class="sxs-lookup"><span data-stu-id="f91b6-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="f91b6-107">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="f91b6-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="f91b6-108">Bei der Erstellung von Machine Learning-Modellen reicht es oft nicht aus, nur Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="f91b6-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="f91b6-109">Häufig müssen Machine Learning- Entwickler, Entscheidungsträger und von den Modellen betroffene Personen erst verstehen, wie Machine Learning-Modelle Entscheidungen treffen und welche Features zu ihrer Leistung beitragen.</span><span class="sxs-lookup"><span data-stu-id="f91b6-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="f91b6-110">**Verallgemeinerte additive Modelle (Generalized Additive Models, GAMs)** werden intern bei Microsoft zur Modellerklärung verwendet, um Entwickler von Machine Learning-Prozessen bei der Erstellung leistungsstarker Modelle zu unterstützen, die von anderen leicht interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f91b6-110">**Generalized Additive Models (GAMs)** are used internally at Microsoft for model explainability to help machine learning developers create high-capacity models that can be easily interpreted by others.</span></span>

<span data-ttu-id="f91b6-111">GAMs sind eine Klasse von **interpretierbaren Modellen**. Dabei handelt es sich um lineare Modelle, bei denen die Benennungen nichtlineare Funktionen sind, die als „shape-Funktionen“ einer einzelnen Variablen bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="f91b6-111">GAMs are a class of **interpretable models** that are linear models where the terms are nonlinear functions, called "shape functions" of a single variable.</span></span> <span data-ttu-id="f91b6-112">Als lineare Modelle sind sie leicht zu interpretieren, aber da die Modelle Funktionen von Features anstelle einer einzelnen Gewichtung lernen, können sie komplexere Beziehungen modellieren als ein einfaches lineares Modell.</span><span class="sxs-lookup"><span data-stu-id="f91b6-112">As linear models, they are easily interpreted but because the models learn functions of features instead of a single weight, they can model more complex relationships than a simple linear model.</span></span> <span data-ttu-id="f91b6-113">Der resultierende GAM-Vorhersagedienst hat einen Intercept-Term, der die durchschnittliche Vorhersage über den Trainingssatz darstellt, und shape-Funktionen, die die Abweichung von der durchschnittlichen Vorhersage darstellen.</span><span class="sxs-lookup"><span data-stu-id="f91b6-113">The resulting GAM predictor has an intercept term that represents the average prediction over the training set, and shape functions that represent the deviation from the average prediction.</span></span> <span data-ttu-id="f91b6-114">Die shape-Funktionen können visuell überprüft werden, um die Reaktion des Modells auf verschiedene Werte eines Features zu analysieren, und wie im folgenden Graph visualisiert werden, der am Ende des Codebeispiels erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f91b6-114">The shape functions can be inspected by eye to see the response of the model to different values of a feature, and visualized like the following graph that is created at the end of the code example.</span></span> <span data-ttu-id="f91b6-115">Der GAM-Trainer in ML.NET wird mithilfe einer flachen, verstärkten Verlaufsstruktur (z.B. Strukturstümpfen) implementiert, um nicht parametrische shape-Funktionen zu erlernen, und basiert auf der in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) von Lou, Caruana und Gehrke beschriebenen Methode.</span><span class="sxs-lookup"><span data-stu-id="f91b6-115">The GAM trainer in ML.NET is implemented using shallow gradient boosted trees (for example tree stumps) to learn nonparametric shape functions, and is based on the method described in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) by Lou, Caruana, and Gehrke.</span></span>

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

<span data-ttu-id="f91b6-117">Ein Beispiel zum Trainieren eines GAM-Modells und zur Überprüfung und Interpretation der Ergebnisse finden Sie im [dotnet/machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span><span class="sxs-lookup"><span data-stu-id="f91b6-117">For a sample of how to train a GAM model and inspect and interpret the results, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span></span>
