---
title: Erstellen von Ausdrucksspalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 11bacf436daf2a77a9cf46b4883d282143572e27
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="creating-expression-columns"></a>Erstellen von Ausdrucksspalten
Sie können einen Ausdruck für eine Spalte definieren, sodass diese einen Wert enthalten kann, der aus anderen Spaltenwerten in der gleichen Zeile oder aus Spaltenwerten mehrerer Zeilen in der Tabelle berechnet wurde. Wenn Sie den auszuwertenden Ausdruck definieren möchten, verwenden Sie die <xref:System.Data.DataColumn.Expression%2A>-Eigenschaft der Zielspalte und verweisen mithilfe der <xref:System.Data.DataColumn.ColumnName%2A>-Eigenschaft auf andere Spalten im Ausdruck. Der <xref:System.Data.DataColumn.DataType%2A> für die Ausdrucksspalte muss für den Wert geeignet sein, den der Ausdruck zurückgibt.  
  
 In der folgenden Tabelle werden Verwendungsmöglichkeiten für Ausdrucksspalten in einer Tabelle aufgelistet.  
  
|Ausdruckstyp|Beispiel|  
|---------------------|-------------|  
|Vergleich|"Gesamtsumme >= 500"|  
|Berechnung|"Einzelpreis * Menge"|  
|Aggregation|Sum(Price)|  
  
 Sie können festlegen, die **Ausdruck** -Eigenschaft für ein vorhandenes **DataColumn** -Objekt, oder Sie zählen die Eigenschaft als dritte Argument übergeben der <xref:System.Data.DataColumn> Konstruktor, wie im folgenden Beispiel gezeigt.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Ausdrücke können auf andere Ausdrucksspalten verweisen. Ein Zirkelverweis, bei dem zwei Ausdrücke aufeinander verweisen, generiert jedoch eine Ausnahme. Regeln zum Schreiben von Ausdrücken finden Sie unter der <xref:System.Data.DataColumn.Expression%2A> Eigenschaft von der **DataColumn** Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [DataTable-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
