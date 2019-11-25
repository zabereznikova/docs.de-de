---
title: Vorbereiten von Daten für die Modellerstellung
description: Erfahren Sie, wie Sie Transformationen in ML.NET verwenden können, um Daten für die weitere Verarbeitung oder die Modellerstellung zu manipulieren und vorzubereiten.
author: luisquintanilla
ms.author: luquinta
ms.date: 09/11/2019
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: e9bfad4724b353b0f3bfc615a40f1d72b80a2cd4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976978"
---
# <a name="prepare-data-for-building-a-model"></a><span data-ttu-id="708fc-103">Vorbereiten von Daten für die Modellerstellung</span><span class="sxs-lookup"><span data-stu-id="708fc-103">Prepare data for building a model</span></span>

<span data-ttu-id="708fc-104">Erfahren Sie, wie Sie ML.NET verwenden können, um Daten für die weitere Verarbeitung oder die Erstellung eines Modells aufzubereiten.</span><span class="sxs-lookup"><span data-stu-id="708fc-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="708fc-105">Die Daten sind oft unsauber und haben eine geringe Dichte.</span><span class="sxs-lookup"><span data-stu-id="708fc-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="708fc-106">Für Machine-Learning-Algorithmen in ML.NET sind Eingaben oder Features in einem einzigen numerischen Vektor erforderlich.</span><span class="sxs-lookup"><span data-stu-id="708fc-106">ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="708fc-107">Analog dazu muss der Wert, der vorhersagt werden soll (Label), codiert werden. Dies gilt insbesondere für kategorische Daten.</span><span class="sxs-lookup"><span data-stu-id="708fc-107">Similarly, the value to predict (label), especially when it's categorical data, has to be encoded.</span></span> <span data-ttu-id="708fc-108">Daher besteht eines der Ziele der Datenaufbereitung darin, die Daten in das von ML.NET-Algorithmen erwartete Format zu bringen.</span><span class="sxs-lookup"><span data-stu-id="708fc-108">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span>

## <a name="filter-data"></a><span data-ttu-id="708fc-109">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="708fc-109">Filter data</span></span>

<span data-ttu-id="708fc-110">Manchmal sind nicht alle Daten in einem Dataset für die Analyse relevant.</span><span class="sxs-lookup"><span data-stu-id="708fc-110">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="708fc-111">Ein Ansatz zur Entfernung irrelevanter Daten ist das Filtern.</span><span class="sxs-lookup"><span data-stu-id="708fc-111">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="708fc-112">Der [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) enthält eine Reihe von Filtervorgängen, der eine [`IDataView`](xref:Microsoft.ML.IDataView) mit allen Daten aufnehmen und eine [IDataView](xref:Microsoft.ML.IDataView) zurückgeben kann, die nur die Datenpunkte von Interesse enthält.</span><span class="sxs-lookup"><span data-stu-id="708fc-112">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="708fc-113">Es ist wichtig zu beachten, dass Filtervorgänge nicht als Teil einer [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)- oder [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601)-Datenaufbereitungspipeline aufgenommen werden können, da sie kein [`IEstimator`](xref:Microsoft.ML.IEstimator%601) oder [`ITransformer`](xref:Microsoft.ML.ITransformer) wie im [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog) sind.</span><span class="sxs-lookup"><span data-stu-id="708fc-113">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span>

<span data-ttu-id="708fc-114">Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:</span><span class="sxs-lookup"><span data-stu-id="708fc-114">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="708fc-115">Um Daten nach dem Wert einer Spalte zu filtern, verwenden Sie die [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*)-Methode.</span><span class="sxs-lookup"><span data-stu-id="708fc-115">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="708fc-116">Das obige Beispiel zeigt Zeilen im Dataset mit einem Preis zwischen 20.0000 und 100.000.000.</span><span class="sxs-lookup"><span data-stu-id="708fc-116">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="708fc-117">Das Ergebnis der Anwendung dieses Filters würde nur die letzten beiden Zeilen in den Daten zurückgeben und die erste Zeile ausschließen, da der Preis den Wert 100000 hat und nicht im angegebenen Bereich liegt.</span><span class="sxs-lookup"><span data-stu-id="708fc-117">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="708fc-118">Ersetzen fehlender Werte</span><span class="sxs-lookup"><span data-stu-id="708fc-118">Replace missing values</span></span>

<span data-ttu-id="708fc-119">Fehlende Werte kommen in Datasets häufig vor.</span><span class="sxs-lookup"><span data-stu-id="708fc-119">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="708fc-120">Ein Ansatz für den Umgang mit fehlenden Daten, besteht darin, sie durch den Standardwert für den gegebenen Typ zu ersetzen, falls vorhanden, oder durch einen anderen sinnvollen Wert, wie beispielsweise den Mittelwert der Daten.</span><span class="sxs-lookup"><span data-stu-id="708fc-120">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span>

<span data-ttu-id="708fc-121">Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:</span><span class="sxs-lookup"><span data-stu-id="708fc-121">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="708fc-122">Beachten Sie, dass im letzten Element in unserer Liste ein Wert für `Price` fehlt.</span><span class="sxs-lookup"><span data-stu-id="708fc-122">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="708fc-123">Um die fehlenden Werte in der `Price`-Spalte zu ersetzen, verwenden Sie die -Methode [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*), um diesen fehlenden Wert einzugeben.</span><span class="sxs-lookup"><span data-stu-id="708fc-123">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="708fc-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) funktioniert nur mit numerischen Daten.</span><span class="sxs-lookup"><span data-stu-id="708fc-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="708fc-125">ML.NET unterstützt verschiedene [Ersetzungsmodi](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span><span class="sxs-lookup"><span data-stu-id="708fc-125">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="708fc-126">Das obige Beispiel verwendet den `Mean`-Ersetzungsmodus, der den fehlenden Wert mit dem Durchschnittswert dieser Spalte ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="708fc-126">The sample above uses the `Mean` replacement mode which will fill in the missing value with that column's average value.</span></span> <span data-ttu-id="708fc-127">Das Ergebnis der Ersetzung trägt für die `Price`-Eigenschaft für das letzte Element in unseren Daten mit 200.000 ein, da dies der Durchschnitt von 100.000 und 300.000 ist.</span><span class="sxs-lookup"><span data-stu-id="708fc-127">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span>

## <a name="use-normalizers"></a><span data-ttu-id="708fc-128">Verwenden von Normalisierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="708fc-128">Use normalizers</span></span>

<span data-ttu-id="708fc-129">Die [Normalisierung](https://en.wikipedia.org/wiki/Feature_scaling) ist eine Datenvorverarbeitungstechnik, die verwendet wird, um Features zu standardisieren, die nicht in der gleichen Größenordnung liegen. Da können Algorithmen schneller konvergieren.</span><span class="sxs-lookup"><span data-stu-id="708fc-129">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to standardize features that are not on the same scale which helps algorithms converge faster.</span></span> <span data-ttu-id="708fc-130">So variieren beispielsweise die Bereiche für Werte wie Alter und Einkommen stark, wobei das Alter im Allgemeinen im Bereich von 0-100 und das Einkommen im Allgemeinen im Bereich von Null bis Tausend liegt.</span><span class="sxs-lookup"><span data-stu-id="708fc-130">For example, the ranges for values like age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="708fc-131">Eine detailliertere Liste und Beschreibung der Normalisierungstransformationen finden Sie auf der Seite zu [Datentransformationen](../resources/transforms.md).</span><span class="sxs-lookup"><span data-stu-id="708fc-131">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span>

### <a name="min-max-normalization"></a><span data-ttu-id="708fc-132">Min-Max-Normalisierung</span><span class="sxs-lookup"><span data-stu-id="708fc-132">Min-Max normalization</span></span>

<span data-ttu-id="708fc-133">Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:</span><span class="sxs-lookup"><span data-stu-id="708fc-133">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="708fc-134">Auf Spalten mit einzelnen numerischen Werten sowie auf Vektoren kann Normalisierung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="708fc-134">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="708fc-135">Verwenden Sie die Min-Max-Normalisierung mit der [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*)-Methode, um die Daten in der Spalte `Price` zu normalisieren.</span><span class="sxs-lookup"><span data-stu-id="708fc-135">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="708fc-136">Die ursprünglichen Preiswerte `[200000,100000]` werden unter Verwendung der Normalisierungsformel `MinMax` in `[ 1, 0.5 ]` umgewandelt, wodurch Ausgabewerte im Bereich von 0-1 generiert werden.</span><span class="sxs-lookup"><span data-stu-id="708fc-136">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula which generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="708fc-137">Quantisierung</span><span class="sxs-lookup"><span data-stu-id="708fc-137">Binning</span></span>

<span data-ttu-id="708fc-138">Die [Quantisierung](https://en.wikipedia.org/wiki/Data_binning) konvertiert kontinuierliche Werte in eine diskrete Darstellung der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="708fc-138">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="708fc-139">Nehmen wir beispielsweise an, dass eines Ihrer Features das Alter ist.</span><span class="sxs-lookup"><span data-stu-id="708fc-139">For example, suppose one of your features is age.</span></span> <span data-ttu-id="708fc-140">Anstatt den tatsächlichen Alterswert zu verwenden, werden durch die Quantisierung Bereiche für diesen Wert erstellt.</span><span class="sxs-lookup"><span data-stu-id="708fc-140">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="708fc-141">0 bis 18 könnte dabei einer der Bereiche sein, ein anderer könnte 19 bis 35 sein usw.</span><span class="sxs-lookup"><span data-stu-id="708fc-141">0-18 could be one bin, another could be 19-35 and so on.</span></span>

<span data-ttu-id="708fc-142">Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:</span><span class="sxs-lookup"><span data-stu-id="708fc-142">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="708fc-143">Normalisieren Sie die Daten mit der [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*)-Methode in Bereiche.</span><span class="sxs-lookup"><span data-stu-id="708fc-143">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) method.</span></span> <span data-ttu-id="708fc-144">Mit dem `maximumBinCount`-Parameter können Sie die Anzahl der Bereiche angeben, die zur Klassifizierung Ihrer Daten benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="708fc-144">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="708fc-145">In diesem Beispiel werden Daten in zwei Bereiche aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="708fc-145">In this example, data will be put into two bins.</span></span>

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="708fc-146">Durch die Quantisierung werden Bereichsbegrenzungen von `[0,200000,Infinity]` erstellt.</span><span class="sxs-lookup"><span data-stu-id="708fc-146">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="708fc-147">Daher sind die resultierenden Bereiche `[0,1,1]`, weil die erste beobachteten Werte zwischen 0 und 200.000 liegen und die anderen größer als 200.000, aber kleiner als unendlich sind.</span><span class="sxs-lookup"><span data-stu-id="708fc-147">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="708fc-148">Arbeiten mit Kategoriedaten</span><span class="sxs-lookup"><span data-stu-id="708fc-148">Work with categorical data</span></span>

<span data-ttu-id="708fc-149">Nicht-numerische Kategoriedaten müssen in eine Zahl umgewandelt werden, bevor sie zum Erstellen eines Machine Learning-Modells verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="708fc-149">Non-numeric categorical data needs to be converted to a number before being used to build a machine learning model.</span></span>

<span data-ttu-id="708fc-150">Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:</span><span class="sxs-lookup"><span data-stu-id="708fc-150">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
CarData[] cars = new CarData[]
{
    new CarData
    {
        Color="Red",
        VehicleType="SUV"
    },
    new CarData
    {
        Color="Blue",
        VehicleType="Sedan"
    },
    new CarData
    {
        Color="Black",
        VehicleType="SUV"
    }
};
```

<span data-ttu-id="708fc-151">Die Kategorieeigenschaft `VehicleType` kann mit der [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*)-Methode in eine Zahl konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="708fc-151">The categorical `VehicleType` property can be converted into a number using the [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) method.</span></span>

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

<span data-ttu-id="708fc-152">Die daraus resultierende Transformation konvertiert den Textwert von `VehicleType` in eine Zahl.</span><span class="sxs-lookup"><span data-stu-id="708fc-152">The resulting transform converts the text value of `VehicleType` to a number.</span></span> <span data-ttu-id="708fc-153">Die Einträge in der `VehicleType`-Spalte sehen beim Anwenden der Transformation wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="708fc-153">The entries in the `VehicleType` column become the following when the transform is applied:</span></span>

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a><span data-ttu-id="708fc-154">Arbeiten mit Textdaten</span><span class="sxs-lookup"><span data-stu-id="708fc-154">Work with text data</span></span>

<span data-ttu-id="708fc-155">Textdaten müssen in Zahlen umgewandelt werden, bevor sie zum Erstellen eines Machine Learning-Modells verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="708fc-155">Text data needs to be transformed into numbers before using it to build a machine learning model.</span></span> <span data-ttu-id="708fc-156">Eine detailliertere Liste und Beschreibung der Texttransformationen finden Sie auf der Seite zu [Datentransformationen](../resources/transforms.md).</span><span class="sxs-lookup"><span data-stu-id="708fc-156">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="708fc-157">Verwenden Sie Daten wie die Daten unten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen wurden:</span><span class="sxs-lookup"><span data-stu-id="708fc-157">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="708fc-158">Zur Konvertierung von Text in eine numerische Vektordarstellung muss mindestens die [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*)-Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="708fc-158">The minimum step to convert text to a numerical vector representation is to use the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="708fc-159">Durch die Verwendung der [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*)-Transformation wird eine Reihe von Transformationen für die Eingabespalte durchgeführt, was zu einem numerischen Vektor führt, der die Lp-normalisierten Wort- und Zeichen-N-Gramme darstellt.</span><span class="sxs-lookup"><span data-stu-id="708fc-159">By using the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) transform, a series of transformations is applied to the input text column resulting in a numerical vector representing the lp-normalized word and character ngrams.</span></span>

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="708fc-160">Die resultierende Transformation konvertiert die Textwerte in der `Description`-Spalte in einen numerischen Vektor, der der folgenden Ausgabe ähnelt:</span><span class="sxs-lookup"><span data-stu-id="708fc-160">The resulting transform would convert the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="708fc-161">Kombinieren Sie komplexe Textverarbeitungsschritte zu einer [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601), um Rauschen zu entfernen und bei Bedarf die Menge der erforderlichen Verarbeitungsressourcen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="708fc-161">Combine complex text processing steps into an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) to remove noise and potentially reduce the amount of required processing resources as needed.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="708fc-162">`textEstimator` enthält eine Teilmenge von Vorgängen, die von der [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*)-Methode durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="708fc-162">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="708fc-163">Der Vorteil einer komplexeren Pipeline ist die Steuerung und Sichtbarkeit hinsichtlich der Transformationen, die für die Daten durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="708fc-163">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span>

<span data-ttu-id="708fc-164">Im Folgenden finden Sie am Beispiel des ersten Eintrags eine detaillierte Beschreibung der Ergebnisse, die durch die vom `textEstimator` definierten Transformationsschritte generiert wurden:</span><span class="sxs-lookup"><span data-stu-id="708fc-164">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="708fc-165">**Ursprünglicher Text: Das ist ein gutes Produkt**</span><span class="sxs-lookup"><span data-stu-id="708fc-165">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="708fc-166">Transformation</span><span class="sxs-lookup"><span data-stu-id="708fc-166">Transform</span></span> | <span data-ttu-id="708fc-167">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="708fc-167">Description</span></span> | <span data-ttu-id="708fc-168">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="708fc-168">Result</span></span>
|--|--|--|
|<span data-ttu-id="708fc-169">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="708fc-169">1. NormalizeText</span></span> | <span data-ttu-id="708fc-170">Konvertiert standardmäßig alle Buchstaben in Kleinbuchstaben</span><span class="sxs-lookup"><span data-stu-id="708fc-170">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="708fc-171">das ist ein gutes produkt</span><span class="sxs-lookup"><span data-stu-id="708fc-171">this is a good product</span></span>
|<span data-ttu-id="708fc-172">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="708fc-172">2. TokenizeWords</span></span> | <span data-ttu-id="708fc-173">Teilt die Zeichenfolge in einzelne Wörter auf</span><span class="sxs-lookup"><span data-stu-id="708fc-173">Splits string into individual words</span></span> | <span data-ttu-id="708fc-174">[„das“, „ist“, „ein“, „gutes“, „produkt“]</span><span class="sxs-lookup"><span data-stu-id="708fc-174">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="708fc-175">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="708fc-175">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="708fc-176">Entfernt die Stoppwörter wie *ist* und *ein*.</span><span class="sxs-lookup"><span data-stu-id="708fc-176">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="708fc-177">[„gutes“, „produkt“]</span><span class="sxs-lookup"><span data-stu-id="708fc-177">["good","product"]</span></span>
|<span data-ttu-id="708fc-178">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="708fc-178">4. MapValueToKey</span></span> | <span data-ttu-id="708fc-179">Ordnet die Werte den Schlüsseln (Kategorien) basierend auf den Eingabedaten zu</span><span class="sxs-lookup"><span data-stu-id="708fc-179">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="708fc-180">[1,2]</span><span class="sxs-lookup"><span data-stu-id="708fc-180">[1,2]</span></span>
|<span data-ttu-id="708fc-181">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="708fc-181">5. ProduceNGrams</span></span> | <span data-ttu-id="708fc-182">Transformiert Text in eine Folge von aufeinander folgenden Wörtern</span><span class="sxs-lookup"><span data-stu-id="708fc-182">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="708fc-183">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="708fc-183">[1,1,1,0,0]</span></span>
|<span data-ttu-id="708fc-184">6. NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="708fc-184">6. NormalizeLpNorm</span></span> | <span data-ttu-id="708fc-185">Skaliert Eingaben durch ihre Lp-Norm</span><span class="sxs-lookup"><span data-stu-id="708fc-185">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="708fc-186">[ 0,577350529, 0,577350529, 0,577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="708fc-186">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
