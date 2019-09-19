---
title: Laden von Daten aus Dateien und anderen Quellen
description: Diese Anleitung zeigt Ihnen, wie Sie Daten für die Verarbeitung und das Training in ML.NET laden. Die Daten werden ursprünglich in Dateien oder anderen Datenquellen wie Datenbanken, JSON, XML oder In-Memory-Sammlungen gespeichert.
ms.date: 09/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 4008f38bf4a20113a3f5c865e38222e5b82f2acc
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991363"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="8ba02-104">Laden von Daten aus Dateien und anderen Quellen</span><span class="sxs-lookup"><span data-stu-id="8ba02-104">Load data from files and other sources</span></span>

<span data-ttu-id="8ba02-105">Diese Anleitung zeigt Ihnen, wie Sie Daten für die Verarbeitung und das Training in ML.NET laden.</span><span class="sxs-lookup"><span data-stu-id="8ba02-105">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="8ba02-106">Die Daten werden ursprünglich in Dateien oder anderen Datenquellen wie Datenbanken, JSON, XML oder In-Memory-Sammlungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8ba02-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="8ba02-107">Erstellen des Datenmodells</span><span class="sxs-lookup"><span data-stu-id="8ba02-107">Create the data model</span></span>

<span data-ttu-id="8ba02-108">Mit ML.NET können Sie Datenmodelle über Klassen definieren.</span><span class="sxs-lookup"><span data-stu-id="8ba02-108">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="8ba02-109">Nehmen wir zum Beispiel die folgenden Eingabedaten:</span><span class="sxs-lookup"><span data-stu-id="8ba02-109">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="8ba02-110">Erstellen Sie ein Datenmodell, das den folgenden Codeausschnitt darstellt:</span><span class="sxs-lookup"><span data-stu-id="8ba02-110">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="8ba02-111">Kommentieren des Datenmodells mit Spaltenattributen</span><span class="sxs-lookup"><span data-stu-id="8ba02-111">Annotating the data model with column attributes</span></span>

<span data-ttu-id="8ba02-112">Attribute geben ML.NET mehr Informationen über das Datenmodell und die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="8ba02-112">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="8ba02-113">Das [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)-Attribut gibt die Spaltenindizes Ihrer Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="8ba02-113">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ba02-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) ist nur erforderlich, wenn Daten aus einer Datei geladen werden.</span><span class="sxs-lookup"><span data-stu-id="8ba02-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="8ba02-115">Spalten werden folgendermaßen geladen:</span><span class="sxs-lookup"><span data-stu-id="8ba02-115">Load columns as:</span></span>

- <span data-ttu-id="8ba02-116">Als Einzelspalten, wie `Size` und `CurrentPrices` in der `HousingData`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8ba02-116">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="8ba02-117">In mehreren Spalten gleichzeitig in Form eines Vektors wie `HistoricalPrices` in der `HousingData`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8ba02-117">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="8ba02-118">Wenn Sie eine Vektoreigenschaft haben, wenden Sie das [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute)-Attribut auf die Eigenschaft in Ihrem Datenmodell an.</span><span class="sxs-lookup"><span data-stu-id="8ba02-118">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="8ba02-119">Dabei ist zu beachten, dass alle Elemente im Vektor vom gleichen Typ sein müssen.</span><span class="sxs-lookup"><span data-stu-id="8ba02-119">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="8ba02-120">Die Trennung der Spalten ermöglicht einfaches und flexibles Merkmalsengineering, aber bei einer sehr großen Anzahl von Spalten führt die Bearbeitung der einzelnen Spalten zu einem negativen Einfluss auf die Trainingsgeschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="8ba02-120">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="8ba02-121">ML.NET arbeitet mit Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="8ba02-121">ML.NET Operates through column names.</span></span> <span data-ttu-id="8ba02-122">Wenn die Spalte einen anderen Namen als den Eigenschaftsnamen haben soll, verwenden Sie das [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute)-Attribut.</span><span class="sxs-lookup"><span data-stu-id="8ba02-122">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="8ba02-123">Beim Erstellen von In-Memory-Objekten erstellen Sie Objekte weiterhin unter Verwendung des Eigenschaftsnamens.</span><span class="sxs-lookup"><span data-stu-id="8ba02-123">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="8ba02-124">Für die Datenverarbeitung und die Erstellung von Machine Learning-Modellen überschreibt und referenziert ML.NET jedoch die Eigenschaft mit dem im [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute)-Attribut angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="8ba02-124">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="8ba02-125">Laden von Daten aus einer Einzeldatei</span><span class="sxs-lookup"><span data-stu-id="8ba02-125">Load data from a single file</span></span>

<span data-ttu-id="8ba02-126">Um Daten aus einer Datei zu laden, verwenden Sie die [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*)-Methode zusammen mit dem Datenmodell für die zu ladenden Daten.</span><span class="sxs-lookup"><span data-stu-id="8ba02-126">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="8ba02-127">Da der `separatorChar`-Parameter standardmäßig mit Tabstopptrennzeichen getrennt ist, ändern Sie ihn bei Bedarf für Ihre Datendatei.</span><span class="sxs-lookup"><span data-stu-id="8ba02-127">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="8ba02-128">Wenn Ihre Datei einen Header hat, setzen Sie den `hasHeader`-Parameter auf `true`, um die erste Zeile in der Datei zu ignorieren und mit dem Laden von Daten aus der zweiten Zeile zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="8ba02-128">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="8ba02-129">Laden von Daten aus mehreren Dateien</span><span class="sxs-lookup"><span data-stu-id="8ba02-129">Load data from multiple files</span></span>

<span data-ttu-id="8ba02-130">Wenn Ihre Daten in mehreren Dateien gespeichert sind, können Sie mit ML.NET Daten aus mehreren Dateien laden, die sich entweder im gleichen Verzeichnis oder in mehreren Verzeichnissen befinden, solange das Datenschema gleich ist.</span><span class="sxs-lookup"><span data-stu-id="8ba02-130">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="8ba02-131">Laden von Dateien in einem einzigen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="8ba02-131">Load from files in a single directory</span></span>

<span data-ttu-id="8ba02-132">Wenn sich alle Ihre Datendateien im gleichen Verzeichnis befinden, verwenden Sie in der [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*)-Methode Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="8ba02-132">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="8ba02-133">Laden von Dateien in mehreren Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="8ba02-133">Load from files in multiple directories</span></span>

<span data-ttu-id="8ba02-134">Um Daten aus mehreren Verzeichnissen zu laden, verwenden Sie die [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*)-Methode, um einen [`TextLoader`](xref:Microsoft.ML.Data.TextLoader) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8ba02-134">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="8ba02-135">Verwenden Sie dann die [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*)-Methode, und geben Sie die einzelnen Dateipfade an (Platzhalter können nicht verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="8ba02-135">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a><span data-ttu-id="8ba02-136">Laden von Daten aus einer relationalen Datenbank</span><span class="sxs-lookup"><span data-stu-id="8ba02-136">Load data from a relational database</span></span>

> [!NOTE]
> <span data-ttu-id="8ba02-137">DatabaseLoader befindet sich derzeit in der Vorschauphase.</span><span class="sxs-lookup"><span data-stu-id="8ba02-137">DatabaseLoader is currently in preview.</span></span> <span data-ttu-id="8ba02-138">Sie kann verwendet werden, indem Sie auf die NuGet-Pakete [Microsoft.ML.Experimental](https://www.nuget.org/packages/Microsoft.ML.Experimental/0.16.0-preview) und [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient/4.6.1) verweisen.</span><span class="sxs-lookup"><span data-stu-id="8ba02-138">It can be used by referencing the [Microsoft.ML.Experimental](https://www.nuget.org/packages/Microsoft.ML.Experimental/0.16.0-preview) and [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient/4.6.1) NuGet packages.</span></span>

<span data-ttu-id="8ba02-139">ML.NET unterstützt das Laden von Daten aus einer Vielzahl von relationalen Datenbanken, die von [`System.Data`](xref:System.Data) unterstützt werden, darunter SQL Server, Azure SQL-Datenbank, Oracle, SQLite, PostgreSQL, Progress, IBM DB2 und viele mehr.</span><span class="sxs-lookup"><span data-stu-id="8ba02-139">ML.NET supports loading data from a variety of relational databases supported by [`System.Data`](xref:System.Data) that include SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2, and many more.</span></span>

<span data-ttu-id="8ba02-140">Bei einer Datenbank mit einer Tabelle mit dem Namen `House` und dem folgenden Schema:</span><span class="sxs-lookup"><span data-stu-id="8ba02-140">Given a database with a table named `House` and the following schema:</span></span>

```SQL
CREATE TABLE [House] (
    [HouseId] int NOT NULL IDENTITY,
    [Size] real NOT NULL,
    [Price] real NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

<span data-ttu-id="8ba02-141">Die Daten können durch eine Klasse wie `HouseData` modelliert werden.</span><span class="sxs-lookup"><span data-stu-id="8ba02-141">The data can be modeled by a class like `HouseData`.</span></span>

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float Price { get; set; }
}
```

<span data-ttu-id="8ba02-142">Erstellen Sie dann in der Anwendung eine `DatabaseLoader`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8ba02-142">Then, inside of your application, create a `DatabaseLoader`.</span></span>

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

<span data-ttu-id="8ba02-143">Definieren Sie die Verbindungszeichenfolge sowie den SQL-Befehl, der für die Datenbank ausgeführt werden soll, und erstellen Sie eine `DatabaseSource`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="8ba02-143">Define your connection string as well as the SQL command to be executed on the database and create a `DatabaseSource` instance.</span></span> <span data-ttu-id="8ba02-144">Dieses Beispiel verwendet eine LocalDB-SQL Server-Datenbank mit einem Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="8ba02-144">This sample uses a LocalDB SQL Server database with a file path.</span></span> <span data-ttu-id="8ba02-145">DatabaseLoader unterstützt jedoch jede andere gültige Verbindungszeichenfolge für lokale Datenbanken und Clouddatenbanken.</span><span class="sxs-lookup"><span data-stu-id="8ba02-145">However, DatabaseLoader supports any other valid connection string for databases on-premises and in the cloud.</span></span>

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size,Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance,connectionString,sqlCommand);
```

<span data-ttu-id="8ba02-146">Verwenden Sie schließlich die `Load`-Methode, um die Daten in eine [`IDataView`](xref:Microsoft.ML.IDataView)-Schnittstelle zu laden.</span><span class="sxs-lookup"><span data-stu-id="8ba02-146">Finally, use the `Load` method to load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="8ba02-147">Laden von Daten aus anderen Quellen</span><span class="sxs-lookup"><span data-stu-id="8ba02-147">Load data from other sources</span></span>

<span data-ttu-id="8ba02-148">Zusätzlich zum Laden von Daten, die in Dateien gespeichert sind, unterstützt ML.NET das Laden von Daten aus verschiedenen Quellen, wie zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8ba02-148">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="8ba02-149">In-Memory-Sammlungen</span><span class="sxs-lookup"><span data-stu-id="8ba02-149">In-memory collections</span></span>
- <span data-ttu-id="8ba02-150">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="8ba02-150">JSON/XML</span></span>

<span data-ttu-id="8ba02-151">Beachten Sie, dass ML.NET bei der Arbeit mit Streamingquellen erwartet, dass die Eingabe in Form einer In-Memory-Sammlung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8ba02-151">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="8ba02-152">Achten Sie daher bei der Arbeit mit Quellen wie JSON/XML darauf, die Daten in eine In-Memory-Sammlung zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="8ba02-152">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="8ba02-153">Schauen Sie sich die folgende in-Memory-Sammlung an:</span><span class="sxs-lookup"><span data-stu-id="8ba02-153">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="8ba02-154">Laden Sie die in-Memory-Sammlung mit der [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)-Methode in eine [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="8ba02-154">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ba02-155">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) geht davon aus, dass das [`IEnumerable`](xref:System.Collections.IEnumerable)-Element, aus dem es geladen wird, threadsicher ist.</span><span class="sxs-lookup"><span data-stu-id="8ba02-155">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
