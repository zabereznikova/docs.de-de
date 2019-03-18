---
title: Untersuchen von Zwischendatenwerten bei der Verarbeitung der Pipeline für maschinelles Lernen mit ML.NET
description: Lernen Sie, wie Sie die tatsächlichen Zwischendatenwerte bei der Verarbeitung der Pipeline für maschinelles Lernen mit ML.NET untersuchen können.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 362cb9351c3cb77b6aa67d59154854e882869ad9
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2019
ms.locfileid: "57843415"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a><span data-ttu-id="167b4-103">Untersuchen von Zwischendatenwerten bei der Verarbeitung der Pipeline für maschinelles Lernen mit ML.NET</span><span class="sxs-lookup"><span data-stu-id="167b4-103">Inspect intermediate data values during ML.NET pipeline processing</span></span>

> [!NOTE]
> <span data-ttu-id="167b4-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="167b4-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="167b4-105">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="167b4-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="167b4-106">Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**.</span><span class="sxs-lookup"><span data-stu-id="167b4-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="167b4-107">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="167b4-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="167b4-108">Während des Experiments sollten Sie die Ergebnisse der Datenverarbeitung zu einem bestimmten Zeitpunkt überwachen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="167b4-108">During the experiment, you may want to observe and validate the data processing results at a given point.</span></span> <span data-ttu-id="167b4-109">Dies ist nicht einfach, da ML.NET-Vorgänge verzögert sind und Objekte erstellen, die „Datenversprechen“ sind.</span><span class="sxs-lookup"><span data-stu-id="167b4-109">This isn't easy since ML.NET operations are lazy, constructing objects that are 'promises' of data.</span></span>

<span data-ttu-id="167b4-110">Die `GetColumn<T>`-Erweiterungsmethode ermöglicht Ihnen das Untersuchen der Zwischendaten.</span><span class="sxs-lookup"><span data-stu-id="167b4-110">The `GetColumn<T>` extension method lets you inspect the intermediate data.</span></span> <span data-ttu-id="167b4-111">Gibt die Inhalte einer Datenspalte als ein `IEnumerable` zurück.</span><span class="sxs-lookup"><span data-stu-id="167b4-111">It returns the contents of one data column as an `IEnumerable`.</span></span>

<span data-ttu-id="167b4-112">Im folgenden Beispiel wird die Verwendung der `GetColumn<T>`-Erweiterungsmethode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="167b4-112">The following example shows how to use the `GetColumn<T>` extension method:</span></span>

<span data-ttu-id="167b4-113">[Beispieldatei](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="167b4-113">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span></span>

<!-- markdownlint-disable MD010 -->
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```
<!-- markdownlint-enable MD010 -->

<span data-ttu-id="167b4-114">Die Definition sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="167b4-114">Our class is defined as follows:</span></span>

```csharp
public class InspectedRow
{
    [LoadColumn(0)]
    public bool IsOver50K { get; set; }
    [LoadColumn(1)]
    public string WorkClass { get; set; }
    [LoadColumn(2)]
    public string Education { get; set; }
    [LoadColumn(3)]
    public string MaritalStatus { get; set; }
}
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Read the data into a data view.
var data = mlContext.Data.ReadFromTextFile<InspectedRow>(dataPath, hasHeader: true);

// Start creating our processing pipeline. For now, let's just concatenate all the text columns
// together into one.
var pipeline = mlContext.Transforms.Concatenate("AllFeatures", "WorkClass", "Education", "MaritalStatus");

// Fit our data pipeline and transform data with it.
var transformedData = pipeline.Fit(data).Transform(data);

// Extract the 'AllFeatures' column.
// This will give the entire dataset: make sure to only take several row
// in case the dataset is huge. The is similar to the static API, except
// you have to specify the column name and type.
var featureColumns =
    transformedData
        .GetColumn<string[]>(mlContext, "AllFeatures")
        .Take(20)
        .ToArray();
```
