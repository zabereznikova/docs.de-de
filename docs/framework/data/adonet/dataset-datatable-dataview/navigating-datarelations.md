---
title: "Navigieren in &#39;DataRelations&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Navigieren in &#39;DataRelations&#39;
Eine der Hauptfunktionen einer <xref:System.Data.DataRelation> besteht darin, die Navigation von einer <xref:System.Data.DataTable> zu einer anderen innerhalb eines <xref:System.Data.DataSet> zu ermöglichen.  Dadurch können Sie alle verknüpften <xref:System.Data.DataRow>\-Objekte in einer **DataTable** abrufen, wenn eine einzelne **DataRow** von einer verknüpften **DataTable** vorliegt.  Nachdem Sie z. B. eine **DataRelation** zwischen einer Kundentabelle und einer Auftragstabelle erstellt haben, können Sie alle Auftragszeilen für eine bestimmte Kundenzeile mit **GetChildRows** abrufen.  
  
 Im folgenden Codebeispiel wird eine **DataRelation** zwischen der **Customers**\-Tabelle und der **Orders**\-Tabelle eines **DataSets** erstellt, und es werden alle Aufträge für die einzelnen Kunden zurückgegeben.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Das nächste Beispiel baut auf dem vorhergehenden Beispiel auf. Hier werden vier Tabellen miteinander verknüpft, sodass über diese Beziehungen zu den Tabellen navigiert werden kann.  Wie im vorhergehenden Beispiel verknüpft **CustomerID** die **Customers**\-Tabelle mit der **Orders**\-Tabelle.  Für jeden Kunden in der **Customers**\-Tabelle werden alle untergeordneten Zeilen in der **Orders**\-Tabelle bestimmt, um die Anzahl der Aufträge eines bestimmten Kunden und die entsprechenden **OrderID**\-Werte zurückgeben zu können.  
  
 Das erweiterte Beispiel gibt auch die Werte aus den Tabellen **OrderDetails** und **Products** zurück.  Die **Orders**\-Tabelle wird unter Verwendung von **OrderID** mit der **OrderDetails**\-Tabelle verknüpft, um die bestellten Produkte und Mengen für jeden Kundenauftrag zu ermitteln.  Da die **OrderDetails**\-Tabelle nur die **ProductID** eines bestellten Produkts enthält, wird **OrderDetails** über **ProductID** mit **Products** verknüpft, um **ProductName** zurückzugeben.  Bei dieser Beziehung ist die **Products**\-Tabelle die übergeordnete Tabelle und die **OrderDetails**\-Tabelle die untergeordnete Tabelle.  Als Ergebnis wird beim Durchlaufen der **OrderDetails**\-Tabelle **GetParentRow** aufgerufen, um den in Beziehung stehenden **ProductName**\-Wert abzurufen.  
  
 Beachten Sie, dass beim Erstellen der **DataRelation** für die Tabellen **Customers** und **Orders** kein Wert für das **createConstraints**\-Flag \(der Standardwert ist **True**\) angegeben wird.  Es wird davon ausgegangen, dass alle Zeilen in der **Orders**\-Tabelle einen **CustomerID**\-Wert haben, der in der übergeordneten **Customers**\-Tabelle vorhanden ist.  Wenn in der **Orders**\-Tabelle eine **CustomerID** vorhanden ist, die nicht in der **Customers**\-Tabelle vorkommt, wird durch eine <xref:System.Data.ForeignKeyConstraint> eine Ausnahme ausgelöst.  
  
 Wenn die untergeordnete Spalte Werte enthält, die in der übergeordneten Spalte nicht enthalten sind, legen Sie beim Hinzufügen der **DataRelation** das **createConstraints**\-Flag auf **false** fest.  Im Beispiel wird **False** für das **createConstraints**\-Flag der **DataRelation** zwischen den Tabellen **Orders** und **OrderDetails** festgelegt.  Damit ist die Anwendung in der Lage, alle Datensätze aus der **OrderDetails**\-Tabelle und nur eine Teilmenge der Datensätze aus der **Orders**\-Tabelle zurückzugeben, ohne dass eine Laufzeitausnahme ausgelöst wird.  Im erweiterten Beispiel wird die Ausgabe im folgenden Format generiert:  
  
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
  
 Das folgende Codebeispiel ist erweitert. In diesem Beispiel werden die Werte aus den Tabellen **OrderDetails** und **Products** und nur eine Teilmenge der Datensätze der **Orders**\-Tabelle zurückgegeben.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)