---
title: Laden von Daten aus einer Textdateien für die Machine Learning-Verarbeitung – ML.NET
description: Erfahren Sie, wie Sie Daten aus einer Textdatei laden, um mit ML.NET Machine Learning-Modelle zu erstellen, zu trainieren und zu bewerten.
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 70c7ccdeaa27b78a412c2bc82f524d4bf42a740a
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091707"
---
# <a name="load-data-from-a-text-file-for-machine-learning-processing---mlnet"></a><span data-ttu-id="23a9d-103">Laden von Daten aus einer Textdateien für die Machine Learning-Verarbeitung – ML.NET</span><span class="sxs-lookup"><span data-stu-id="23a9d-103">Load data from a text file for machine learning processing - ML.NET</span></span>

<span data-ttu-id="23a9d-104">`TextLoader` wird verwendet, um Daten aus einer Textdatei zu laden.</span><span class="sxs-lookup"><span data-stu-id="23a9d-104">`TextLoader` is used to load data from text files.</span></span> <span data-ttu-id="23a9d-105">Sie müssen die Datenspalten, deren Typen und ihre Position in der Textdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="23a9d-105">You need to specify the data columns, their types, and their location in the text file.</span></span>

<span data-ttu-id="23a9d-106">Beachten Sie, dass es durchaus akzeptabel ist, einige Spalten einer Datei zu lesen oder die gleiche Spalte mehrmals zu lesen.</span><span class="sxs-lookup"><span data-stu-id="23a9d-106">Note that it's perfectly acceptable to read some columns of a file, or read the same column multiple times.</span></span>

<span data-ttu-id="23a9d-107">[Beispieldatei](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="23a9d-107">[Example file](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span></span>

```console
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse
```

<span data-ttu-id="23a9d-108">So laden Sie die Daten aus einer Textdatei:</span><span class="sxs-lookup"><span data-stu-id="23a9d-108">To load the data from a text file:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // A boolean column depicting the 'target label'.
        new TextLoader.Column("IsOver50k",DataKind.BL,0),
        // Three text columns.
        new TextLoader.Column("WorkClass",DataKind.TX,1),
        new TextLoader.Column("Education",DataKind.TX,2),
        new TextLoader.Column("MaritalStatus",DataKind.TX,3)
    },
    hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(dataPath);
```