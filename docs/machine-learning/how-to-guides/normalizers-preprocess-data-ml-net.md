---
title: 'Vorverarbeiten von Trainingsdaten mit Normalisierungsfunktionen zur Nutzung in der Datenverarbeitung: ML.NET'
description: Erfahren Sie, wie Sie Normalisierungsfunktionen verwenden, um Trainingsdaten für die Modellerstellung für maschinelles Lernen vorzuverarbeiten.
ms.date: 02/01/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4311307f5410a96bb4a30fcedd88bc43afd25c12
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738577"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a>Vorverarbeiten von Trainingsdaten mit Normalisierungsfunktionen zur Nutzung in der Datenverarbeitung: ML.NET

ML.NET bietet eine Reihe von [parametrischen und nicht parametrischen Algorithmen](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).

Es ist **nicht** so entscheidend, welche Normalisierungsfunktion Sie wählen. Entscheidender ist, dass Sie überhaupt eine Normalisierungsfunktion **verwenden**, wenn Sie lineare oder andere parametrische Modelle trainieren.

Beziehen Sie die Normalisierungsfunktion immer direkt in die ML.NET-Lernpipeline mit ein, um Folgendes zu erreichen:

- Die Lernpipeline wird nur auf Basis der Trainingsdaten trainiert und nicht auf Basis Ihrer Testdaten.
- Sie wird korrekt auf alle eingehenden Daten angewendet, ohne dass eine zusätzliche Vorverarbeitung bei der Vorhersage nötig ist.

Hier finden Sie einen Codeausschnitt, in dem die Normalisierung in Lernpipelines dargestellt ist. Hierfür wird vom Iris-Dataset ausgegangen:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(
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
        new NormalizingEstimator.MinMaxColumn("Features", "MinMaxNormalized", fixZero: true),
        new NormalizingEstimator.MeanVarColumn("Features", "MeanVarNormalized", fixZero: true),
        new NormalizingEstimator.BinningColumn("Features", "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
