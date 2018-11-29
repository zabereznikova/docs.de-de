---
title: Untersuchen von Zwischendatenwerten bei der Verarbeitung der Pipeline für maschinelles Lernen mit ML.NET
description: Lernen Sie, wie Sie die tatsächlichen Zwischendatenwerte bei der Verarbeitung der Pipeline für maschinelles Lernen mit ML.NET untersuchen können.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: cd229c120f7599c9a304a84a1669947e613fc917
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297587"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a>Untersuchen von Zwischendatenwerten bei der Verarbeitung der Pipeline für maschinelles Lernen mit ML.NET

Während des Experiments sollten Sie die Ergebnisse der Datenverarbeitung zu einem bestimmten Zeitpunkt überwachen und überprüfen. Dies ist nicht einfach, da ML.NET-Vorgänge verzögert sind und Objekte erstellen, die „Datenversprechen“ sind.

Die `GetColumn<T>`-Erweiterungsmethode ermöglicht Ihnen das Untersuchen der Zwischendaten. Gibt die Inhalte einer Datenspalte als ein `IEnumerable` zurück.

Im folgenden Beispiel wird die Verwendung der `GetColumn<T>`-Erweiterungsmethode gezeigt.

[Beispieldatei](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```

Die Definition sieht folgendermaßen aus:

```csharp
private class InspectedRow
{
    public bool IsOver50K;
    public string Workclass;
    public string Education;
    public string MaritalStatus;
    public string[] AllFeatures;
}
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.TextReader(new TextLoader.Arguments
{
    Column = new[] {
        // A boolean column depicting the 'label'.
        new TextLoader.Column("IsOver50K", DataKind.BL, 0),
        // Three text columns.
        new TextLoader.Column("Workclass", DataKind.TX, 1),
        new TextLoader.Column("Education", DataKind.TX, 2),
        new TextLoader.Column("MaritalStatus", DataKind.TX, 3)
    },
    // First line of the file is a header, not a data row.
    HasHeader = true
});

// Start creating our processing pipeline. For now, let's just concatenate all the text columns
// together into one.
var pipeline = mlContext.Transforms.Concatenate("AllFeatures", "Education", "MaritalStatus");

// Let's verify that the data has been read correctly. 
// First, we read the data file.
var data = reader.Read(dataPath);

// Fit our data pipeline and transform data with it.
var transformedData = pipeline.Fit(data).Transform(data);

// 'transformedData' is a 'promise' of data. Let's actually read it.
var someRows = transformedData
    // Convert to an enumerable of user-defined type. 
    .AsEnumerable<InspectedRow>(mlContext, reuseRowObject: false)
    // Take a couple values as an array.
    .Take(4).ToArray();

// Extract the 'AllFeatures' column.
// This will give the entire dataset: make sure to only take several row
// in case the dataset is huge. The is similar to the static API, except
// you have to specify the column name and type.
var featureColumns = transformedData.GetColumn<string[]>(mlContext, "AllFeatures")
    .Take(20).ToArray();
```