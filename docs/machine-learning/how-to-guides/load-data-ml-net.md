---
title: Laden von Daten aus Dateien und anderen Quellen
description: Diese Anleitung zeigt Ihnen, wie Sie Daten für die Verarbeitung und das Training in ML.NET laden. Die Daten werden ursprünglich in Dateien oder anderen Datenquellen wie Datenbanken, JSON, XML oder In-Memory-Sammlungen gespeichert.
ms.date: 06/25/2019
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: fafbe3fed9e3f0b509eda4f9d8967965bde19767
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397749"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="2c830-104">Laden von Daten aus Dateien und anderen Quellen</span><span class="sxs-lookup"><span data-stu-id="2c830-104">Load data from files and other sources</span></span>

<span data-ttu-id="2c830-105">Diese Anleitung zeigt Ihnen, wie Sie Daten für die Verarbeitung und das Training in ML.NET laden.</span><span class="sxs-lookup"><span data-stu-id="2c830-105">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="2c830-106">Die Daten werden ursprünglich in Dateien oder anderen Datenquellen wie Datenbanken, JSON, XML oder In-Memory-Sammlungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2c830-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="2c830-107">Erstellen des Datenmodells</span><span class="sxs-lookup"><span data-stu-id="2c830-107">Create the data model</span></span>

<span data-ttu-id="2c830-108">Mit ML.NET können Sie Datenmodelle über Klassen definieren.</span><span class="sxs-lookup"><span data-stu-id="2c830-108">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="2c830-109">Nehmen wir zum Beispiel die folgenden Eingabedaten:</span><span class="sxs-lookup"><span data-stu-id="2c830-109">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="2c830-110">Erstellen Sie ein Datenmodell, das den folgenden Codeausschnitt darstellt:</span><span class="sxs-lookup"><span data-stu-id="2c830-110">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="2c830-111">Kommentieren des Datenmodells mit Spaltenattributen</span><span class="sxs-lookup"><span data-stu-id="2c830-111">Annotating the data model with column attributes</span></span>

<span data-ttu-id="2c830-112">Attribute geben ML.NET mehr Informationen über das Datenmodell und die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="2c830-112">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="2c830-113">Das [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)-Attribut gibt die Spaltenindizes Ihrer Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="2c830-113">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c830-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) ist nur erforderlich, wenn Daten aus einer Datei geladen werden.</span><span class="sxs-lookup"><span data-stu-id="2c830-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="2c830-115">Spalten werden folgendermaßen geladen:</span><span class="sxs-lookup"><span data-stu-id="2c830-115">Load columns as:</span></span> 
- <span data-ttu-id="2c830-116">Als Einzelspalten, wie `Size` und `CurrentPrices` in der `HousingData`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2c830-116">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="2c830-117">In mehreren Spalten gleichzeitig in Form eines Vektors wie `HistoricalPrices` in der `HousingData`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2c830-117">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="2c830-118">Wenn Sie eine Vektoreigenschaft haben, wenden Sie das [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute)-Attribut auf die Eigenschaft in Ihrem Datenmodell an.</span><span class="sxs-lookup"><span data-stu-id="2c830-118">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="2c830-119">Dabei ist zu beachten, dass alle Elemente im Vektor vom gleichen Typ sein müssen.</span><span class="sxs-lookup"><span data-stu-id="2c830-119">It's important to note that all of the elements in the vector need to be the same type.</span></span>

<span data-ttu-id="2c830-120">ML.NET arbeitet mit Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="2c830-120">ML.NET Operates through column names.</span></span> <span data-ttu-id="2c830-121">Wenn die Spalte einen anderen Namen als den Eigenschaftsnamen haben soll, verwenden Sie das [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute)-Attribut.</span><span class="sxs-lookup"><span data-stu-id="2c830-121">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="2c830-122">Beim Erstellen von In-Memory-Objekten erstellen Sie Objekte weiterhin unter Verwendung des Eigenschaftsnamens.</span><span class="sxs-lookup"><span data-stu-id="2c830-122">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="2c830-123">Für die Datenverarbeitung und die Erstellung von Machine Learning-Modellen überschreibt und referenziert ML.NET jedoch die Eigenschaft mit dem im [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute)-Attribut angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="2c830-123">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="2c830-124">Laden von Daten aus einer Einzeldatei</span><span class="sxs-lookup"><span data-stu-id="2c830-124">Load data from a single file</span></span>

<span data-ttu-id="2c830-125">Um Daten aus einer Datei zu laden, verwenden Sie die [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*)-Methode zusammen mit dem Datenmodell für die zu ladenden Daten.</span><span class="sxs-lookup"><span data-stu-id="2c830-125">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="2c830-126">Da der `separatorChar`-Parameter standardmäßig mit Tabstopptrennzeichen getrennt ist, ändern Sie ihn bei Bedarf für Ihre Datendatei.</span><span class="sxs-lookup"><span data-stu-id="2c830-126">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="2c830-127">Wenn Ihre Datei einen Header hat, setzen Sie den `hasHeader`-Parameter auf `true`, um die erste Zeile in der Datei zu ignorieren und mit dem Laden von Daten aus der zweiten Zeile zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="2c830-127">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="2c830-128">Laden von Daten aus mehreren Dateien</span><span class="sxs-lookup"><span data-stu-id="2c830-128">Load data from multiple files</span></span>

<span data-ttu-id="2c830-129">Wenn Ihre Daten in mehreren Dateien gespeichert sind, können Sie mit ML.NET Daten aus mehreren Dateien laden, die sich entweder im gleichen Verzeichnis oder in mehreren Verzeichnissen befinden, solange das Datenschema gleich ist.</span><span class="sxs-lookup"><span data-stu-id="2c830-129">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="2c830-130">Laden von Dateien in einem einzigen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="2c830-130">Load from files in a single directory</span></span>

<span data-ttu-id="2c830-131">Wenn sich alle Ihre Datendateien im gleichen Verzeichnis befinden, verwenden Sie in der [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*)-Methode Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="2c830-131">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="2c830-132">Laden von Dateien in mehreren Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="2c830-132">Load from files in multiple directories</span></span>

<span data-ttu-id="2c830-133">Um Daten aus mehreren Verzeichnissen zu laden, verwenden Sie die [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*)-Methode, um einen [`TextLoader`](xref:Microsoft.ML.Data.TextLoader) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c830-133">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="2c830-134">Verwenden Sie dann die [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*)-Methode, und geben Sie die einzelnen Dateipfade an (Platzhalter können nicht verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="2c830-134">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="2c830-135">Laden von Daten aus anderen Quellen</span><span class="sxs-lookup"><span data-stu-id="2c830-135">Load data from other sources</span></span>

<span data-ttu-id="2c830-136">Zusätzlich zum Laden von Daten, die in Dateien gespeichert sind, unterstützt ML.NET das Laden von Daten aus verschiedenen Quellen, wie zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2c830-136">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="2c830-137">In-Memory-Sammlungen</span><span class="sxs-lookup"><span data-stu-id="2c830-137">In-memory collections</span></span>
- <span data-ttu-id="2c830-138">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="2c830-138">JSON/XML</span></span>
- <span data-ttu-id="2c830-139">Databases</span><span class="sxs-lookup"><span data-stu-id="2c830-139">Databases</span></span>

<span data-ttu-id="2c830-140">Beachten Sie, dass ML.NET bei der Arbeit mit Streamingquellen erwartet, dass die Eingabe in Form einer In-Memory-Sammlung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2c830-140">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="2c830-141">Achten Sie daher bei der Arbeit mit Quellen wie JSON/XML darauf, die Daten in eine In-Memory-Sammlung zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="2c830-141">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="2c830-142">Schauen Sie sich die folgende in-Memory-Sammlung an:</span><span class="sxs-lookup"><span data-stu-id="2c830-142">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="2c830-143">Laden Sie die in-Memory-Sammlung mit der [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)-Methode in eine [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="2c830-143">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
