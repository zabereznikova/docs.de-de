---
title: Bestimmen der Wichtigkeit von Modellfeatures mit Permutation Feature Importance (PFI) in ML.NET
description: Verstehen der Wichtigkeit von Modellfeatures mit Permutation Feature Importance (PFI) in ML.NET
ms.date: 12/04/2018
ms.custom: mvc,how-to
ms.openlocfilehash: ebad89aaee1155d7c116b8536307756227dced31
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307109"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a><span data-ttu-id="8359f-103">Bestimmen der Wichtigkeit von Modellfeatures mit Permutation Feature Importance (PFI) in ML.NET</span><span class="sxs-lookup"><span data-stu-id="8359f-103">Determine the feature importance of models with Permutation Feature Importance in ML.NET</span></span>

<span data-ttu-id="8359f-104">Bei der Erstellung von Machine Learning-Modellen reicht es oft nicht aus, nur Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="8359f-104">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="8359f-105">Häufig müssen Machine Learning- Entwickler, Entscheidungsträger und von den Modellen betroffene Personen erst verstehen, wie Machine Learning-Modelle Entscheidungen treffen und welche Features zu ihrer Leistung beitragen.</span><span class="sxs-lookup"><span data-stu-id="8359f-105">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="8359f-106">`Permutation Feature Importance` (PFI) ist ein Modellerklärungswerkzeug, das intern bei Microsoft verwendet wird, um Entwicklern von Machine Learning-Prozessen zu helfen, die Bedeutung von Modellen besser zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="8359f-106">`Permutation Feature Importance` (PFI) is a model explainability tool that is used internally at Microsoft to help machine learning developers better understand the feature importance of models.</span></span>

<span data-ttu-id="8359f-107">PFI ist eine Technik zum Bestimmen der **Wichtigkeit globaler Features** in einem trainierten Machine Learning-Modell, motiviert von Breiman im [Paper „Random Forests“, Abschnitt 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span><span class="sxs-lookup"><span data-stu-id="8359f-107">PFI is a technique to determine **global feature importance** in a trained machine learning model, motivated by Breiman in the ["Random Forests" paper, section 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span></span> <span data-ttu-id="8359f-108">PFI misst die Wichtigkeit von Features, indem es die Frage stellt: „Was wäre die Auswirkung auf das Modell, wenn die Werte für ein Feature auf einen zufälligen\* Wert festgelegt würden?“.</span><span class="sxs-lookup"><span data-stu-id="8359f-108">PFI measures feature importance by asking the question, "What would the effect on the model be if the values for a feature were set to a random\* value?".</span></span> <span data-ttu-id="8359f-109">Der Vorteil der PFI-Methode besteht darin, dass sie modellunabhängig ist – sie arbeitet mit jedem Modell, das ausgewertet werden kann – und sie kann jeden Datensatz, nicht nur den Trainingssatz, verwenden, um die Wichtigkeit der Features zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="8359f-109">The advantage of the PFI method is that it is model agnostic — it works with any model that can be evaluated — and it can use any dataset, not just the training set, to compute feature importance.</span></span> <span data-ttu-id="8359f-110">Sie können PFI verwenden, um die Wichtigkeit von Features wie in diesem Graph darzustellen:</span><span class="sxs-lookup"><span data-stu-id="8359f-110">You can use PFI like so to produce feature importances like this graph:</span></span>

![Permutation Feature Importance-Graph](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model, data);
 
// Get the feature names from the training set
var featureNames = data.Schema.GetColumns()
                .Select(tuple => tuple.column.Name) // Get the column names
                .Where(name => name != labelName) // Drop the Label
                .ToArray();
 
// Write out the feature names and their importance to the model's R-squared value
for (int i = 0; i < featureNames.Length; i++)
  Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].rSquared:G4}");
```

<span data-ttu-id="8359f-112">Ein Beispiel für die Verwendung von PFI zum Analysieren der Wichtigkeit von Features eines Modells finden Sie im [ dotnet/machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span><span class="sxs-lookup"><span data-stu-id="8359f-112">For a sample using PFI to analyze the feature importance of a model, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span></span>

<span data-ttu-id="8359f-113">/\* Nicht genau zufällig, aber über eine Gruppe von Beispielen permutiert.</span><span class="sxs-lookup"><span data-stu-id="8359f-113">/\* Well, not random exactly, but permuted across the set of examples.</span></span>
