---
title: Vorbereiten von Daten für die Modellerstellung
description: Erfahren Sie, wie Sie Transformationen in ML.NET verwenden können, um Daten für die weitere Verarbeitung oder die Modellerstellung zu manipulieren und vorzubereiten.
author: luisquintanilla
ms.author: luquinta
ms.date: 01/29/2020
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 12f933253af9ea519d711c20227fe075fed003de
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452986"
---
# <a name="prepare-data-for-building-a-model"></a><span data-ttu-id="91ed2-103">Vorbereiten von Daten für die Modellerstellung</span><span class="sxs-lookup"><span data-stu-id="91ed2-103">Prepare data for building a model</span></span>

<span data-ttu-id="91ed2-104">Erfahren Sie, wie Sie ML.NET verwenden können, um Daten für die weitere Verarbeitung oder die Erstellung eines Modells aufzubereiten.</span><span class="sxs-lookup"><span data-stu-id="91ed2-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="91ed2-105">Die Daten sind oft unsauber und haben eine geringe Dichte.</span><span class="sxs-lookup"><span data-stu-id="91ed2-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="91ed2-106">Für Machine-Learning-Algorithmen in ML.NET sind Eingaben oder Features in einem einzigen numerischen Vektor erforderlich.</span><span class="sxs-lookup"><span data-stu-id="91ed2-106">ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="91ed2-107">Analog dazu muss der Wert, der vorhersagt werden soll (Label), codiert werden. Dies gilt insbesondere für kategorische Daten.</span><span class="sxs-lookup"><span data-stu-id="91ed2-107">Similarly, the value to predict (label), especially when it's categorical data, has to be encoded.</span></span> <span data-ttu-id="91ed2-108">Daher besteht eines der Ziele der Datenaufbereitung darin, die Daten in das von ML.NET-Algorithmen erwartete Format zu bringen.</span><span class="sxs-lookup"><span data-stu-id="91ed2-108">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span>

## <a name="filter-data"></a><span data-ttu-id="91ed2-109">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="91ed2-109">Filter data</span></span>

<span data-ttu-id="91ed2-110">Manchmal sind nicht alle Daten in einem Dataset für die Analyse relevant.</span><span class="sxs-lookup"><span data-stu-id="91ed2-110">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="91ed2-111">Ein Ansatz zur Entfernung irrelevanter Daten ist das Filtern.</span><span class="sxs-lookup"><span data-stu-id="91ed2-111">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="91ed2-112">Der [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) enthält eine Reihe von Filtervorgängen, der eine [`IDataView`](xref:Microsoft.ML.IDataView) mit allen Daten aufnehmen und eine [IDataView](xref:Microsoft.ML.IDataView) zurückgeben kann, die nur die Datenpunkte von Interesse enthält.</span><span class="sxs-lookup"><span data-stu-id="91ed2-112">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="91ed2-113">Es ist wichtig zu beachten, dass Filtervorgänge nicht als Teil einer [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)- oder [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601)-Datenaufbereitungspipeline aufgenommen werden können, da sie kein [`IEstimator`](xref:Microsoft.ML.IEstimator%601) oder [`ITransformer`](xref:Microsoft.ML.ITransformer) wie im [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog) sind.</span><span class="sxs-lookup"><span data-stu-id="91ed2-113">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span>

<span data-ttu-id="91ed2-114">Laden Sie die folgenden Eingabedaten in eine [`IDataView`](xref:Microsoft.ML.IDataView) namens `data`:</span><span class="sxs-lookup"><span data-stu-id="91ed2-114">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

<span data-ttu-id="91ed2-115">Um Daten nach dem Wert einer Spalte zu filtern, verwenden Sie die [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A)-Methode.</span><span class="sxs-lookup"><span data-stu-id="91ed2-115">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="91ed2-116">Das obige Beispiel zeigt Zeilen im Dataset mit einem Preis zwischen 20.0000 und 100.000.000.</span><span class="sxs-lookup"><span data-stu-id="91ed2-116">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="91ed2-117">Das Ergebnis der Anwendung dieses Filters würde nur die letzten beiden Zeilen in den Daten zurückgeben und die erste Zeile ausschließen, da der Preis den Wert 100000 hat und nicht im angegebenen Bereich liegt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-117">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="91ed2-118">Ersetzen fehlender Werte</span><span class="sxs-lookup"><span data-stu-id="91ed2-118">Replace missing values</span></span>

<span data-ttu-id="91ed2-119">Fehlende Werte kommen in Datasets häufig vor.</span><span class="sxs-lookup"><span data-stu-id="91ed2-119">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="91ed2-120">Ein Ansatz für den Umgang mit fehlenden Daten, besteht darin, sie durch den Standardwert für den gegebenen Typ zu ersetzen, falls vorhanden, oder durch einen anderen sinnvollen Wert, wie beispielsweise den Mittelwert der Daten.</span><span class="sxs-lookup"><span data-stu-id="91ed2-120">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span>

<span data-ttu-id="91ed2-121">Laden Sie die folgenden Eingabedaten in eine [`IDataView`](xref:Microsoft.ML.IDataView) namens `data`:</span><span class="sxs-lookup"><span data-stu-id="91ed2-121">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=float.NaN
    }
};
```

<span data-ttu-id="91ed2-122">Beachten Sie, dass im letzten Element in unserer Liste ein Wert für `Price` fehlt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-122">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="91ed2-123">Um die fehlenden Werte in der `Price`-Spalte zu ersetzen, verwenden Sie die -Methode [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A), um diesen fehlenden Wert einzugeben.</span><span class="sxs-lookup"><span data-stu-id="91ed2-123">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91ed2-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) funktioniert nur mit numerischen Daten.</span><span class="sxs-lookup"><span data-stu-id="91ed2-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="91ed2-125">ML.NET unterstützt verschiedene [Ersetzungsmodi](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span><span class="sxs-lookup"><span data-stu-id="91ed2-125">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="91ed2-126">Das obige Beispiel verwendet den Ersetzungsmodus `Mean`, der den fehlenden Wert mit dem Durchschnittswert dieser Spalte auffüllt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-126">The sample above uses the `Mean` replacement mode, which fills in the missing value with that column's average value.</span></span> <span data-ttu-id="91ed2-127">Das Ergebnis der Ersetzung trägt für die `Price`-Eigenschaft für das letzte Element in unseren Daten mit 200.000 ein, da dies der Durchschnitt von 100.000 und 300.000 ist.</span><span class="sxs-lookup"><span data-stu-id="91ed2-127">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span>

## <a name="use-normalizers"></a><span data-ttu-id="91ed2-128">Verwenden von Normalisierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="91ed2-128">Use normalizers</span></span>

<span data-ttu-id="91ed2-129">[Normalisierung](https://en.wikipedia.org/wiki/Feature_scaling) ist eine Datenvorverarbeitungstechnik, die verwendet wird, um Features so zu skalieren, dass sie sich im gleichen Bereich, normalerweise zwischen 0 und 1, befinden, damit sie von einem Algorithmus für maschinelles Lernen präziser verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="91ed2-129">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to scale features to be in the same range, usually between 0 and 1, so that they can be more accurately processed by a machine learning algorithm.</span></span> <span data-ttu-id="91ed2-130">So variieren beispielsweise die Bereiche für Alter und Einkommen stark, wobei das Alter im Allgemeinen im Bereich von 0-100 und das Einkommen im Allgemeinen im Bereich von 0 bis x-Tausende liegt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-130">For example, the ranges for age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="91ed2-131">Eine detailliertere Liste und Beschreibung der Normalisierungstransformationen finden Sie auf der Seite zu [Datentransformationen](../resources/transforms.md).</span><span class="sxs-lookup"><span data-stu-id="91ed2-131">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span>

### <a name="min-max-normalization"></a><span data-ttu-id="91ed2-132">Min-Max-Normalisierung</span><span class="sxs-lookup"><span data-stu-id="91ed2-132">Min-Max normalization</span></span>

<span data-ttu-id="91ed2-133">Laden Sie die folgenden Eingabedaten in eine [`IDataView`](xref:Microsoft.ML.IDataView) namens `data`:</span><span class="sxs-lookup"><span data-stu-id="91ed2-133">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms = 2f,
        Price = 200000f
    },
    new HomeData
    {
        NumberOfBedrooms = 1f,
        Price = 100000f
    }
};
```

<span data-ttu-id="91ed2-134">Auf Spalten mit einzelnen numerischen Werten sowie auf Vektoren kann Normalisierung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="91ed2-134">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="91ed2-135">Verwenden Sie die Min-Max-Normalisierung mit der [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A)-Methode, um die Daten in der Spalte `Price` zu normalisieren.</span><span class="sxs-lookup"><span data-stu-id="91ed2-135">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="91ed2-136">Die ursprünglichen Preiswerte `[200000,100000]` werden unter Verwendung der Normalisierungsformel `MinMax` in `[ 1, 0.5 ]` umgewandelt, wodurch Ausgabewerte im Bereich von 0 bis 1 generiert werden.</span><span class="sxs-lookup"><span data-stu-id="91ed2-136">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula that generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="91ed2-137">Quantisierung</span><span class="sxs-lookup"><span data-stu-id="91ed2-137">Binning</span></span>

<span data-ttu-id="91ed2-138">Die [Quantisierung](https://en.wikipedia.org/wiki/Data_binning) konvertiert kontinuierliche Werte in eine diskrete Darstellung der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="91ed2-138">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="91ed2-139">Nehmen wir beispielsweise an, dass eines Ihrer Features das Alter ist.</span><span class="sxs-lookup"><span data-stu-id="91ed2-139">For example, suppose one of your features is age.</span></span> <span data-ttu-id="91ed2-140">Anstatt den tatsächlichen Alterswert zu verwenden, werden durch die Quantisierung Bereiche für diesen Wert erstellt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-140">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="91ed2-141">0 bis 18 könnte dabei einer der Bereiche sein, ein anderer könnte 19 bis 35 sein usw.</span><span class="sxs-lookup"><span data-stu-id="91ed2-141">0-18 could be one bin, another could be 19-35 and so on.</span></span>

<span data-ttu-id="91ed2-142">Laden Sie die folgenden Eingabedaten in eine [`IDataView`](xref:Microsoft.ML.IDataView) namens `data`:</span><span class="sxs-lookup"><span data-stu-id="91ed2-142">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

<span data-ttu-id="91ed2-143">Normalisieren Sie die Daten mit der [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A)-Methode in Bereiche.</span><span class="sxs-lookup"><span data-stu-id="91ed2-143">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A) method.</span></span> <span data-ttu-id="91ed2-144">Mit dem `maximumBinCount`-Parameter können Sie die Anzahl der Bereiche angeben, die zur Klassifizierung Ihrer Daten benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="91ed2-144">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="91ed2-145">In diesem Beispiel werden Daten in zwei Bereiche aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-145">In this example, data will be put into two bins.</span></span>

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="91ed2-146">Durch die Quantisierung werden Bereichsbegrenzungen von `[0,200000,Infinity]` erstellt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-146">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="91ed2-147">Daher sind die resultierenden Bereiche `[0,1,1]`, weil die erste beobachteten Werte zwischen 0 und 200.000 liegen und die anderen größer als 200.000, aber kleiner als unendlich sind.</span><span class="sxs-lookup"><span data-stu-id="91ed2-147">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="91ed2-148">Arbeiten mit Kategoriedaten</span><span class="sxs-lookup"><span data-stu-id="91ed2-148">Work with categorical data</span></span>

<span data-ttu-id="91ed2-149">Einer der gängigsten Datentypen sind Kategoriedaten.</span><span class="sxs-lookup"><span data-stu-id="91ed2-149">One of the most common types of data is categorical data.</span></span> <span data-ttu-id="91ed2-150">Kategoriedaten zeichnen sich durch eine begrenzte Anzahl von Kategorien aus.</span><span class="sxs-lookup"><span data-stu-id="91ed2-150">Categorical data has a finite number of categories.</span></span> <span data-ttu-id="91ed2-151">Beispiele sind die Bundesstaaten der USA oder eine Liste der Tierarten, die in einer Reihe von Bildern gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="91ed2-151">For example, the states of the USA, or a list of the types of animals found in a set of pictures.</span></span> <span data-ttu-id="91ed2-152">Unabhängig davon, ob es sich bei den Kategoriedaten um Features oder Beschriftungen handelt, müssen sie einem numerischen Wert zugeordnet werden, damit sie zur Erzeugung eines Machine Learning-Modells verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="91ed2-152">Whether the categorical data are features or labels, they must be mapped onto a numerical value so they can be used to generate a machine learning model.</span></span> <span data-ttu-id="91ed2-153">Es gibt je nach dem zu lösenden Problem eine Reihe von Möglichkeiten, in ML.NET mit Kategoriedaten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="91ed2-153">There are a number of ways of working with categorical data in ML.NET, depending on the problem you are solving.</span></span>

### <a name="key-value-mapping"></a><span data-ttu-id="91ed2-154">Schlüsselwertzuordnung</span><span class="sxs-lookup"><span data-stu-id="91ed2-154">Key value mapping</span></span>

<span data-ttu-id="91ed2-155">In ML.NET ist ein Schlüssel ein ganzzahliger Wert, der eine Kategorie darstellt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-155">In ML.NET, a key is an integer value that represents a category.</span></span> <span data-ttu-id="91ed2-156">Die Schlüsselwertzuordnung kommt meist zum Einsatz, um Zeichenfolgenbeschriftungen für das Training eindeutigen ganzzahligen Werten und dann wieder ihren Zeichenfolgenwerten zuzuordnen, sobald das Modell zum Erstellen einer Vorhersage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="91ed2-156">Key value mapping is most often used to map string labels into unique integer values for training, then back to their string values when the model is used to make a prediction.</span></span>

<span data-ttu-id="91ed2-157">Die für die Schlüsselwertzuordnung verwendeten Transformationen sind [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) und [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).</span><span class="sxs-lookup"><span data-stu-id="91ed2-157">The transforms used to perform key value mapping are [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) and [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).</span></span>

<span data-ttu-id="91ed2-158">`MapValueToKey` fügt ein Wörterbuch von Zuordnungen im Modell hinzu, sodass `MapKeyToValue` bei der Erstellung einer Vorhersage die Rücktransformation vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="91ed2-158">`MapValueToKey` adds a dictionary of mappings in the model, so that `MapKeyToValue` can perform the reverse transform when making a prediction.</span></span>

### <a name="one-hot-encoding"></a><span data-ttu-id="91ed2-159">1-aus-n-Code</span><span class="sxs-lookup"><span data-stu-id="91ed2-159">One hot encoding</span></span>

<span data-ttu-id="91ed2-160">1-aus-n-Code verwendet eine endliche Menge von Werten und ordnet sie ganzen Zahlen zu, deren binäre Darstellung einen einzigen `1`-Wert an eindeutigen Positionen in der Zeichenfolge aufweist.</span><span class="sxs-lookup"><span data-stu-id="91ed2-160">One hot encoding takes a finite set of values and maps them onto integers whose binary representation has a single `1` value in unique positions in the string.</span></span> <span data-ttu-id="91ed2-161">1-aus-n-Code kann die beste Wahl sein, wenn es keine implizite Reihenfolge der Kategoriedaten gibt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-161">One hot encoding can be the best choice if there is no implicit ordering of the categorical data.</span></span> <span data-ttu-id="91ed2-162">In der folgenden Tabelle wird ein Beispiel mit Postleitzahlen als Rohwerte gezeigt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-162">The following table shows an example with zip codes as raw values.</span></span>

|<span data-ttu-id="91ed2-163">Rohwert</span><span class="sxs-lookup"><span data-stu-id="91ed2-163">Raw value</span></span>|<span data-ttu-id="91ed2-164">1-aus-n-Code-Wert</span><span class="sxs-lookup"><span data-stu-id="91ed2-164">One hot encoded value</span></span>|
|---------|---------------------|
|<span data-ttu-id="91ed2-165">98052</span><span class="sxs-lookup"><span data-stu-id="91ed2-165">98052</span></span>|<span data-ttu-id="91ed2-166">00...01</span><span class="sxs-lookup"><span data-stu-id="91ed2-166">00...01</span></span>|
|<span data-ttu-id="91ed2-167">98100</span><span class="sxs-lookup"><span data-stu-id="91ed2-167">98100</span></span>|<span data-ttu-id="91ed2-168">00...10</span><span class="sxs-lookup"><span data-stu-id="91ed2-168">00...10</span></span>|
|<span data-ttu-id="91ed2-169">...</span><span class="sxs-lookup"><span data-stu-id="91ed2-169">...</span></span>|<span data-ttu-id="91ed2-170">...</span><span class="sxs-lookup"><span data-stu-id="91ed2-170">...</span></span>|
|<span data-ttu-id="91ed2-171">98109</span><span class="sxs-lookup"><span data-stu-id="91ed2-171">98109</span></span>|<span data-ttu-id="91ed2-172">10...00</span><span class="sxs-lookup"><span data-stu-id="91ed2-172">10...00</span></span>|

<span data-ttu-id="91ed2-173">Die Transformation zum Konvertieren von Kategoriedaten in1-aus-n-Code-Zahlen ist [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).</span><span class="sxs-lookup"><span data-stu-id="91ed2-173">The transform to convert categorical data to one-hot encoded numbers is [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).</span></span>

### <a name="hashing"></a><span data-ttu-id="91ed2-174">Hashing</span><span class="sxs-lookup"><span data-stu-id="91ed2-174">Hashing</span></span>

<span data-ttu-id="91ed2-175">Hashing ist eine weitere Möglichkeit, um Kategoriedaten in Zahlen umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="91ed2-175">Hashing is another way to convert categorical data to numbers.</span></span> <span data-ttu-id="91ed2-176">Eine Hashfunktion ordnet Daten beliebiger Größe (z. B. eine Textzeichenfolge) einer Zahl mit einem festen Bereich zu.</span><span class="sxs-lookup"><span data-stu-id="91ed2-176">A hash function maps data of an arbitrary size (a string of text for example) onto a number with a fixed range.</span></span> <span data-ttu-id="91ed2-177">Hashing kann eine schnelle und speichereffiziente Methode zur Vektorisierung von Features sein.</span><span class="sxs-lookup"><span data-stu-id="91ed2-177">Hashing can be a fast and space-efficient way of vectorizing features.</span></span> <span data-ttu-id="91ed2-178">Ein nennenswertes Beispiel für Hashing beim maschinellen Lernen sind E-Mail-Spamfilter, bei denen anstelle eines Wörterbuchs bekannter Wörter jedes Wort in der E-Mail gehasht und zu einem großen Featurevektor hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="91ed2-178">One notable example of hashing in machine learning is email spam filtering where, instead of maintaining a dictionary of known words, every word in the email is hashed and added to a large feature vector.</span></span> <span data-ttu-id="91ed2-179">Durch den Einsatz von Hashing wird das Problem der Umgehung des Spamfilters durch die Verwendung von Wörtern vermieden, die nicht im Wörterbuch stehen.</span><span class="sxs-lookup"><span data-stu-id="91ed2-179">Using hashing in this way avoids the problem of malicious spam filtering circumvention by the use of words that are not in the dictionary.</span></span>

<span data-ttu-id="91ed2-180">ML.NET bietet eine [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A)-Transformation zur Durchführung des Hashings für Text, Datumsangaben und numerische Daten.</span><span class="sxs-lookup"><span data-stu-id="91ed2-180">ML.NET provides [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) transform to perform hashing on text, dates, and numerical data.</span></span> <span data-ttu-id="91ed2-181">Wie bei der Schlüsselwertzuordnung sind die Ausgaben der Hashtransformation Schlüsseltypen.</span><span class="sxs-lookup"><span data-stu-id="91ed2-181">Like value key mapping, the outputs of the hash transform are key types.</span></span>

## <a name="work-with-text-data"></a><span data-ttu-id="91ed2-182">Arbeiten mit Textdaten</span><span class="sxs-lookup"><span data-stu-id="91ed2-182">Work with text data</span></span>

<span data-ttu-id="91ed2-183">Wie Kategoriedaten müssen Textdaten in numerische Features umgewandelt werden, bevor sie zum Erstellen eines Machine Learning-Modells verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="91ed2-183">Like categorical data, text data needs to be transformed into numerical features before using it to build a machine learning model.</span></span> <span data-ttu-id="91ed2-184">Eine detailliertere Liste und Beschreibung der Texttransformationen finden Sie auf der Seite zu [Datentransformationen](../resources/transforms.md).</span><span class="sxs-lookup"><span data-stu-id="91ed2-184">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="91ed2-185">Verwenden Sie Daten wie die Daten unten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen wurden:</span><span class="sxs-lookup"><span data-stu-id="91ed2-185">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
ReviewData[] reviews = new ReviewData[]
{
    new ReviewData
    {
        Description="This is a good product",
        Rating=4.7f
    },
    new ReviewData
    {
        Description="This is a bad product",
        Rating=2.3f
    }
};
```

<span data-ttu-id="91ed2-186">ML.NET bietet die [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A)-Transformation, die den Zeichenfolgenwert eines Texts verwendet und durch Anwenden einer Reihe einzelner Transformationen eine Reihe von Features anhand des Texts erstellt.</span><span class="sxs-lookup"><span data-stu-id="91ed2-186">ML.NET provides the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) transform that takes a text's string value and creates a set of features from the text, by applying a series of individual transforms.</span></span>

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="91ed2-187">Die resultierende Transformation konvertiert die Textwerte in der Spalte `Description` in einen numerischen Vektor, der der folgenden Ausgabe ähnelt:</span><span class="sxs-lookup"><span data-stu-id="91ed2-187">The resulting transform converts the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="91ed2-188">Die Transformationen, aus denen sich `FeaturizeText` zusammensetzt, können auch für eine präzisere Steuerung der Generierung von Features einzeln angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="91ed2-188">The transforms that make up `FeaturizeText` can also be applied individually for finer grain control over feature generation.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="91ed2-189">`textEstimator` enthält eine Teilmenge von Vorgängen, die von der [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A)-Methode durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="91ed2-189">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) method.</span></span> <span data-ttu-id="91ed2-190">Der Vorteil einer komplexeren Pipeline ist die Steuerung und Sichtbarkeit hinsichtlich der Transformationen, die für die Daten durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="91ed2-190">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span>

<span data-ttu-id="91ed2-191">Im Folgenden finden Sie am Beispiel des ersten Eintrags eine detaillierte Beschreibung der Ergebnisse, die durch die vom `textEstimator` definierten Transformationsschritte generiert wurden:</span><span class="sxs-lookup"><span data-stu-id="91ed2-191">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="91ed2-192">**Ursprünglicher Text: Das ist ein gutes Produkt**</span><span class="sxs-lookup"><span data-stu-id="91ed2-192">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="91ed2-193">Transformation</span><span class="sxs-lookup"><span data-stu-id="91ed2-193">Transform</span></span> | <span data-ttu-id="91ed2-194">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91ed2-194">Description</span></span> | <span data-ttu-id="91ed2-195">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="91ed2-195">Result</span></span>
|--|--|--|
|<span data-ttu-id="91ed2-196">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="91ed2-196">1. NormalizeText</span></span> | <span data-ttu-id="91ed2-197">Konvertiert standardmäßig alle Buchstaben in Kleinbuchstaben</span><span class="sxs-lookup"><span data-stu-id="91ed2-197">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="91ed2-198">das ist ein gutes produkt</span><span class="sxs-lookup"><span data-stu-id="91ed2-198">this is a good product</span></span>
|<span data-ttu-id="91ed2-199">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="91ed2-199">2. TokenizeWords</span></span> | <span data-ttu-id="91ed2-200">Teilt die Zeichenfolge in einzelne Wörter auf</span><span class="sxs-lookup"><span data-stu-id="91ed2-200">Splits string into individual words</span></span> | <span data-ttu-id="91ed2-201">[„das“, „ist“, „ein“, „gutes“, „produkt“]</span><span class="sxs-lookup"><span data-stu-id="91ed2-201">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="91ed2-202">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="91ed2-202">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="91ed2-203">Entfernt die Stoppwörter wie *ist* und *ein*.</span><span class="sxs-lookup"><span data-stu-id="91ed2-203">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="91ed2-204">[„gutes“, „produkt“]</span><span class="sxs-lookup"><span data-stu-id="91ed2-204">["good","product"]</span></span>
|<span data-ttu-id="91ed2-205">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="91ed2-205">4. MapValueToKey</span></span> | <span data-ttu-id="91ed2-206">Ordnet die Werte den Schlüsseln (Kategorien) basierend auf den Eingabedaten zu</span><span class="sxs-lookup"><span data-stu-id="91ed2-206">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="91ed2-207">[1,2]</span><span class="sxs-lookup"><span data-stu-id="91ed2-207">[1,2]</span></span>
|<span data-ttu-id="91ed2-208">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="91ed2-208">5. ProduceNGrams</span></span> | <span data-ttu-id="91ed2-209">Transformiert Text in eine Folge von aufeinander folgenden Wörtern</span><span class="sxs-lookup"><span data-stu-id="91ed2-209">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="91ed2-210">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="91ed2-210">[1,1,1,0,0]</span></span>
|<span data-ttu-id="91ed2-211">6. NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="91ed2-211">6. NormalizeLpNorm</span></span> | <span data-ttu-id="91ed2-212">Skaliert Eingaben durch ihre Lp-Norm</span><span class="sxs-lookup"><span data-stu-id="91ed2-212">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="91ed2-213">[ 0,577350529, 0,577350529, 0,577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="91ed2-213">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
