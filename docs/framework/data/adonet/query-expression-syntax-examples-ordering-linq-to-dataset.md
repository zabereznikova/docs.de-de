---
title: "Beispiele f&#252;r die Abfrageausdruckssyntax: Sortieren (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 653a4a97-1e4a-4b2d-8d24-7dbe1f2a5c84
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Beispiele f&#252;r die Abfrageausdruckssyntax: Sortieren (LINQ to DataSet)
In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> und <xref:System.Linq.Enumerable.ThenByDescending%2A> und der Abfrageausdruckssyntax ein <xref:System.Data.DataSet> abfragen und die Reihenfolge der Ergebnisse festlegen können.  
  
 Informationen zur `FillDataSet`\-Methode, die in diesen Beispielen verwendet wird, finden Sie unter [Laden von Daten in ein 'DataSet'](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 In den Beispielen in diesem Thema wird auf die Tabellen \<legacyBold\>Contact\<\/legacyBold\>, \<legacyBold\>Address\<\/legacyBold\>, \<legacyBold\>Product\<\/legacyBold\>, \<legacyBold\>SalesOrderHeader\<\/legacyBold\> und \<legacyBold\>SalesOrderDetail\<\/legacyBold\> in der \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Beispieldatenbank zurückgegriffen.  
  
 Die Beispiele in diesem Thema beziehen sich auf die folgenden `using`\/`Imports`\-Anweisungen:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet\-Projekts in Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## OrderBy  
  
### Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.OrderBy%2A>\-Methode verwendet, um eine nach Nachnamen geordnete Liste der Kontakte abzurufen.  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple1)]  
  
### Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.OrderBy%2A>\-Methode verwendet, um eine nach der Länge der Nachnamen geordnete Liste der Kontakte abzurufen.  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple2)]  
  
## OrderByDescending  
  
### Beispiel  
 In diesem Beispiel wird `orderby… descending` \(`Order By … Descending`\), das Äquivalent zur <xref:System.Linq.Enumerable.OrderByDescending%2A>\-Methode, verwendet, um die Preisliste in absteigender Reihenfolge \(höchster Preis zuerst, niedrigster zuletzt\) zu sortieren.  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## Reverse  
  
### Beispiel  
 In diesem Beispiel wird <xref:System.Linq.Enumerable.Reverse%2A> verwendet, um eine Liste der Aufträge zu erstellen, bei denen der `OrderDate`\-Wert vor dem 20. Februar 2002 liegt.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## ThenByDescending  
  
### Beispiel  
 In diesem Beispiel wird `OrderBy… Descending`, das Äquivalent zur <xref:System.Linq.Enumerable.ThenByDescending%2A>\-Methode, verwendet, um eine Liste von Produkten absteigend zuerst nach dem Namen und dann nach dem Listenpreis \(höchster Preis zuerst, niedrigster Preis zuletzt\) zu sortieren.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## Siehe auch  
 [Laden von Daten in ein 'DataSet'](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [LINQ to DataSet\-Beispiele](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)