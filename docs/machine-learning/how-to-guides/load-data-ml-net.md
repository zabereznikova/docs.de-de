---
title: Laden von Daten
description: Laden der Datendatei der Streamingdaten in ML.NET
ms.date: 05/03/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 6edcc92b610e2e1f5e21c371b9f0aefd0b216d31
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063646"
---
# <a name="load-data-from-file-and-in-memory-sources"></a>Laden von Daten aus der Datei und In-Memory-Quellen

Diese Anleitung zeigt Ihnen, wie Sie Daten für die Verarbeitung und das Training in ML.NET laden. Die Daten werden ursprünglich in Dateien oder Echtzeit-/Streamingdatenquellen gespeichert.

## <a name="create-the-data-model"></a>Erstellen des Datenmodells

Mit ML.NET können Sie Datenmodelle über Klassen definieren. Nehmen wir zum Beispiel die folgenden Eingabedaten:

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

Erstellen Sie ein Datenmodell, das den folgenden Codeausschnitt darstellt:

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }
 
    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

### <a name="annotating-the-data-model-with-column-attributes"></a>Kommentieren des Datenmodells mit Spaltenattributen

Attribute geben ML.NET mehr Informationen über das Datenmodell und die Datenquelle.

Das [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)-Attribut gibt die Spaltenindizes Ihrer Eigenschaften an.

> [!IMPORTANT]
> [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) ist nur erforderlich, wenn Daten aus einer Datei geladen werden.

Spalten werden folgendermaßen geladen: 
- Als Einzelspalten, wie `Size` und `CurrentPrices` in der `HousingData`-Klasse.
- In mehreren Spalten gleichzeitig in Form eines Vektors wie `HistoricalPrices` in der `HousingData`-Klasse.

Wenn Sie eine Vektoreigenschaft haben, wenden Sie das [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute)-Attribut auf die Eigenschaft in Ihrem Datenmodell an. Dabei ist zu beachten, dass alle Elemente im Vektor vom gleichen Typ sein müssen.

ML.NET arbeitet mit Spaltennamen. Wenn die Spalte einen anderen Namen als den Eigenschaftsnamen haben soll, verwenden Sie das [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute)-Attribut. Beim Erstellen von In-Memory-Objekten erstellen Sie Objekte weiterhin unter Verwendung des Eigenschaftsnamens. Für die Datenverarbeitung und die Erstellung von Machine Learning-Modellen überschreibt und referenziert ML.NET jedoch die Eigenschaft mit dem im [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute)-Attribut angegebenen Wert.

## <a name="load-data-from-a-single-file"></a>Laden von Daten aus einer Einzeldatei

Um Daten aus einer Datei zu laden, verwenden Sie die [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*)-Methode zusammen mit dem Datenmodell für die zu ladenden Daten. Da der `separatorChar`-Parameter standardmäßig mit Tabstopptrennzeichen getrennt ist, ändern Sie ihn bei Bedarf für Ihre Datendatei. Wenn Ihre Datei einen Header hat, setzen Sie den `hasHeader`-Parameter auf `true`, um die erste Zeile in der Datei zu ignorieren und mit dem Laden von Daten aus der zweiten Zeile zu beginnen.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a>Laden von Daten aus mehreren Dateien

Wenn Ihre Daten in mehreren Dateien gespeichert sind, können Sie mit ML.NET Daten aus mehreren Dateien laden, die sich entweder im gleichen Verzeichnis oder in mehreren Verzeichnissen befinden, solange das Datenschema gleich ist.

### <a name="load-from-files-in-a-single-directory"></a>Laden von Dateien in einem einzigen Verzeichnis

Wenn sich alle Ihre Datendateien im gleichen Verzeichnis befinden, verwenden Sie in der [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*)-Methode Platzhalter.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a>Laden von Dateien in mehreren Verzeichnissen

Um Daten aus mehreren Verzeichnissen zu laden, verwenden Sie die [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*)-Methode, um einen [`TextLoader`](xref:Microsoft.ML.Data.TextLoader) zu erstellen. Verwenden Sie dann die [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*)-Methode, und geben Sie die einzelnen Dateipfade an (Platzhalter können nicht verwendet werden).

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-streaming-source"></a>Laden von Daten aus einer Streamingquelle

Zusätzlich zum Laden von Daten, die auf dem Datenträger gespeichert sind, unterstützt ML.NET das Laden von Daten aus verschiedenen Streamingquellen, wie zum Beispiel:

- In-Memory-Sammlungen
- JSON/XML
- Datenbanken

> [!IMPORTANT]
> Beachten Sie, dass ML.NET bei der Arbeit mit Streamingquellen erwartet, dass die Eingabe in Form einer In-Memory-Sammlung erfolgt. Achten Sie daher bei der Arbeit mit Quellen wie JSON/XML darauf, die Daten in eine In-Memory-Sammlung zu formatieren.

Schauen Sie sich die folgende in-Memory-Sammlung an:

```csharp
HousingData[] inMemoryCollection = new HousingData[]
{
    new HousingData
    {
        Size =700f,
        HistoricalPrices = new float[]
        {
            100000f, 3000000f, 250000f
        },
        CurrentPrice = 500000f
    },
    new HousingData
    {
        Size =1000f,
        HistoricalPrices = new float[]
        {
            600000f, 400000f, 650000f
        },
        CurrentPrice=700000f
    }
};
```

Laden Sie die in-Memory-Sammlung mit der [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)-Methode in eine [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
