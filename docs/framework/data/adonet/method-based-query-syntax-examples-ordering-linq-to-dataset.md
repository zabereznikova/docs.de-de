---
title: "Beispiele f&#252;r die methodenbasierte Abfragesyntax: Sortieren (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Beispiele f&#252;r die methodenbasierte Abfragesyntax: Sortieren (LINQ to DataSet)
In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der <xref:System.Linq.Enumerable.OrderBy%2A>\-Methode, der <xref:System.Linq.Enumerable.Reverse%2A>\-Methode und der <xref:System.Linq.Enumerable.ThenBy%2A>\-Methode sowie der methodenbasierten Abfragesyntax ein <xref:System.Data.DataSet> abfragen und die Reihenfolge der Ergebnisse festlegen können.  
  
 Informationen zur `FillDataSet`\-Methode, die in diesen Beispielen verwendet wird, finden Sie unter [Laden von Daten in ein 'DataSet'](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 In den Beispielen in diesem Thema wird auf die Tabellen \<legacyBold\>Contact\<\/legacyBold\>, \<legacyBold\>Address\<\/legacyBold\>, \<legacyBold\>Product\<\/legacyBold\>, \<legacyBold\>SalesOrderHeader\<\/legacyBold\> und \<legacyBold\>SalesOrderDetail\<\/legacyBold\> in der \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Beispieldatenbank zurückgegriffen.  
  
 Die Beispiele in diesem Thema beziehen sich auf die folgenden `using`\/`Imports`\-Anweisungen:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet\-Projekts in Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## OrderBy  
  
### Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.OrderBy%2A>\-Methode mit einem benutzerdefinierten Vergleich verwendet, um die Nachnamen ohne Berücksichtigung der Groß\- oder Kleinschreibung zu sortieren.  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## Reverse  
  
### Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.Reverse%2A>\-Methode verwendet, um eine Liste der Aufträge zu erstellen, bei denen der `OrderDate`\-Wert vor dem 20. Februar 2002 liegt.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## ThenBy  
  
### Beispiel  
 In diesem Beispiel werden die Methoden <xref:System.Linq.Enumerable.OrderBy%2A> und <xref:System.Linq.Enumerable.ThenBy%2A> mit einem benutzerdefinierten Vergleich verwendet, um die Daten zuerst nach dem Listenpreis zu und dann nach dem Produktnamen \(ohne Berücksichtigung der Groß\- oder Kleinschreibung\) zu sortieren.  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## Siehe auch  
 [Laden von Daten in ein 'DataSet'](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [LINQ to DataSet\-Beispiele](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)