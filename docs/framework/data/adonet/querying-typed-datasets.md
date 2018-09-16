---
title: Abfragen von typisierten DataSets
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45685815"
---
# <a name="query-typed-datasets"></a>Abfragen von typisierten "DataSets"

Wenn das Schema der <xref:System.Data.DataSet> heißt Zeitpunkt der Anwendungskonzeptionierung, es wird empfohlen, dass Sie eine typisierte verwenden <xref:System.Data.DataSet> bei der Verwendung von LINQ to DataSet. Eine typisierte <xref:System.Data.DataSet> ist eine abgeleitete Klasse eine <xref:System.Data.DataSet>. Damit erbt sie alle Methoden, Ereignisse und Eigenschaften eines <xref:System.Data.DataSet>. Darüber hinaus eine typisierte <xref:System.Data.DataSet> stellt stark typisierte Methoden, Ereignisse und Eigenschaften bereit. Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen. Dadurch werden Abfragen einfacher und lesbarer. Weitere Informationen finden Sie unter [typisierter DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).

LINQ to DataSet ebenfalls unterstützt Abfragen von Daten in einem typisierten <xref:System.Data.DataSet>. Mit einer typisierten <xref:System.Data.DataSet>, Sie müssen nicht die generischen <xref:System.Data.DataRowExtensions.Field%2A> Methode oder <xref:System.Data.DataRowExtensions.SetField%2A> Methode, um Spaltendaten zugreifen zu können. Eigenschaftennamen sind zum Zeitpunkt der Kompilierung verfügbar, da die Typinformationen, in enthalten ist der <xref:System.Data.DataSet>. LINQ to DataSet bietet Zugriff auf Spaltenwerte als korrektem Typ, ein, sodass Typkonflikte abgefangen werden, wenn der Code statt zur Laufzeit kompiliert wird.

Bevor Sie beginnen können, eine typisierte Abfrage <xref:System.Data.DataSet>, müssen Sie die Klasse generieren, mit der **DataSet-Designer** in Visual Studio. Weitere Informationen finden Sie unter [erstellen und Konfigurieren von DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).

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

- [Abfragen von DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [Tabellenübergreifende Abfragen](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [Abfragen für einzelne Tabellen](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
