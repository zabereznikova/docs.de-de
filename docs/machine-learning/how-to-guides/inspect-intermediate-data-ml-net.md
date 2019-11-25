---
title: Untersuchen von Zwischendaten bei der ML.NET-Verarbeitung
description: Erfahren Sie, wie Sie Zwischendaten während des Ladens der ML.NET Machine Learning-Pipline, des Verarbeitens und Trainings des Modells in ML.NET überprüfen können.
ms.date: 06/25/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 11df1d5caaa7b7974360d863f85afbff18985e47
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977089"
---
# <a name="inspect-intermediate-data-during-processing"></a><span data-ttu-id="4de33-103">Untersuchen von Zwischendaten bei der Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="4de33-103">Inspect intermediate data during processing</span></span>

<span data-ttu-id="4de33-104">Erfahren Sie, wie Sie Zwischendaten während des Ladens, Verarbeitens und Trainings des Modells in ML.NET überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="4de33-104">Learn how to inspect intermediate data during loading, processing, and model training steps in ML.NET.</span></span> <span data-ttu-id="4de33-105">Zwischendaten werden in den einzelnen Phasen in der Machine learning-Pipeline ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="4de33-105">Intermediate data is the output of each stage in the machine learning pipeline.</span></span>

<span data-ttu-id="4de33-106">Zwischendaten, wie die unten dargestellten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden, können in ML.NET auf verschiedene Weise überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="4de33-106">Intermediate data like the one represented below which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView) can be inspected in various ways in ML.NET.</span></span>

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

## <a name="convert-idataview-to-ienumerable"></a><span data-ttu-id="4de33-107">Konvertieren von IDataView in IEnumerable</span><span class="sxs-lookup"><span data-stu-id="4de33-107">Convert IDataView to IEnumerable</span></span>

<span data-ttu-id="4de33-108">Eine der schnellsten Möglichkeiten, eine [`IDataView`](xref:Microsoft.ML.IDataView) zu überprüfen, ist die Konvertierung in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span><span class="sxs-lookup"><span data-stu-id="4de33-108">One of the quickest ways to inspect an [`IDataView`](xref:Microsoft.ML.IDataView) is to convert it to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span> <span data-ttu-id="4de33-109">Zum Konvertieren einer [`IDataView`](xref:Microsoft.ML.IDataView) in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) verwenden Sie die [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode.</span><span class="sxs-lookup"><span data-stu-id="4de33-109">To convert an [`IDataView`](xref:Microsoft.ML.IDataView) to [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) use the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

<span data-ttu-id="4de33-110">Um die Leistung zu optimieren, legen Sie den Wert von `reuseRowObject` auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="4de33-110">To optimize performance, set `reuseRowObject` to `true`.</span></span> <span data-ttu-id="4de33-111">Dadurch wird das gleiche Objekt bei der Auswertung verzögert mit den Daten der aktuellen Zeile ausgefüllt, anstatt für jede Zeile im Dataset ein neues Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4de33-111">Doing so will lazily populate the same object with the data of the current row as it's being evaluated as opposed to creating a new object for each row in the dataset.</span></span>

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

## <a name="accessing-specific-indices-with-ienumerable"></a><span data-ttu-id="4de33-112">Zugreifen auf bestimmte Indizes mit IEnumerable</span><span class="sxs-lookup"><span data-stu-id="4de33-112">Accessing specific indices with IEnumerable</span></span>

<span data-ttu-id="4de33-113">Wenn Sie nur Zugriff auf einen Teil der Daten oder bestimmte Indizes benötigen, verwenden Sie [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) und setzen Sie den Parameterwert `reuseRowObject` auf `false`, damit für jede der angeforderten Zeilen im Dataset ein neues Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4de33-113">If you only need access to a portion of the data or specific indices, use [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) and set the `reuseRowObject` parameter value to `false` so a new object is created for each of the requested rows in the dataset.</span></span> <span data-ttu-id="4de33-114">Konvertieren Sie [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) anschließend in ein Array oder eine Liste.</span><span class="sxs-lookup"><span data-stu-id="4de33-114">Then, convert the [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) to an array or list.</span></span>

> [!WARNING]
> <span data-ttu-id="4de33-115">Durch die Konvertierung des Ergebnisses von [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) in ein Array oder eine Liste werden alle angeforderten [`IDataView`](xref:Microsoft.ML.IDataView)-Zeilen in den Speicher geladen, wodurch die Leistung beeinträchtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4de33-115">Converting the result of [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) to an array or list will load all the requested [`IDataView`](xref:Microsoft.ML.IDataView) rows into memory which may affect performance.</span></span>

<span data-ttu-id="4de33-116">Nachdem die Sammlung erstellt wurde, können Sie Vorgänge für die Daten ausführen.</span><span class="sxs-lookup"><span data-stu-id="4de33-116">Once the collection has been created, you can perform operations on the data.</span></span> <span data-ttu-id="4de33-117">Der folgende Codeausschnitt umfasst die ersten drei Zeilen des Datasets und berechnet den durchschnittlichen aktuellen Preis.</span><span class="sxs-lookup"><span data-stu-id="4de33-117">The code snippet below takes the first three rows in the dataset and calculates the average current price.</span></span>

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

## <a name="inspect-values-in-a-single-column"></a><span data-ttu-id="4de33-118">Überprüfen von Werten in einer einzelnen Spalte</span><span class="sxs-lookup"><span data-stu-id="4de33-118">Inspect values in a single column</span></span>

<span data-ttu-id="4de33-119">Mit der [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*)-Methode kann zu jedem beliebigen Zeitpunkt im Modellerstellungsprozess auf Werte in einer einzelnen Spalte einer [`IDataView`](xref:Microsoft.ML.IDataView) zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="4de33-119">At any point in the model building process, values in a single column of an [`IDataView`](xref:Microsoft.ML.IDataView) can be accessed using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span> <span data-ttu-id="4de33-120">Die [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*)-Methode gibt alle Werte in einer einzelne Spalte als [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) wieder.</span><span class="sxs-lookup"><span data-stu-id="4de33-120">The [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method returns all of the values in a single column as an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span>

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a><span data-ttu-id="4de33-121">Zeilenweises Überprüfen von IDataView-Werten</span><span class="sxs-lookup"><span data-stu-id="4de33-121">Inspect IDataView values one row at a time</span></span>

<span data-ttu-id="4de33-122">[`IDataView`](xref:Microsoft.ML.IDataView) wird verzögert ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4de33-122">[`IDataView`](xref:Microsoft.ML.IDataView) is lazily evaluated.</span></span> <span data-ttu-id="4de33-123">Um die Zeilen einer [`IDataView`](xref:Microsoft.ML.IDataView) zu durchlaufen, ohne die Konvertierung in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) durchzuführen, wie in den vorangegangenen Abschnitten dieses Dokuments demonstriert, erstellen Sie ein [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) unter Verwendung der [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*)-Methode, und übergeben Sie das [DataViewSchema](xref:Microsoft.ML.DataViewSchema) Ihrer [`IDataView`](xref:Microsoft.ML.IDataView) als Parameter.</span><span class="sxs-lookup"><span data-stu-id="4de33-123">To iterate over the rows of an [`IDataView`](xref:Microsoft.ML.IDataView) without converting to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) as demonstrated in previous sections of this document, create a [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) by using the [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) method and passing in the [DataViewSchema](xref:Microsoft.ML.DataViewSchema) of your [`IDataView`](xref:Microsoft.ML.IDataView) as a parameter.</span></span> <span data-ttu-id="4de33-124">Um Zeilen zu durchlaufen, verwenden Sie die [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*)-Cursormethode zusammen mit [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601)-Delegaten, um die entsprechenden Werte aus einzelnen Spalten zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="4de33-124">Then, to iterate over rows, use the [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) cursor method along with [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) delegates to extract the respective values from each of the columns.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4de33-125">Aus Leistungsgründen verwenden Vektoren in ML.NET [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) anstelle von nativen Sammlungstypen (d.h. `Vector`,`float[]`).</span><span class="sxs-lookup"><span data-stu-id="4de33-125">For performance purposes, vectors in ML.NET use [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) instead of native collection types (that is, `Vector`,`float[]`).</span></span>

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

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a><span data-ttu-id="4de33-126">Anzeigen einer Vorschau des Ergebnisses der Vorverarbeitung oder des Trainings für eine Teilmenge der Daten</span><span class="sxs-lookup"><span data-stu-id="4de33-126">Preview result of pre-processing or training on a subset of the data</span></span>

> [!WARNING]
> <span data-ttu-id="4de33-127">Verwenden Sie `Preview` nicht im Produktionscode, da dies für das Debugging vorgesehen ist und die Leistung beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="4de33-127">Do not use `Preview` in production code because it is intended for debugging and may reduce performance.</span></span>

<span data-ttu-id="4de33-128">Der Modellerstellungsprozess ist experimentell und iterativ.</span><span class="sxs-lookup"><span data-stu-id="4de33-128">The model building process is experimental and iterative.</span></span> <span data-ttu-id="4de33-129">Um eine Vorschau anzuzeigen, wie die Daten nach der Vorverarbeitung oder dem Training eines Machine Learning-Modells für eine Teilmenge der Daten aussehen würden, verwenden Sie die [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*)-Methode, die ein [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4de33-129">To preview what data would look like after pre-processing or training a machine learning model on a subset of the data, use the [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) method which returns a [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span></span> <span data-ttu-id="4de33-130">Das Ergebnis ist ein Objekt mit den Eigenschaften `ColumnView` und `RowView`, die beide ein [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) sind und die Werte aus einer bestimmten Spalte oder Zeile enthalten.</span><span class="sxs-lookup"><span data-stu-id="4de33-130">The result is an object with `ColumnView` and `RowView` properties which are both an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) and contain the values in a particular column or row.</span></span> <span data-ttu-id="4de33-131">Geben Sie die Anzahl der Zeilen an, auf die die Transformation mit dem `maxRows`-Parameter angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4de33-131">Specify the number of rows to apply the transformation to with the `maxRows` parameter.</span></span>

![Vorschauobjekt für den Datendebugger](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

<span data-ttu-id="4de33-133">Das Ergebnis der Überprüfung einer [`IDataView`](xref:Microsoft.ML.IDataView) würde etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4de33-133">The result of inspecting an [`IDataView`](xref:Microsoft.ML.IDataView) would look similar to the following:</span></span>

![Vorschau des Datendebuggers – Zeilenansicht](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
