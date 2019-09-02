---
title: Anzeigen von Daten in einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: ea92b8a5e46bdaa8e94756cd28a3fbcb2789d7b3
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204389"
---
# <a name="viewing-data-in-a-datatable"></a>Anzeigen von Daten in einer "DataTable"

Sie können <xref:System.Data.DataTable> auf den Inhalt eines-Objekts zugreifen, indem Sie die **Zeilen** -und **Spalten** Auflistungen der **Daten**Tabelle verwenden. Sie können auch die <xref:System.Data.DataTable.Select%2A> -Methode verwenden, um Teilmengen der Daten in einer Datentabelle nach Kriterien, einschließlich Suchkriterien, Sortierreihenfolge und Zeilen Status, zurückzugeben. Darüber hinaus können Sie die <xref:System.Data.DataRowCollection.Find%2A> -Methode der **DataRowCollection** verwenden, wenn Sie mithilfe eines Primärschlüssel Werts eine bestimmte Zeile suchen.

Die **Select** -Methode des **Daten** Tabelle-Objekts gibt eine Gruppe <xref:System.Data.DataRow> von-Objekten zurück, die den angegebenen Kriterien entsprechen. **Select** führt optionale Argumente eines Filter Ausdrucks, eines Sortierungs Ausdrucks und von **DataViewRowState**aus. Der Filter Ausdruck identifiziert, welche Zeilen basierend auf **datacolenumn** -Werten zurückgegeben werden `LastName = 'Smith'`, z. b. Der Sortierausdruck folgt den Standard-SQL-Konventionen für die Anordnung von Spalten, z. B. `LastName ASC, FirstName ASC`. Regeln zum Schreiben von Ausdrücken finden Sie unter <xref:System.Data.DataColumn.Expression%2A> der-Eigenschaft der **datacolenumn** -Klasse.

> [!TIP]
> Wenn Sie eine Reihe von Aufrufen der **Select** -Methode einer **Daten**Tabelle ausführen, können Sie die Leistung steigern, indem Sie zuerst einen <xref:System.Data.DataView> für die **Daten**Tabelle erstellen. Beim Erstellen der **DataView** werden die Zeilen der Tabelle indiziert. Die **Select** -Methode verwendet dann diesen Index, wodurch die Zeit zum Generieren des Abfrage Ergebnisses erheblich reduziert wird. Weitere Informationen zum Erstellen einer **DataView** für eine **Daten**Tabelle finden Sie unter [DataViews](dataviews.md).

Die **Select** -Methode bestimmt, welche Version der Zeilen basierend auf einem <xref:System.Data.DataViewRowState>angezeigt oder bearbeitet werden soll. In der folgenden Tabelle werden die möglichen **DataViewRowState** -Enumerationswerte beschrieben.

|"DataViewRowState"-Wert|Beschreibung|
|----------------------------|-----------------|
|**CurrentRows**|Aktuelle Zeilen, einschließlich nicht geänderter, hinzugefügter und geänderter Zeilen.|
|**Lö**|Eine gelöschte Zeile.|
|**ModifiedCurrent**|Eine aktuelle Version, die eine geänderte Version der ursprünglichen Daten darstellt. (Siehe **ModifiedOriginal**.)|
|**ModifiedOriginal**|Die ursprüngliche Version aller geänderten Zeilen. Die aktuelle Version ist mit **ModifiedCurrent**verfügbar.|
|**Hinzugefügt**|Eine neue Zeile.|
|**Keine**|Keine|
|**OriginalRows**|Ursprüngliche Zeilen, einschließlich nicht geänderter und gelöschter Zeilen.|
|**Unverändert**|Eine nicht geänderte Zeile.|

Im folgenden Beispiel wird das **DataSet** -Objekt so gefiltert, dass Sie nur mit Zeilen arbeiten, deren **DataViewRowState** auf **CurrentRows**festgelegt ist.

```vb
Dim column As DataColumn
Dim row As DataRow

Dim currentRows() As DataRow = _
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)

If (currentRows.Length < 1 ) Then
  Console.WriteLine("No Current Rows Found")
Else
  For Each column in workTable.Columns
    Console.Write(vbTab & column.ColumnName)
  Next

  Console.WriteLine(vbTab & "RowState")

  For Each row In currentRows
    For Each column In workTable.Columns
      Console.Write(vbTab & row(column).ToString())
    Next

    Dim rowState As String = _
        System.Enum.GetName(row.RowState.GetType(), row.RowState)
    Console.WriteLine(vbTab & rowState)
  Next
End If
```

```csharp
DataRow[] currentRows = workTable.Select(
    null, null, DataViewRowState.CurrentRows);

if (currentRows.Length < 1 )
  Console.WriteLine("No Current Rows Found");
else
{
  foreach (DataColumn column in workTable.Columns)
    Console.Write("\t{0}", column.ColumnName);

  Console.WriteLine("\tRowState");

  foreach (DataRow row in currentRows)
  {
    foreach (DataColumn column in workTable.Columns)
      Console.Write("\t{0}", row[column]);

    Console.WriteLine("\t" + row.RowState);
  }
}
```

Die **Select** -Methode kann verwendet werden, um Zeilen mit unterschiedlichen **RowState** -Werten oder Feldwerten zurückzugeben. Im folgenden Beispiel wird ein **DataRow** -Array zurückgegeben, das auf alle gelöschten Zeilen verweist, und es wird ein weiteres **DataRow** -Array zurückgegeben, das auf alle Zeilen verweist, geordnet nach **CustLName**, wobei die **CustId-** Spalte größer als 5 ist. Informationen dazu, wie Sie die Informationen in der **gelöschten** Zeile anzeigen, finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).

```vb
' Retrieve all deleted rows.
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)

' Retrieve rows where CustID > 5, and order by CustLName.
Dim custRows() As DataRow = workTable.Select( _
    "CustID > 5", "CustLName ASC")
```

```csharp
// Retrieve all deleted rows.
DataRow[] deletedRows = workTable.Select(
    null, null, DataViewRowState.Deleted);

// Retrieve rows where CustID > 5, and order by CustLName.
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [Bearbeiten von Daten in einer DataTable](manipulating-data-in-a-datatable.md)
- [Zeilenstatus und Zeilenversionen](row-states-and-row-versions.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
