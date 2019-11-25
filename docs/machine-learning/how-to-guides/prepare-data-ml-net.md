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
# <a name="prepare-data-for-building-a-model"></a>Vorbereiten von Daten für die Modellerstellung

Erfahren Sie, wie Sie ML.NET verwenden können, um Daten für die weitere Verarbeitung oder die Erstellung eines Modells aufzubereiten.

Die Daten sind oft unsauber und haben eine geringe Dichte. Für Machine-Learning-Algorithmen in ML.NET sind Eingaben oder Features in einem einzigen numerischen Vektor erforderlich. Analog dazu muss der Wert, der vorhersagt werden soll (Label), codiert werden. Dies gilt insbesondere für kategorische Daten. Daher besteht eines der Ziele der Datenaufbereitung darin, die Daten in das von ML.NET-Algorithmen erwartete Format zu bringen.

## <a name="filter-data"></a>Filtern von Daten

Manchmal sind nicht alle Daten in einem Dataset für die Analyse relevant. Ein Ansatz zur Entfernung irrelevanter Daten ist das Filtern. Der [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) enthält eine Reihe von Filtervorgängen, der eine [`IDataView`](xref:Microsoft.ML.IDataView) mit allen Daten aufnehmen und eine [IDataView](xref:Microsoft.ML.IDataView) zurückgeben kann, die nur die Datenpunkte von Interesse enthält. Es ist wichtig zu beachten, dass Filtervorgänge nicht als Teil einer [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)- oder [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601)-Datenaufbereitungspipeline aufgenommen werden können, da sie kein [`IEstimator`](xref:Microsoft.ML.IEstimator%601) oder [`ITransformer`](xref:Microsoft.ML.ITransformer) wie im [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog) sind.

Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:

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

Um Daten nach dem Wert einer Spalte zu filtern, verwenden Sie die [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*)-Methode.

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

Das obige Beispiel zeigt Zeilen im Dataset mit einem Preis zwischen 20.0000 und 100.000.000. Das Ergebnis der Anwendung dieses Filters würde nur die letzten beiden Zeilen in den Daten zurückgeben und die erste Zeile ausschließen, da der Preis den Wert 100000 hat und nicht im angegebenen Bereich liegt.

## <a name="replace-missing-values"></a>Ersetzen fehlender Werte

Fehlende Werte kommen in Datasets häufig vor. Ein Ansatz für den Umgang mit fehlenden Daten, besteht darin, sie durch den Standardwert für den gegebenen Typ zu ersetzen, falls vorhanden, oder durch einen anderen sinnvollen Wert, wie beispielsweise den Mittelwert der Daten.

Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:

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

Beachten Sie, dass im letzten Element in unserer Liste ein Wert für `Price` fehlt. Um die fehlenden Werte in der `Price`-Spalte zu ersetzen, verwenden Sie die -Methode [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*), um diesen fehlenden Wert einzugeben.

> [!IMPORTANT]
> [`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) funktioniert nur mit numerischen Daten.

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

ML.NET unterstützt verschiedene [Ersetzungsmodi](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode). Das obige Beispiel verwendet den `Mean`-Ersetzungsmodus, der den fehlenden Wert mit dem Durchschnittswert dieser Spalte ausfüllt. Das Ergebnis der Ersetzung trägt für die `Price`-Eigenschaft für das letzte Element in unseren Daten mit 200.000 ein, da dies der Durchschnitt von 100.000 und 300.000 ist.

## <a name="use-normalizers"></a>Verwenden von Normalisierungsfunktionen

Die [Normalisierung](https://en.wikipedia.org/wiki/Feature_scaling) ist eine Datenvorverarbeitungstechnik, die verwendet wird, um Features zu standardisieren, die nicht in der gleichen Größenordnung liegen. Da können Algorithmen schneller konvergieren. So variieren beispielsweise die Bereiche für Werte wie Alter und Einkommen stark, wobei das Alter im Allgemeinen im Bereich von 0-100 und das Einkommen im Allgemeinen im Bereich von Null bis Tausend liegt. Eine detailliertere Liste und Beschreibung der Normalisierungstransformationen finden Sie auf der Seite zu [Datentransformationen](../resources/transforms.md).

### <a name="min-max-normalization"></a>Min-Max-Normalisierung

Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:

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

Auf Spalten mit einzelnen numerischen Werten sowie auf Vektoren kann Normalisierung angewendet werden. Verwenden Sie die Min-Max-Normalisierung mit der [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*)-Methode, um die Daten in der Spalte `Price` zu normalisieren.

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

Die ursprünglichen Preiswerte `[200000,100000]` werden unter Verwendung der Normalisierungsformel `MinMax` in `[ 1, 0.5 ]` umgewandelt, wodurch Ausgabewerte im Bereich von 0-1 generiert werden.

### <a name="binning"></a>Quantisierung

Die [Quantisierung](https://en.wikipedia.org/wiki/Data_binning) konvertiert kontinuierliche Werte in eine diskrete Darstellung der Eingabe. Nehmen wir beispielsweise an, dass eines Ihrer Features das Alter ist. Anstatt den tatsächlichen Alterswert zu verwenden, werden durch die Quantisierung Bereiche für diesen Wert erstellt. 0 bis 18 könnte dabei einer der Bereiche sein, ein anderer könnte 19 bis 35 sein usw.

Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:

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

Normalisieren Sie die Daten mit der [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*)-Methode in Bereiche. Mit dem `maximumBinCount`-Parameter können Sie die Anzahl der Bereiche angeben, die zur Klassifizierung Ihrer Daten benötigt werden. In diesem Beispiel werden Daten in zwei Bereiche aufgeteilt.

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

Durch die Quantisierung werden Bereichsbegrenzungen von `[0,200000,Infinity]` erstellt. Daher sind die resultierenden Bereiche `[0,1,1]`, weil die erste beobachteten Werte zwischen 0 und 200.000 liegen und die anderen größer als 200.000, aber kleiner als unendlich sind.

## <a name="work-with-categorical-data"></a>Arbeiten mit Kategoriedaten

Nicht-numerische Kategoriedaten müssen in eine Zahl umgewandelt werden, bevor sie zum Erstellen eines Machine Learning-Modells verwendet werden können.

Verwenden die folgenden Eingabedaten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden:

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

Die Kategorieeigenschaft `VehicleType` kann mit der [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*)-Methode in eine Zahl konvertiert werden.

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

Die daraus resultierende Transformation konvertiert den Textwert von `VehicleType` in eine Zahl. Die Einträge in der `VehicleType`-Spalte sehen beim Anwenden der Transformation wie folgt aus:

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a>Arbeiten mit Textdaten

Textdaten müssen in Zahlen umgewandelt werden, bevor sie zum Erstellen eines Machine Learning-Modells verwendet werden können. Eine detailliertere Liste und Beschreibung der Texttransformationen finden Sie auf der Seite zu [Datentransformationen](../resources/transforms.md).

Verwenden Sie Daten wie die Daten unten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen wurden:

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

Zur Konvertierung von Text in eine numerische Vektordarstellung muss mindestens die [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*)-Methode verwendet werden. Durch die Verwendung der [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*)-Transformation wird eine Reihe von Transformationen für die Eingabespalte durchgeführt, was zu einem numerischen Vektor führt, der die Lp-normalisierten Wort- und Zeichen-N-Gramme darstellt.

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

Die resultierende Transformation konvertiert die Textwerte in der `Description`-Spalte in einen numerischen Vektor, der der folgenden Ausgabe ähnelt:

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

Kombinieren Sie komplexe Textverarbeitungsschritte zu einer [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601), um Rauschen zu entfernen und bei Bedarf die Menge der erforderlichen Verarbeitungsressourcen zu reduzieren.

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

`textEstimator` enthält eine Teilmenge von Vorgängen, die von der [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*)-Methode durchgeführt werden. Der Vorteil einer komplexeren Pipeline ist die Steuerung und Sichtbarkeit hinsichtlich der Transformationen, die für die Daten durchgeführt werden.

Im Folgenden finden Sie am Beispiel des ersten Eintrags eine detaillierte Beschreibung der Ergebnisse, die durch die vom `textEstimator` definierten Transformationsschritte generiert wurden:

**Ursprünglicher Text: Das ist ein gutes Produkt**

|Transformation | BESCHREIBUNG | Ergebnis
|--|--|--|
|1. NormalizeText | Konvertiert standardmäßig alle Buchstaben in Kleinbuchstaben | das ist ein gutes produkt
|2. TokenizeWords | Teilt die Zeichenfolge in einzelne Wörter auf | [„das“, „ist“, „ein“, „gutes“, „produkt“]
|3. RemoveDefaultStopWords | Entfernt die Stoppwörter wie *ist* und *ein*. | [„gutes“, „produkt“]
|4. MapValueToKey | Ordnet die Werte den Schlüsseln (Kategorien) basierend auf den Eingabedaten zu |  [1,2]
|5. ProduceNGrams | Transformiert Text in eine Folge von aufeinander folgenden Wörtern | [1,1,1,0,0]
|6. NormalizeLpNorm | Skaliert Eingaben durch ihre Lp-Norm | [ 0,577350529, 0,577350529, 0,577350529, 0, 0 ]
