---
title: Untersuchen von Zwischendatenwerten bei der ML.NET-Verarbeitung
description: Lernen Sie, wie Sie die tatsächlichen Zwischendatenwerte bei der Verarbeitung der Pipeline für maschinelles Lernen mit ML.NET untersuchen können.
ms.date: 04/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 06c4a473841db62a10dfc24025f842df7ae2c583
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063516"
---
# <a name="inspect-intermediate-data-values-during-processing"></a><span data-ttu-id="63a28-103">Untersuchen von Zwischendatenwerten bei der Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="63a28-103">Inspect intermediate data values during processing</span></span>

<span data-ttu-id="63a28-104">Erfahren Sie, wie Sie Werte während des Ladens, Verarbeitens und Trainings in ML.NET überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="63a28-104">Learn how to inspect values during loading, processing and training steps in ML.NET.</span></span>

<span data-ttu-id="63a28-105">Daten wie die unten dargestellten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden, können in ML.NET auf verschiedene Weise überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="63a28-105">Data like the one represented below which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView) can be inspected in various ways in ML.NET.</span></span>
 
```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

## <a name="convert-idataview-to-ienumerable"></a><span data-ttu-id="63a28-106">Konvertieren von IDataView in IEnumerable</span><span class="sxs-lookup"><span data-stu-id="63a28-106">Convert IDataView to IEnumerable</span></span>

<span data-ttu-id="63a28-107">Eine der schnellsten Möglichkeiten, die Werte einer [`IDataView`](xref:Microsoft.ML.IDataView) zu überprüfen, ist die Konvertierung in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span><span class="sxs-lookup"><span data-stu-id="63a28-107">One of the quickest ways to inspect the values of an [`IDataView`](xref:Microsoft.ML.IDataView) is to convert it to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span> <span data-ttu-id="63a28-108">Zum Konvertieren einer [`IDataView`](xref:Microsoft.ML.IDataView) in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) verwenden Sie die [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode.</span><span class="sxs-lookup"><span data-stu-id="63a28-108">To convert an [`IDataView`](xref:Microsoft.ML.IDataView) to [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) use the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span> 

<span data-ttu-id="63a28-109">Um die Leistung zu optimieren, legen Sie den Wert von `reuseRowObject` auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="63a28-109">To optimize performance, set the value of `reuseRowObject` to `true`.</span></span> <span data-ttu-id="63a28-110">Dadurch wird das gleiche Objekt bei der Auswertung verzögert mit den Daten der aktuellen Zeile ausgefüllt, anstatt für jede Zeile im Dataset ein neues Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="63a28-110">Doing so will lazily populate the same object with the data of the current row as it's being evaluated as opposed to creating a new object for each row in the dataset.</span></span>

```csharp
// Create an IEnumerable of HousingData objects from IDataView
IEnumerable<HousingData> housingDataEnumerable =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: true);

// Iterate over each row
foreach (HousingData row in housingDataEnumerable)
{
    // Do something (print out Size property) with current Housing Data object being evaluated
    Console.WriteLine(row.Size);
}
```

<span data-ttu-id="63a28-111">Wenn Sie nur Zugriff auf einen Teil der Daten oder bestimmte Indizes benötigen, verwenden Sie [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) und setzen Sie den Parameterwert `reuseRowObject` auf `false`, damit für jede der angeforderten Zeilen im Dataset ein neues Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="63a28-111">If you only need access to a portion of the data or specific indices, use [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) and set the `reuseRowObject` parameter value to `false` so a new object is created for each of the requested rows in the dataset.</span></span> <span data-ttu-id="63a28-112">Konvertieren Sie [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) anschließend in ein Array oder eine Liste.</span><span class="sxs-lookup"><span data-stu-id="63a28-112">Then, convert the [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) to an array or list.</span></span>

> [!WARNING]
> <span data-ttu-id="63a28-113">Durch die Konvertierung des Ergebnisses von [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) in ein Array oder eine Liste werden alle angeforderten [`IDataView`](xref:Microsoft.ML.IDataView)-Zeilen in den Speicher geladen, wodurch die Leistung beeinträchtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="63a28-113">Converting the result of [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) to an array or list will load all the requested [`IDataView`](xref:Microsoft.ML.IDataView) rows into memory which may affect performance.</span></span>

<span data-ttu-id="63a28-114">Nachdem die Sammlung erstellt wurde, können Sie Vorgänge für die Daten ausführen.</span><span class="sxs-lookup"><span data-stu-id="63a28-114">Once the collection has been created, you can perform operations on the data.</span></span> <span data-ttu-id="63a28-115">Der folgende Codeausschnitt umfasst die ersten drei Zeilen des Datasets und berechnet den durchschnittlichen aktuellen Preis.</span><span class="sxs-lookup"><span data-stu-id="63a28-115">The code snippet below takes the first three rows in the dataset and calculates the average current price.</span></span>

```csharp
// Create an Array of HousingData objects from IDataView
HousingData[] housingDataArray =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: false)
        .Take(3)
        .ToArray();

// Calculate Average CurrentPrice of First Three Elements
HousingData firstRow = housingDataArray[0];
HousingData secondRow = housingDataArray[1];
HousingData thirdRow = housingDataArray[2];
float averageCurrentPrice = (firstRow.CurrentPrice + secondRow.CurrentPrice + thirdRow.CurrentPrice) / 3;
``` 

## <a name="inspect-values-in-a-single-column"></a><span data-ttu-id="63a28-116">Überprüfen von Werten in einer einzelnen Spalte</span><span class="sxs-lookup"><span data-stu-id="63a28-116">Inspect values in a single column</span></span>

<span data-ttu-id="63a28-117">Mit der [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*)-Methode kann zu jedem beliebigen Zeitpunkt im Modellerstellungsprozess auf Werte in einer einzelnen Spalte einer [`IDataView`](xref:Microsoft.ML.IDataView) zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="63a28-117">At any point in the model building process, values in a single column of an [`IDataView`](xref:Microsoft.ML.IDataView) can be accessed using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span> <span data-ttu-id="63a28-118">Die [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*)-Methode gibt alle Werte in einer einzelne Spalte als [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) wieder.</span><span class="sxs-lookup"><span data-stu-id="63a28-118">The [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method returns all of the values in a single column as an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span>

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a><span data-ttu-id="63a28-119">Zeilenweises Überprüfen von IDataView-Werten</span><span class="sxs-lookup"><span data-stu-id="63a28-119">Inspect IDataView values one row at a time</span></span>

<span data-ttu-id="63a28-120">[`IDataView`](xref:Microsoft.ML.IDataView) wird verzögert ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="63a28-120">[`IDataView`](xref:Microsoft.ML.IDataView) is lazily evaluated.</span></span> <span data-ttu-id="63a28-121">Um die Zeilen einer [`IDataView`](xref:Microsoft.ML.IDataView) zu durchlaufen, ohne die Konvertierung in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) durchzuführen, wie in den vorangegangenen Abschnitten dieses Dokuments demonstriert, erstellen Sie ein [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) unter Verwendung der [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*)-Methode, und übergeben Sie das [DataViewSchema](xref:Microsoft.ML.DataViewSchema) Ihrer [`IDataView`](xref:Microsoft.ML.IDataView) als Parameter.</span><span class="sxs-lookup"><span data-stu-id="63a28-121">To iterate over the rows of an [`IDataView`](xref:Microsoft.ML.IDataView) without converting to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) as demonstrated in previous sections of this document, create a [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) by using the [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) method and passing in the [DataViewSchema](xref:Microsoft.ML.DataViewSchema) of your [`IDataView`](xref:Microsoft.ML.IDataView) as a parameter.</span></span> <span data-ttu-id="63a28-122">Um Zeilen zu durchlaufen, verwenden Sie die [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*)-Cursormethode zusammen mit [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601)-Delegaten, um die entsprechenden Werte aus einzelnen Spalten zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="63a28-122">Then, to iterate over rows, use the [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) cursor method along with [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) delegates to extract the respective values from each of the columns.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63a28-123">Aus Leistungsgründen verwenden Vektoren in ML.NET [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) anstelle von nativen Sammlungstypen (d.h. `Vector`,`float[]`).</span><span class="sxs-lookup"><span data-stu-id="63a28-123">For performance purposes, vectors in ML.NET use [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) instead of native collection types (that is, `Vector`,`float[]`).</span></span> 

```csharp
// Get DataViewSchema of IDataView
DataViewSchema columns = data.Schema;

// Create DataViewCursor
using (DataViewRowCursor cursor = data.GetRowCursor(columns))
{
    // Define variables where extracted values will be stored to
    float size = default;
    VBuffer<float> historicalPrices = default;
    float currentPrice = default;

    // Define delegates for extracting values from columns
    ValueGetter<float> sizeDelegate = cursor.GetGetter<float>(columns[0]);
    ValueGetter<VBuffer<float>> historicalPriceDelegate = cursor.GetGetter<VBuffer<float>>(columns[1]);
    ValueGetter<float> currentPriceDelegate = cursor.GetGetter<float>(columns[2]);
    
    // Iterate over each row
    while (cursor.MoveNext())
    {
        //Get values from respective columns
        sizeDelegate.Invoke(ref size);
        historicalPriceDelegate.Invoke(ref historicalPrices);
        currentPriceDelegate.Invoke(ref currentPrice);
    }
}
```

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a><span data-ttu-id="63a28-124">Anzeigen einer Vorschau des Ergebnisses der Vorverarbeitung oder des Trainings für eine Teilmenge der Daten</span><span class="sxs-lookup"><span data-stu-id="63a28-124">Preview result of pre-processing or training on a subset of the data</span></span>

> [!WARNING]
> <span data-ttu-id="63a28-125">Verwenden Sie `Preview` nicht im Produktionscode, da dies für das Debugging vorgesehen ist und die Leistung beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="63a28-125">Do not use `Preview` in production code because it is intended for debugging and may reduce performance.</span></span>

<span data-ttu-id="63a28-126">Der Modellerstellungsprozess ist experimentell und iterativ.</span><span class="sxs-lookup"><span data-stu-id="63a28-126">The model building process is experimental and iterative.</span></span> <span data-ttu-id="63a28-127">Um eine Vorschau anzuzeigen, wie die Daten nach der Vorverarbeitung oder dem Training eines Machine Learning-Modells für eine Teilmenge der Daten aussehen würden, verwenden Sie die [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*)-Methode, die ein [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="63a28-127">To preview what data would look like after pre-processing or training a machine learning model on a subset of the data, use the [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) method which returns a [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span></span> <span data-ttu-id="63a28-128">Das Ergebnis ist ein Objekt mit den Eigenschaften `ColumnView` und `RowView`, die beide ein [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) sind und die Werte aus einer bestimmten Spalte oder Zeile enthalten.</span><span class="sxs-lookup"><span data-stu-id="63a28-128">The result is an object with `ColumnView` and `RowView` properties which are both an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) and contain the values in a particular column or row.</span></span> <span data-ttu-id="63a28-129">Geben Sie die Anzahl der Zeilen an, auf die die Transformation mit dem `maxRows`-Parameter angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63a28-129">Specify the number of rows to apply the transformation to with the `maxRows` parameter.</span></span>

![Vorschauobjekt für den Datendebugger](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

<span data-ttu-id="63a28-131">Das Ergebnis der Überprüfung einer [`IDataView`](xref:Microsoft.ML.IDataView) würde etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="63a28-131">The result of inspecting an [`IDataView`](xref:Microsoft.ML.IDataView) would look similar to the following:</span></span>

![Vorschau des Datendebuggers – Zeilenansicht](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
