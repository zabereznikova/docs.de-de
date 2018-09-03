---
title: Navigieren in "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 1819d468d12c03ce0c4faac11f4b20b8fe0f9c33
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482005"
---
# <a name="navigating-datarelations"></a>Navigieren in "DataRelations"
Eine der Hauptfunktionen einer <xref:System.Data.DataRelation> besteht darin, die Navigation von einer <xref:System.Data.DataTable> zu einer anderen innerhalb eines <xref:System.Data.DataSet> zu ermöglichen. Dadurch können Sie alle Abrufen der entsprechenden <xref:System.Data.DataRow> Objekte in einem **DataTable** Wenn eine einzelne **DataRow** von einer verknüpften **DataTable**. Z. B. nach dem Einrichten einer **DataRelation** zwischen einer Tabelle möglicher Kunden und eine Tabelle mit Bestellungen, können Sie alle Auftragszeilen für eine bestimmte Kundenzeile mit abrufen **GetChildRows**.  
  
 Das folgende Codebeispiel erstellt eine **DataRelation** zwischen der **Kunden** Tabelle und die **Bestellungen** Tabelle mit einer **DataSet** und gibt zurück Alle Bestellungen für jeden Kunden.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Das nächste Beispiel baut auf dem vorhergehenden Beispiel auf. Hier werden vier Tabellen miteinander verknüpft, sodass über diese Beziehungen zu den Tabellen navigiert werden kann. Wie im vorherigen Beispiel **"CustomerID"** bezieht sich die **Kunden** Tabelle, auf die **Bestellungen** Tabelle. Für jeden Kunden in den **Kunden** Tabelle, alle untergeordneten Zeilen in der **Bestellungen** Tabelle ermittelt werden, um die Anzahl der Aufträge eines bestimmten Kunden zurückzugeben und ihre **"OrderID"** Werte.  
  
 Das erweiterte Beispiel gibt auch die Werte aus der **OrderDetails** und **Produkte** Tabellen. Die **Bestellungen** Tabelle bezieht sich auf die **OrderDetails** Tabelle mithilfe von **"OrderID"** um zu bestimmen, für jede kundenbestellung, Produkte und Mengen geordnet wurden. Da die **OrderDetails** Tabelle enthält nur die **"ProductID"** eines bestellten Produkts, **OrderDetails** bezieht sich auf **Produkte** Mithilfe von **"ProductID"** zum Zurückgeben der **ProductName**. Bei dieser Beziehung ist die **Produkte** Tabelle ist das übergeordnete Element und die **Bestelldetails** Tabelle ist das untergeordnete Element. Als Ergebnis beim Durchlaufen der **OrderDetails** Tabelle **GetParentRow** wird aufgerufen, um die zugehörigen abrufen **ProductName** Wert.  
  
 Beachten Sie, dass bei der **DataRelation** für erstellt wird die **Kunden** und **Bestellungen** Tabellen kein Wert wird angegeben, für die **CreateConstraints**Flag (der Standardwert ist **"true"**). Dies setzt voraus, dass alle Zeilen in der **Bestellungen** Tabelle eine **"CustomerID"** -Wert, der in das übergeordnete Element vorhanden ist **Kunden** Tabelle. Wenn eine **"CustomerID"** vorhanden ist, der **Bestellungen** Tabelle, die in nicht vorhanden ist die **Kunden** Tabelle eine <xref:System.Data.ForeignKeyConstraint> löst eine Ausnahme ausgelöst wird.  
  
 Wenn die untergeordnete Spalte Werte enthält, die der übergeordneten Spalte nicht enthalten sind, legen die **CreateConstraints** flag auf **"false"** beim Hinzufügen der **DataRelation**. Im Beispiel die **CreateConstraints** ergebniskennzeichen auf **"false"** für die **DataRelation** zwischen der **Bestellungen** Tabelle und die  **OrderDetails** Tabelle. Dadurch kann die Anwendung alle Datensätze aus Zurückgeben der **OrderDetails** Tabellen- und nur eine Teilmenge der Datensätze aus der **Bestellungen** Tabelle ohne eine Laufzeitausnahme generiert. Im erweiterten Beispiel wird die Ausgabe im folgenden Format generiert:  
  
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
  
 Im folgenden Codebeispiel wird ein Beispiel für eine erweiterte, in denen die Werte aus der **OrderDetails** und **Produkte** Tabellen zurückgegeben, mit nur einer Teilmenge der Datensätze in der **Bestellungen**Tabelle zurückgegeben wird.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
