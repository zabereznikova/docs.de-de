---
title: 'Trainieren eines Machine Learning-Modells mithilfe von Daten, die nicht in einer Textdatei enthalten sind: ML.NET'
description: Erfahren Sie, wie Sie ML.NET verwenden, um als Teil der Vorhersagepipeline Trainingsdaten, die nicht in einer Datei gespeichert sind, für Machine Learning-Modelle zu laden.
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 971c5c62acc9dd7bf29aa11ce898c2b76822c3d7
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/30/2018
ms.locfileid: "52672081"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a><span data-ttu-id="e0e19-103">Trainieren eines Machine Learning-Modells mithilfe von Daten, die nicht in einer Textdatei enthalten sind: ML.NET</span><span class="sxs-lookup"><span data-stu-id="e0e19-103">Train a machine learning model with data that's not in a text file - ML.NET</span></span>

<span data-ttu-id="e0e19-104">Häufig wird das `TextLoader`-Element verwendet, um die Trainingsdaten aus einer Datei zu lesen. Dabei handelt es sich um den Anwendungsfall, der in der Regel für ML.NET veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="e0e19-104">The commonly demonstrated use case for ML.NET is use the `TextLoader` to read the training data from a file.</span></span>
<span data-ttu-id="e0e19-105">In Trainingsszenarios in Echtzeit können sich die Daten allerdings auch an anderen Orten befinden. Z. B.:</span><span class="sxs-lookup"><span data-stu-id="e0e19-105">However, in real-time training scenarios the data can be elsewhere, such as:</span></span>

* <span data-ttu-id="e0e19-106">Sie können in SQL Tabellen gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="e0e19-106">in SQL tables</span></span>
* <span data-ttu-id="e0e19-107">Sie können aus Protokolldateien extrahiert worden sein.</span><span class="sxs-lookup"><span data-stu-id="e0e19-107">extracted from log files</span></span>
* <span data-ttu-id="e0e19-108">Sie können spontan erstellt worden sein.</span><span class="sxs-lookup"><span data-stu-id="e0e19-108">generated on the fly</span></span>

<span data-ttu-id="e0e19-109">Verwenden Sie [Schemaverständnis](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md), um ein bereits vorhandenes `IEnumerable`-Objekt für C# als `DataView` in ML.NET zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="e0e19-109">Use [schema comprehension](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) to bring an existing C# `IEnumerable` into ML.NET as a `DataView`.</span></span>

<span data-ttu-id="e0e19-110">Anhand dieses Beispiels erfahren Sie, wie Sie ein Vorhersagemodell für Änderungen durch die Kunden erstellen und die folgenden Features aus Ihrem Produktionssystem extrahieren:</span><span class="sxs-lookup"><span data-stu-id="e0e19-110">For this example, you'll build the customer churn prediction model, and extract the following features from your production system:</span></span>

* <span data-ttu-id="e0e19-111">Kunden-ID (wird vom Modell ignoriert)</span><span class="sxs-lookup"><span data-stu-id="e0e19-111">Customer ID (ignored by the model)</span></span>
* <span data-ttu-id="e0e19-112">Angabe, ob der Kunde eine Änderung vorgenommen hat (die Zielbezeichnung)</span><span class="sxs-lookup"><span data-stu-id="e0e19-112">Whether the customer has churned (the target 'label')</span></span>
* <span data-ttu-id="e0e19-113">Die demografische Kategorie (eine Zeichenfolge wie „junge Erwachsene“)</span><span class="sxs-lookup"><span data-stu-id="e0e19-113">The 'demographic category' (one string, like 'young adult' etc.)</span></span>
* <span data-ttu-id="e0e19-114">Die Anzahl der Besuche in den letzten 5 Tagen.</span><span class="sxs-lookup"><span data-stu-id="e0e19-114">The number of visits from the last 5 days.</span></span>

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

<span data-ttu-id="e0e19-115">Laden Sie diese Daten in das `DataView`, und trainieren Sie das Modell mithilfe des folgenden Codes:</span><span class="sxs-lookup"><span data-stu-id="e0e19-115">Load this data into the `DataView` and train the model, using the following code:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.CreateStreamingDataView(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
