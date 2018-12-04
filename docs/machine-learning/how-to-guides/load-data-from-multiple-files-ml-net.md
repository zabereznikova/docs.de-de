---
title: 'Laden von Daten aus mehreren Dateien für Machine Learning-Prozesse: ML.NET'
description: Erfahren Sie, wie Sie Daten aus mehreren Dateien laden, um mit ML.NET Machine Learning-Modelle zu erstellen, zu trainieren und zu bewerten.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: c9b34bd6bcbac62e9f9c33226f5d0feb41168392
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/30/2018
ms.locfileid: "52672404"
---
# <a name="load-data-from-multiple-files-for-machine-learning-processing---mlnet"></a><span data-ttu-id="a521d-103">Laden von Daten aus mehreren Dateien für Machine Learning-Prozesse: ML.NET</span><span class="sxs-lookup"><span data-stu-id="a521d-103">Load data from multiple files for machine learning processing - ML.NET</span></span>

<span data-ttu-id="a521d-104">Verwenden Sie den `TextLoader`, und geben Sie ein Array von Dateien für die `Read`-Methode an.</span><span class="sxs-lookup"><span data-stu-id="a521d-104">Use the `TextLoader`, and specify an array of files to the `Read` method.</span></span> <span data-ttu-id="a521d-105">Die Dateien müssen dasselbe Schema aufweisen (dieselbe Nummer und dieselben Spaltenarten):</span><span class="sxs-lookup"><span data-stu-id="a521d-105">The files must have the same schema (same number and type of columns):</span></span>

* [<span data-ttu-id="a521d-106">Beispieldatei1</span><span class="sxs-lookup"><span data-stu-id="a521d-106">Example file1</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.train)
* [<span data-ttu-id="a521d-107">Beispieldatei2</span><span class="sxs-lookup"><span data-stu-id="a521d-107">Example file2</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.test)

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.TextReader(new TextLoader.Arguments
{
    Column = new[] {
        // A boolean column depicting the 'label'.
        new TextLoader.Column("IsOver50k", DataKind.BL, 0),
        // Three text columns.
        new TextLoader.Column("Workclass", DataKind.TX, 1),
        new TextLoader.Column("Education", DataKind.TX, 2),
        new TextLoader.Column("MaritalStatus", DataKind.TX, 3)
    },
    // First line of the file is a header, not a data row.
    HasHeader = true
});

var data = reader.Read(exampleFile1, exampleFile2);
```