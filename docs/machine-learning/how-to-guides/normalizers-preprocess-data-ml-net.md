---
title: 'Vorverarbeiten von Trainingsdaten mit Normalisierungsfunktionen zur Nutzung in der Datenverarbeitung: ML.NET'
description: Erfahren Sie, wie Sie Normalisierungsfunktionen verwenden, um Trainingsdaten für die Modellerstellung für maschinelles Lernen vorzuverarbeiten.
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 28d358cd381f71b4116e1dd25d847fc51835f09e
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093046"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a><span data-ttu-id="22ef6-103">Vorverarbeiten von Trainingsdaten mit Normalisierungsfunktionen zur Nutzung in der Datenverarbeitung: ML.NET</span><span class="sxs-lookup"><span data-stu-id="22ef6-103">Preprocess training data with normalizers to use in data processing - ML.NET</span></span>

<span data-ttu-id="22ef6-104">ML.NET bietet eine Reihe von [parametrischen und nicht parametrischen Algorithmen](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span><span class="sxs-lookup"><span data-stu-id="22ef6-104">ML.NET exposes a number of [parametric and non-parametric algorithms](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span></span>

<span data-ttu-id="22ef6-105">Es ist **nicht** so entscheidend, welche Normalisierungsfunktion Sie wählen. Entscheidender ist, dass Sie überhaupt eine Normalisierungsfunktion **verwenden**, wenn Sie lineare oder andere parametrische Modelle trainieren.</span><span class="sxs-lookup"><span data-stu-id="22ef6-105">It's **not** as important which normalizer you choose as it is to **use** a normalizer when training linear or other parametric models.</span></span>

<span data-ttu-id="22ef6-106">Beziehen Sie die Normalisierungsfunktion immer direkt in die ML.NET-Lernpipeline mit ein, um Folgendes zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="22ef6-106">Always include the normalizer directly in the ML.NET learning pipeline, so it:</span></span>

- <span data-ttu-id="22ef6-107">Die Lernpipeline wird nur auf Basis der Trainingsdaten trainiert und nicht auf Basis Ihrer Testdaten.</span><span class="sxs-lookup"><span data-stu-id="22ef6-107">is only trained on the training data, and not on your test data,</span></span>
- <span data-ttu-id="22ef6-108">Sie wird korrekt auf alle eingehenden Daten angewendet, ohne dass eine zusätzliche Vorverarbeitung bei der Vorhersage nötig ist.</span><span class="sxs-lookup"><span data-stu-id="22ef6-108">is correctly applied to all the new incoming data, without the need for extra pre-processing at prediction time.</span></span>

<span data-ttu-id="22ef6-109">Hier finden Sie einen Codeausschnitt, in dem die Normalisierung in Lernpipelines dargestellt ist.</span><span class="sxs-lookup"><span data-stu-id="22ef6-109">Here's a snippet of code that demonstrates normalization in learning pipelines.</span></span> <span data-ttu-id="22ef6-110">Hierfür wird vom Iris-Dataset ausgegangen:</span><span class="sxs-lookup"><span data-stu-id="22ef6-110">It assumes the Iris dataset:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features",DataKind.R4,0,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has comma.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
            new NormalizingEstimator.MinMaxColumn(inputColumnName:"Features", outputColumnName:"MinMaxNormalized", fixZero: true),
            new NormalizingEstimator.MeanVarColumn(inputColumnName: "Features", outputColumnName: "MeanVarNormalized", fixZero: true),
            new NormalizingEstimator.BinningColumn(inputColumnName: "Features", outputColumnName: "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
