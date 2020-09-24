---
title: Navigieren in "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 5eb2ee16712be5ccd5e9aa0af4dde22dcaaeea09
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148385"
---
# <a name="navigating-datarelations"></a>Navigieren in "DataRelations"

Eine der Hauptfunktionen einer <xref:System.Data.DataRelation> besteht darin, die Navigation von einer <xref:System.Data.DataTable> zu einer anderen innerhalb eines <xref:System.Data.DataSet> zu ermöglichen. Auf diese Weise können Sie alle verknüpften <xref:System.Data.DataRow> Objekte in einer **Daten** Tabelle abrufen, wenn Sie eine einzelne **DataRow** aus einer verknüpften **Daten**Tabelle erhalten. Nachdem Sie z. b. eine **DataRelations** zwischen einer Tabelle mit Kunden und einer Tabelle mit Bestellungen eingerichtet haben, können Sie mithilfe von **GetChildRows**alle Auftragszeilen für eine bestimmte Kunden Zeile abrufen.  
  
 Im folgenden Codebeispiel wird eine **DataRelations** zwischen der **Customers** -Tabelle und der **Orders** -Tabelle eines **DataSets** erstellt und alle Bestellungen für jeden Kunden zurückgegeben.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Das nächste Beispiel baut auf dem vorhergehenden Beispiel auf. Hier werden vier Tabellen miteinander verknüpft, sodass über diese Beziehungen zu den Tabellen navigiert werden kann. Wie im vorherigen Beispiel verknüpft **CustomerID** die **Customers** -Tabelle mit der **Orders** -Tabelle. Für jeden Kunden in der **Customers** -Tabelle werden alle untergeordneten Zeilen in der **Orders** -Tabelle bestimmt, um die Anzahl der Bestellungen eines bestimmten Kunden und deren **OrderID** -Werte zurückzugeben.  
  
 Das erweiterte Beispiel gibt auch die Werte aus den Tabellen **Order Details** und **Products** zurück. Die **Orders** -Tabelle bezieht sich auf die **Order Details** -Tabelle mithilfe von **OrderID** , um für jeden Kundenauftrag festzustellen, welche Produkte und Mengen sortiert wurden. Da die **Order Details** -Tabelle nur die **ProductID** eines bestellten Produkts enthält, steht **Order Details** im Zusammenhang mit **Produkten** , die **ProductID** verwenden, um **ProductName**zurückzugeben. In dieser Beziehung ist die Tabelle " **Products** " das übergeordnete Element, und die Tabelle " **Order Details** " ist das untergeordnete Element. Daher wird beim Durchlaufen der **Order Details** -Tabelle **getparameentrow** aufgerufen, um den zugehörigen **ProductName** -Wert abzurufen.  
  
 Beachten Sie, dass bei der Erstellung der **DataRelations** -Tabelle für die **Customers** -und **Orders** -Tabelle kein Wert für das Flag "" vom Typ " **anateconstraints** " angegeben wird (Standardwert: **true**). Dabei wird davon ausgegangen, dass alle Zeilen in der **Orders** -Tabelle einen **CustomerID-** Wert aufweisen, der in der übergeordneten **Customers** -Tabelle vorhanden ist. Wenn eine **CustomerID** in der **Orders** -Tabelle vorhanden ist, die in der **Customers** -Tabelle nicht vorhanden ist, <xref:System.Data.ForeignKeyConstraint> wird eine Ausnahme ausgelöst.  
  
 Wenn die untergeordnete Spalte Werte enthalten kann, die in der übergeordneten Spalte nicht enthalten sind, legen Sie beim Hinzufügen von **DataRelations**das Flag " **kreateconstraints** " auf " **false** " fest. In dem Beispiel wird das Flag " **kreateconstraints** " für " **DataRelations** " zwischen der Tabelle " **Orders** " und der Tabelle " **Order Details** " auf " **false** " festgelegt. Dadurch kann die Anwendung alle Datensätze aus der Tabelle **Order Details** und nur eine Teilmenge der Datensätze aus der Tabelle **Orders** zurückgeben, ohne eine Lauf Zeit Ausnahme zu erzeugen. Im erweiterten Beispiel wird die Ausgabe im folgenden Format generiert:  
  
```output  
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
  
 Das folgende Codebeispiel ist ein erweitertes Beispiel, bei dem die Werte aus den Tabellen **Order Details** und **Products** zurückgegeben werden, wobei nur eine Teilmenge der Datensätze in der **Orders** -Tabelle zurückgegeben wird.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
