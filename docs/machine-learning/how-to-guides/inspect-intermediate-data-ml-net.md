---
title: Untersuchen von Zwischendaten bei der ML.NET-Verarbeitung
description: Erfahren Sie, wie Sie Zwischendaten während des Ladens der ML.NET Machine Learning-Pipline, des Verarbeitens und Trainings des Modells in ML.NET überprüfen können.
ms.date: 06/25/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 11df1d5caaa7b7974360d863f85afbff18985e47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73977089"
---
# <a name="inspect-intermediate-data-during-processing"></a>Untersuchen von Zwischendaten bei der Verarbeitung

Erfahren Sie, wie Sie Zwischendaten während des Ladens, Verarbeitens und Trainings des Modells in ML.NET überprüfen können. Zwischendaten werden in den einzelnen Phasen in der Machine learning-Pipeline ausgegeben.

Zwischendaten, wie die unten dargestellten, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden, können in ML.NET auf verschiedene Weise überprüft werden.

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

## <a name="convert-idataview-to-ienumerable"></a>Konvertieren von IDataView in IEnumerable

Eine der schnellsten Möglichkeiten, eine [`IDataView`](xref:Microsoft.ML.IDataView) zu überprüfen, ist die Konvertierung in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601). Zum Konvertieren einer [`IDataView`](xref:Microsoft.ML.IDataView) in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) verwenden Sie die [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*)-Methode.

Um die Leistung zu optimieren, legen Sie den Wert von `reuseRowObject` auf `true` fest. Dadurch wird das gleiche Objekt bei der Auswertung verzögert mit den Daten der aktuellen Zeile ausgefüllt, anstatt für jede Zeile im Dataset ein neues Objekt zu erstellen.

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

## <a name="accessing-specific-indices-with-ienumerable"></a>Zugreifen auf bestimmte Indizes mit IEnumerable

Wenn Sie nur Zugriff auf einen Teil der Daten oder bestimmte Indizes benötigen, verwenden Sie [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) und setzen Sie den Parameterwert `reuseRowObject` auf `false`, damit für jede der angeforderten Zeilen im Dataset ein neues Objekt erstellt wird. Konvertieren Sie [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) anschließend in ein Array oder eine Liste.

> [!WARNING]
> Durch die Konvertierung des Ergebnisses von [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) in ein Array oder eine Liste werden alle angeforderten [`IDataView`](xref:Microsoft.ML.IDataView)-Zeilen in den Speicher geladen, wodurch die Leistung beeinträchtigt werden kann.

Nachdem die Sammlung erstellt wurde, können Sie Vorgänge für die Daten ausführen. Der folgende Codeausschnitt umfasst die ersten drei Zeilen des Datasets und berechnet den durchschnittlichen aktuellen Preis.

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

## <a name="inspect-values-in-a-single-column"></a>Überprüfen von Werten in einer einzelnen Spalte

Mit der [`IDataView`](xref:Microsoft.ML.IDataView)-Methode kann zu jedem beliebigen Zeitpunkt im Modellerstellungsprozess auf Werte in einer einzelnen Spalte einer [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) zugegriffen werden. Die [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*)-Methode gibt alle Werte in einer einzelne Spalte als [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) wieder.

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a>Zeilenweises Überprüfen von IDataView-Werten

[`IDataView`](xref:Microsoft.ML.IDataView) wird verzögert ausgewertet. Um die Zeilen einer [`IDataView`](xref:Microsoft.ML.IDataView) zu durchlaufen, ohne die Konvertierung in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) durchzuführen, wie in den vorangegangenen Abschnitten dieses Dokuments demonstriert, erstellen Sie ein [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) unter Verwendung der [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*)-Methode, und übergeben Sie das [DataViewSchema](xref:Microsoft.ML.DataViewSchema) Ihrer [`IDataView`](xref:Microsoft.ML.IDataView) als Parameter. Um Zeilen zu durchlaufen, verwenden Sie die [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*)-Cursormethode zusammen mit [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601)-Delegaten, um die entsprechenden Werte aus einzelnen Spalten zu extrahieren.

> [!IMPORTANT]
> Aus Leistungsgründen verwenden Vektoren in ML.NET [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) anstelle von nativen Sammlungstypen (d.h. `Vector`,`float[]`).

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

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a>Anzeigen einer Vorschau des Ergebnisses der Vorverarbeitung oder des Trainings für eine Teilmenge der Daten

> [!WARNING]
> Verwenden Sie `Preview` nicht im Produktionscode, da dies für das Debugging vorgesehen ist und die Leistung beeinträchtigen kann.

Der Modellerstellungsprozess ist experimentell und iterativ. Um eine Vorschau anzuzeigen, wie die Daten nach der Vorverarbeitung oder dem Training eines Machine Learning-Modells für eine Teilmenge der Daten aussehen würden, verwenden Sie die [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*)-Methode, die ein [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview) zurückgibt. Das Ergebnis ist ein Objekt mit den Eigenschaften `ColumnView` und `RowView`, die beide ein [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) sind und die Werte aus einer bestimmten Spalte oder Zeile enthalten. Geben Sie die Anzahl der Zeilen an, auf die die Transformation mit dem `maxRows`-Parameter angewendet werden soll.

![Vorschauobjekt für den Datendebugger](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

Das Ergebnis der Überprüfung einer [`IDataView`](xref:Microsoft.ML.IDataView) würde etwa wie folgt aussehen:

![Vorschau des Datendebuggers – Zeilenansicht](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
