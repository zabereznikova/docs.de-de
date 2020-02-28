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
# <a name="prepare-data-for-building-a-model"></a>Vorbereiten von Daten für die Modellerstellung

Erfahren Sie, wie Sie ML.NET verwenden können, um Daten für die weitere Verarbeitung oder die Erstellung eines Modells aufzubereiten.

Die Daten sind oft unsauber und haben eine geringe Dichte. Für Machine-Learning-Algorithmen in ML.NET sind Eingaben oder Features in einem einzigen numerischen Vektor erforderlich. Analog dazu muss der Wert, der vorhersagt werden soll (Label), codiert werden. Dies gilt insbesondere für kategorische Daten. Daher besteht eines der Ziele der Datenaufbereitung darin, die Daten in das von ML.NET-Algorithmen erwartete Format zu bringen.

## <a name="filter-data"></a>Filtern von Daten

Manchmal sind nicht alle Daten in einem Dataset für die Analyse relevant. Ein Ansatz zur Entfernung irrelevanter Daten ist das Filtern. Der [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) enthält eine Reihe von Filtervorgängen, der eine [`IDataView`](xref:Microsoft.ML.IDataView) mit allen Daten aufnehmen und eine [IDataView](xref:Microsoft.ML.IDataView) zurückgeben kann, die nur die Datenpunkte von Interesse enthält. Es ist wichtig zu beachten, dass Filtervorgänge nicht als Teil einer [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)- oder [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601)-Datenaufbereitungspipeline aufgenommen werden können, da sie kein [`IEstimator`](xref:Microsoft.ML.IEstimator%601) oder [`ITransformer`](xref:Microsoft.ML.ITransformer) wie im [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog) sind.

Laden Sie die folgenden Eingabedaten in eine [`IDataView`](xref:Microsoft.ML.IDataView) namens `data`:

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

Um Daten nach dem Wert einer Spalte zu filtern, verwenden Sie die [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A)-Methode.

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

Das obige Beispiel zeigt Zeilen im Dataset mit einem Preis zwischen 20.0000 und 100.000.000. Das Ergebnis der Anwendung dieses Filters würde nur die letzten beiden Zeilen in den Daten zurückgeben und die erste Zeile ausschließen, da der Preis den Wert 100000 hat und nicht im angegebenen Bereich liegt.

## <a name="replace-missing-values"></a>Ersetzen fehlender Werte

Fehlende Werte kommen in Datasets häufig vor. Ein Ansatz für den Umgang mit fehlenden Daten, besteht darin, sie durch den Standardwert für den gegebenen Typ zu ersetzen, falls vorhanden, oder durch einen anderen sinnvollen Wert, wie beispielsweise den Mittelwert der Daten.

Laden Sie die folgenden Eingabedaten in eine [`IDataView`](xref:Microsoft.ML.IDataView) namens `data`:

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

Beachten Sie, dass im letzten Element in unserer Liste ein Wert für `Price` fehlt. Um die fehlenden Werte in der `Price`-Spalte zu ersetzen, verwenden Sie die -Methode [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A), um diesen fehlenden Wert einzugeben.

> [!IMPORTANT]
> [`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) funktioniert nur mit numerischen Daten.

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

ML.NET unterstützt verschiedene [Ersetzungsmodi](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode). Das obige Beispiel verwendet den Ersetzungsmodus `Mean`, der den fehlenden Wert mit dem Durchschnittswert dieser Spalte auffüllt. Das Ergebnis der Ersetzung trägt für die `Price`-Eigenschaft für das letzte Element in unseren Daten mit 200.000 ein, da dies der Durchschnitt von 100.000 und 300.000 ist.

## <a name="use-normalizers"></a>Verwenden von Normalisierungsfunktionen

[Normalisierung](https://en.wikipedia.org/wiki/Feature_scaling) ist eine Datenvorverarbeitungstechnik, die verwendet wird, um Features so zu skalieren, dass sie sich im gleichen Bereich, normalerweise zwischen 0 und 1, befinden, damit sie von einem Algorithmus für maschinelles Lernen präziser verarbeitet werden können. So variieren beispielsweise die Bereiche für Alter und Einkommen stark, wobei das Alter im Allgemeinen im Bereich von 0-100 und das Einkommen im Allgemeinen im Bereich von 0 bis x-Tausende liegt. Eine detailliertere Liste und Beschreibung der Normalisierungstransformationen finden Sie auf der Seite zu [Datentransformationen](../resources/transforms.md).

### <a name="min-max-normalization"></a>Min-Max-Normalisierung

Laden Sie die folgenden Eingabedaten in eine [`IDataView`](xref:Microsoft.ML.IDataView) namens `data`:

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

Auf Spalten mit einzelnen numerischen Werten sowie auf Vektoren kann Normalisierung angewendet werden. Verwenden Sie die Min-Max-Normalisierung mit der [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A)-Methode, um die Daten in der Spalte `Price` zu normalisieren.

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

Die ursprünglichen Preiswerte `[200000,100000]` werden unter Verwendung der Normalisierungsformel `MinMax` in `[ 1, 0.5 ]` umgewandelt, wodurch Ausgabewerte im Bereich von 0 bis 1 generiert werden.

### <a name="binning"></a>Quantisierung

Die [Quantisierung](https://en.wikipedia.org/wiki/Data_binning) konvertiert kontinuierliche Werte in eine diskrete Darstellung der Eingabe. Nehmen wir beispielsweise an, dass eines Ihrer Features das Alter ist. Anstatt den tatsächlichen Alterswert zu verwenden, werden durch die Quantisierung Bereiche für diesen Wert erstellt. 0 bis 18 könnte dabei einer der Bereiche sein, ein anderer könnte 19 bis 35 sein usw.

Laden Sie die folgenden Eingabedaten in eine [`IDataView`](xref:Microsoft.ML.IDataView) namens `data`:

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

Normalisieren Sie die Daten mit der [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A)-Methode in Bereiche. Mit dem `maximumBinCount`-Parameter können Sie die Anzahl der Bereiche angeben, die zur Klassifizierung Ihrer Daten benötigt werden. In diesem Beispiel werden Daten in zwei Bereiche aufgeteilt.

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

Einer der gängigsten Datentypen sind Kategoriedaten. Kategoriedaten zeichnen sich durch eine begrenzte Anzahl von Kategorien aus. Beispiele sind die Bundesstaaten der USA oder eine Liste der Tierarten, die in einer Reihe von Bildern gefunden wurden. Unabhängig davon, ob es sich bei den Kategoriedaten um Features oder Beschriftungen handelt, müssen sie einem numerischen Wert zugeordnet werden, damit sie zur Erzeugung eines Machine Learning-Modells verwendet werden können. Es gibt je nach dem zu lösenden Problem eine Reihe von Möglichkeiten, in ML.NET mit Kategoriedaten zu arbeiten.

### <a name="key-value-mapping"></a>Schlüsselwertzuordnung

In ML.NET ist ein Schlüssel ein ganzzahliger Wert, der eine Kategorie darstellt. Die Schlüsselwertzuordnung kommt meist zum Einsatz, um Zeichenfolgenbeschriftungen für das Training eindeutigen ganzzahligen Werten und dann wieder ihren Zeichenfolgenwerten zuzuordnen, sobald das Modell zum Erstellen einer Vorhersage verwendet wird.

Die für die Schlüsselwertzuordnung verwendeten Transformationen sind [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) und [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).

`MapValueToKey` fügt ein Wörterbuch von Zuordnungen im Modell hinzu, sodass `MapKeyToValue` bei der Erstellung einer Vorhersage die Rücktransformation vornehmen kann.

### <a name="one-hot-encoding"></a>1-aus-n-Code

1-aus-n-Code verwendet eine endliche Menge von Werten und ordnet sie ganzen Zahlen zu, deren binäre Darstellung einen einzigen `1`-Wert an eindeutigen Positionen in der Zeichenfolge aufweist. 1-aus-n-Code kann die beste Wahl sein, wenn es keine implizite Reihenfolge der Kategoriedaten gibt. In der folgenden Tabelle wird ein Beispiel mit Postleitzahlen als Rohwerte gezeigt.

|Rohwert|1-aus-n-Code-Wert|
|---------|---------------------|
|98052|00...01|
|98100|00...10|
|...|...|
|98109|10...00|

Die Transformation zum Konvertieren von Kategoriedaten in1-aus-n-Code-Zahlen ist [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).

### <a name="hashing"></a>Hashing

Hashing ist eine weitere Möglichkeit, um Kategoriedaten in Zahlen umzuwandeln. Eine Hashfunktion ordnet Daten beliebiger Größe (z. B. eine Textzeichenfolge) einer Zahl mit einem festen Bereich zu. Hashing kann eine schnelle und speichereffiziente Methode zur Vektorisierung von Features sein. Ein nennenswertes Beispiel für Hashing beim maschinellen Lernen sind E-Mail-Spamfilter, bei denen anstelle eines Wörterbuchs bekannter Wörter jedes Wort in der E-Mail gehasht und zu einem großen Featurevektor hinzugefügt wird. Durch den Einsatz von Hashing wird das Problem der Umgehung des Spamfilters durch die Verwendung von Wörtern vermieden, die nicht im Wörterbuch stehen.

ML.NET bietet eine [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A)-Transformation zur Durchführung des Hashings für Text, Datumsangaben und numerische Daten. Wie bei der Schlüsselwertzuordnung sind die Ausgaben der Hashtransformation Schlüsseltypen.

## <a name="work-with-text-data"></a>Arbeiten mit Textdaten

Wie Kategoriedaten müssen Textdaten in numerische Features umgewandelt werden, bevor sie zum Erstellen eines Machine Learning-Modells verwendet werden können. Eine detailliertere Liste und Beschreibung der Texttransformationen finden Sie auf der Seite zu [Datentransformationen](../resources/transforms.md).

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

ML.NET bietet die [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A)-Transformation, die den Zeichenfolgenwert eines Texts verwendet und durch Anwenden einer Reihe einzelner Transformationen eine Reihe von Features anhand des Texts erstellt.

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

Die resultierende Transformation konvertiert die Textwerte in der Spalte `Description` in einen numerischen Vektor, der der folgenden Ausgabe ähnelt:

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

Die Transformationen, aus denen sich `FeaturizeText` zusammensetzt, können auch für eine präzisere Steuerung der Generierung von Features einzeln angewendet werden.

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

`textEstimator` enthält eine Teilmenge von Vorgängen, die von der [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A)-Methode durchgeführt werden. Der Vorteil einer komplexeren Pipeline ist die Steuerung und Sichtbarkeit hinsichtlich der Transformationen, die für die Daten durchgeführt werden.

Im Folgenden finden Sie am Beispiel des ersten Eintrags eine detaillierte Beschreibung der Ergebnisse, die durch die vom `textEstimator` definierten Transformationsschritte generiert wurden:

**Ursprünglicher Text: Das ist ein gutes Produkt**

|Transformation | Beschreibung | Ergebnis
|--|--|--|
|1. NormalizeText | Konvertiert standardmäßig alle Buchstaben in Kleinbuchstaben | das ist ein gutes produkt
|2. TokenizeWords | Teilt die Zeichenfolge in einzelne Wörter auf | [„das“, „ist“, „ein“, „gutes“, „produkt“]
|3. RemoveDefaultStopWords | Entfernt die Stoppwörter wie *ist* und *ein*. | [„gutes“, „produkt“]
|4. MapValueToKey | Ordnet die Werte den Schlüsseln (Kategorien) basierend auf den Eingabedaten zu |  [1,2]
|5. ProduceNGrams | Transformiert Text in eine Folge von aufeinander folgenden Wörtern | [1,1,1,0,0]
|6. NormalizeLpNorm | Skaliert Eingaben durch ihre Lp-Norm | [ 0,577350529, 0,577350529, 0,577350529, 0, 0 ]
