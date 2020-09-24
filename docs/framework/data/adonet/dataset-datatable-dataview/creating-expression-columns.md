---
title: Erstellen von Ausdrucksspalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: ad14e4d3d6a1107f994d9536485257f9dc1851f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166845"
---
# <a name="creating-expression-columns"></a>Erstellen von Ausdrucksspalten

Sie können einen Ausdruck für eine Spalte definieren, sodass diese einen Wert enthalten kann, der aus anderen Spaltenwerten in der gleichen Zeile oder aus Spaltenwerten mehrerer Zeilen in der Tabelle berechnet wurde. Wenn Sie den auszuwertenden Ausdruck definieren möchten, verwenden Sie die <xref:System.Data.DataColumn.Expression%2A>-Eigenschaft der Zielspalte und verweisen mithilfe der <xref:System.Data.DataColumn.ColumnName%2A>-Eigenschaft auf andere Spalten im Ausdruck. Der <xref:System.Data.DataColumn.DataType%2A> für die Ausdrucksspalte muss für den Wert geeignet sein, den der Ausdruck zurückgibt.  
  
 In der folgenden Tabelle werden Verwendungsmöglichkeiten für Ausdrucksspalten in einer Tabelle aufgelistet.  
  
|Ausdruckstyp|Beispiel|  
|---------------------|-------------|  
|Vergleich|"Gesamt >= 500"|  
|Berechnung|"Einzelpreis * Menge"|  
|Aggregation|Sum(Price)|  
  
 Sie können die **Expression** -Eigenschaft für ein vorhandenes **datacolenumn** -Objekt festlegen, oder Sie können die-Eigenschaft als drittes Argument, das an den- <xref:System.Data.DataColumn> Konstruktor übergeben wird, einschließen, wie im folgenden Beispiel gezeigt.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Ausdrücke können auf andere Ausdrucksspalten verweisen. Ein Zirkelverweis, bei dem zwei Ausdrücke aufeinander verweisen, generiert jedoch eine Ausnahme. Regeln zum Schreiben von Ausdrücken finden Sie unter der- <xref:System.Data.DataColumn.Expression%2A> Eigenschaft der **datacolenumn** -Klasse.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [DataTable-Schemadefinition](datatable-schema-definition.md)
- ["DataTables"](datatables.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
