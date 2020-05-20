---
title: Laden von Daten aus Dateien und anderen Quellen
description: Diese Anleitung zeigt Ihnen, wie Sie Daten mithilfe der API für die Verarbeitung und das Training in ML.NET laden. Daten werden in Dateien, Datenbanken, JSON, XML oder In-Memory-Sammlungen gespeichert.
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 83aaae2d2e75b3076841750bf5d505390a538bc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74344755"
---
# <a name="load-data-from-files-and-other-sources"></a>Laden von Daten aus Dateien und anderen Quellen

Diese Anleitung zeigt Ihnen, wie Sie Daten mithilfe der API für die Verarbeitung und das Training in ML.NET laden. Die Daten werden ursprünglich in Dateien oder anderen Datenquellen wie Datenbanken, JSON, XML oder In-Memory-Sammlungen gespeichert.

Wenn Sie den Modell-Generator verwenden, finden Sie weitere Informationen unter [Laden von Trainingsdaten in den Modell-Generator](load-data-model-builder.md).

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

Wenn Sie eine Vektoreigenschaft haben, wenden Sie das [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute)-Attribut auf die Eigenschaft in Ihrem Datenmodell an. Dabei ist zu beachten, dass alle Elemente im Vektor vom gleichen Typ sein müssen. Die Trennung der Spalten ermöglicht einfaches und flexibles Merkmalsengineering, aber bei einer sehr großen Anzahl von Spalten führt die Bearbeitung der einzelnen Spalten zu einem negativen Einfluss auf die Trainingsgeschwindigkeit.

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

## <a name="load-data-from-a-relational-database"></a>Laden von Daten aus einer relationalen Datenbank

ML.NET unterstützt das Laden von Daten aus einer Vielzahl von relationalen Datenbanken, die von [`System.Data`](xref:System.Data) unterstützt werden, darunter SQL Server, Azure SQL-Datenbank, Oracle, SQLite, PostgreSQL, Progress, IBM DB2 und viele mehr.

> [!NOTE]
> Um `DatabaseLoader`zu verwenden, verweisen Sie auf das NuGet-Paket [System. Data. SqlClient](https://www.nuget.org/packages/System.Data.SqlClient).

Bei einer Datenbank mit einer Tabelle mit dem Namen `House` und dem folgenden Schema:

```SQL
CREATE TABLE [House] (
    [HouseId] INT NOT NULL IDENTITY,
    [Size] INT NOT NULL,
    [NumBed] INT NOT NULL,
    [Price] REAL NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

Die Daten können durch eine Klasse wie `HouseData` modelliert werden.

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float NumBed { get; set; }

    public float Price { get; set; }
}
```

Erstellen Sie dann in der Anwendung eine `DatabaseLoader`-Klasse.

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

Definieren Sie die Verbindungszeichenfolge sowie den SQL-Befehl, der für die Datenbank ausgeführt werden soll, und erstellen Sie eine `DatabaseSource`-Instanz. Dieses Beispiel verwendet eine LocalDB-SQL Server-Datenbank mit einem Dateipfad. DatabaseLoader unterstützt jedoch jede andere gültige Verbindungszeichenfolge für lokale Datenbanken und Clouddatenbanken.

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size, CAST(NumBed as REAL) as NumBed, Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance, connectionString, sqlCommand);
```

Numerische Daten, die nicht vom Typ [`Real`](xref:System.Data.SqlDbType) sind, müssen in [`Real`](xref:System.Data.SqlDbType) konvertiert werden. Der [`Real`](xref:System.Data.SqlDbType)-Typ wird als Gleitkommawert mit einfacher Genauigkeit oder [`Single`](xref:System.Single) dargestellt (der von ML.NET-Algorithmen erwartete Eingabetyp). In diesem Beispiel ist die Spalte `NumBed` eine ganze Zahl in der Datenbank. Mithilfe der integrierten Funktion `CAST` wird sie in [`Real`](xref:System.Data.SqlDbType) konvertiert. Da die `Price`-Eigenschaft bereits vom Typ [`Real`](xref:System.Data.SqlDbType) ist, wird sie unverändert geladen.

Verwenden Sie die `Load`-Methode, um die Daten in ein [`IDataView`](xref:Microsoft.ML.IDataView)-Element zu laden.

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a>Laden von Daten aus anderen Quellen

Zusätzlich zum Laden von Daten, die in Dateien gespeichert sind, unterstützt ML.NET das Laden von Daten aus verschiedenen Quellen, wie zum Beispiel:

- In-Memory-Sammlungen
- JSON/XML

Beachten Sie, dass ML.NET bei der Arbeit mit Streamingquellen erwartet, dass die Eingabe in Form einer In-Memory-Sammlung erfolgt. Achten Sie daher bei der Arbeit mit Quellen wie JSON/XML darauf, die Daten in eine In-Memory-Sammlung zu formatieren.

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

> [!IMPORTANT]
> [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) geht davon aus, dass das [`IEnumerable`](xref:System.Collections.IEnumerable)-Element, aus dem es geladen wird, threadsicher ist.

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

## <a name="next-steps"></a>Nächste Schritte

- Informationen zum Bereinigen oder anderweitigen Verarbeiten von Daten finden Sie unter [Vorbereiten von Daten für die Modellerstellung](prepare-data-ml-net.md).
- Wenn Sie bereit sind, ein Modell zu erstellen, finden Sie weitere Informationen unter [Trainieren und Auswerten eines Modells](train-machine-learning-model-ml-net.md).
