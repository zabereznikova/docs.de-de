---
title: Abfragen von typisierten DataSets
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 55714c4dae73cd17a849cc35681797dfa4266e3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782967"
---
# <a name="query-typed-datasets"></a>Abfragen von typisierten Datasets

Wenn das Schema <xref:System.Data.DataSet> der zum Zeitpunkt der Anwendungs Entwurfszeit bekannt ist, empfiehlt es sich, bei Verwendung <xref:System.Data.DataSet> von LINQ to DataSet eine typisierte zu verwenden. Ein typisierter <xref:System.Data.DataSet> ist eine Klasse, die von <xref:System.Data.DataSet>einem abgeleitet ist. Damit erbt sie alle Methoden, Ereignisse und Eigenschaften eines <xref:System.Data.DataSet>. Darüber hinaus stellt ein <xref:System.Data.DataSet> typisiertes stark typisierte Methoden, Ereignisse und Eigenschaften bereit. Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen. Dadurch werden Abfragen einfacher und lesbarer. Weitere Informationen finden Sie unter [typisierte Datasets](./dataset-datatable-dataview/typed-datasets.md).

LINQ to DataSet unterstützt auch das Abfragen über ein <xref:System.Data.DataSet>typisiertes. Bei einem typisierten <xref:System.Data.DataSet>müssen Sie die generische <xref:System.Data.DataRowExtensions.Field%2A> Methode oder <xref:System.Data.DataRowExtensions.SetField%2A> Methode nicht verwenden, um auf Spaltendaten zuzugreifen. Eigenschaftsnamen sind zum Zeitpunkt der Kompilierung verfügbar, da die Typinformationen <xref:System.Data.DataSet>in enthalten sind. LINQ to DataSet bietet Zugriff auf Spaltenwerte als korrekten Typ, sodass Typen Konflikt Fehler abgefangen werden, wenn der Code statt zur Laufzeit kompiliert wird.

Bevor Sie mit dem Abfragen eines typisierten <xref:System.Data.DataSet>beginnen können, müssen Sie die-Klasse mithilfe des **DataSet-Designers** in Visual Studio generieren. Weitere Informationen finden Sie unter [Erstellen und Konfigurieren von Datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Abfrage von Daten in einem typisierten <xref:System.Data.DataSet> veranschaulicht:

```csharp
var query = from o in orders
            where o.OnlineOrderFlag == true
            select new { o.SalesOrderID,
                         o.OrderDate,
                         o.SalesOrderNumber };

foreach(var order in query)
{
    Console.WriteLine("{0}\t{1:d}\t{2}",
      order.SalesOrderID,
      order.OrderDate,
      order.SalesOrderNumber);
}
```

```vb
Dim orders = ds.Tables("SalesOrderHeader")

Dim query = _
       From o In orders _
       Where o.OnlineOrderFlag = True _
       Select New {SalesOrderID := o.SalesOrderID, _
                   OrderDate := o.OrderDate, _
                   SalesOrderNumber := o.SalesOrderNumber}

For Each Dim onlineOrder In query
 Console.WriteLine("{0}\t{1:d}\t{2}", _
 onlineOrder.SalesOrderID, _
 onlineOrder.OrderDate, _
 onlineOrder.SalesOrderNumber)
Next
```

## <a name="see-also"></a>Siehe auch

- [Abfragen von DataSets](querying-datasets-linq-to-dataset.md)
- [Tabellenübergreifende Abfragen](cross-table-queries-linq-to-dataset.md)
- [Abfragen für einzelne Tabellen](single-table-queries-linq-to-dataset.md)
