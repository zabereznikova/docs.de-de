---
title: Navigieren in "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: c46007fb86a76405fd99d6e943779238d6885aa8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="navigating-datarelations"></a>Navigieren in "DataRelations"
Eine der Hauptfunktionen einer <xref:System.Data.DataRelation> besteht darin, die Navigation von einer <xref:System.Data.DataTable> zu einer anderen innerhalb eines <xref:System.Data.DataSet> zu ermöglichen. Dies ermöglicht es Ihnen, alle verwandten <xref:System.Data.DataRow> Objekte in einem **DataTable** Wenn eine einzelne **DataRow** aus einer verknüpften **DataTable**. Beispielsweise nach dem Herstellen einer **DataRelation** zwischen einer Tabelle möglicher Kunden und eine Tabelle der Aufträge, können Sie alle Auftragszeilen für eine bestimmte Kundenzeile mit abrufen **GetChildRows**.  
  
 Das folgende Codebeispiel erstellt eine **DataRelation** zwischen der **Kunden** Tabelle und die **Aufträge** Tabelle mit einer **DataSet** und gibt zurück Alle Aufträge für jeden Kunden.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Das nächste Beispiel baut auf dem vorhergehenden Beispiel auf. Hier werden vier Tabellen miteinander verknüpft, sodass über diese Beziehungen zu den Tabellen navigiert werden kann. Wie im vorherigen Beispiel **CustomerID** bezieht sich die **Kunden** Tabelle, auf die **Aufträge** Tabelle. Für jeden Kunden in der **Kunden** Tabelle, alle untergeordneten Zeilen in der **Aufträge** Tabelle bestimmt sind, um die Anzahl der Aufträge eines bestimmten Kunden zurückzugeben und ihre **OrderID** Werte.  
  
 Das erweiterte Beispiel gibt auch die Werte aus den **OrderDetails** und **Produkte** Tabellen. Die **Aufträge** Tabelle bezieht sich auf die **OrderDetails** Tabelle mit **OrderID** bestimmen, für jeden Kundenauftrag, Produkte und Mengen sortiert wurden. Da die **OrderDetails** Tabelle enthält nur die **"ProductID"** eines bestellten Produkts **OrderDetails** bezieht sich auf **Produkte** mit **"ProductID"** zum Zurückgeben der **ProductName**. In dieser Beziehung ist die **Produkte** Tabelle ist das übergeordnete Element und die **Bestelldetails** Tabelle wird das untergeordnete Element. Als Ergebnis wird beim Durchlaufen der **OrderDetails** Tabelle **GetParentRow** wird aufgerufen, um den zugehörigen abrufen **ProductName** Wert.  
  
 Beachten Sie, dass bei der **DataRelation** wird erstellt, für die **Kunden** und **Aufträge** Tabellen kein Feldwert angegeben ist die **CreateConstraints**Flag (der Standardwert ist **"true"**). Dies setzt voraus, dass alle Zeilen in der **Aufträge** Tabelle enthalten eine **CustomerID** -Wert, der in der übergeordneten Tabelle vorhanden ist **Kunden** Tabelle. Wenn eine **CustomerID** vorhanden ist, der **Aufträge** Tabelle, die in nicht vorhanden ist die **Kunden** Tabelle, eine <xref:System.Data.ForeignKeyConstraint> löst eine Ausnahme ausgelöst wird.  
  
 Wenn die untergeordnete Spalte Werte enthält, die der übergeordneten Spalte nicht enthalten sind, legen die **CreateConstraints** flag auf **"false"** beim Hinzufügen der **DataRelation**. Im Beispiel die **CreateConstraints** Flag wird festgelegt, um **"false"** für die **DataRelation** zwischen der **Aufträge** Tabelle und die  **OrderDetails** Tabelle. Dadurch kann die Anwendung zur Rückgabe aller Datensätze aus der **OrderDetails** Tabellen- und nur eine Teilmenge der Datensätze aus der **Aufträge** Tabelle ohne generieren eine Laufzeitausnahme. Im erweiterten Beispiel wird die Ausgabe im folgenden Format generiert:  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 Das folgende Codebeispiel ist erweitert, in dem die Werte aus den **OrderDetails** und **Produkte** Tabellen zurückgegeben werden, und nur eine Teilmenge der Datensätze in der **Aufträge**Tabelle zurückgegeben wird.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
