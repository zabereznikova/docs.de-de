---
title: "Beispiele f&#252;r die Abfrageausdruckssyntax: Filtern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: c27cb89c-1c1d-4988-9f38-950eda3cb275
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Beispiele f&#252;r die Abfrageausdruckssyntax: Filtern
In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden `Where` und `Where…Contains` und der Abfrageausdruckssyntax ein [AdventureWorks Sales\-Modell](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) abfragen können.  Hinweis: Where…`Contains` kann nicht als Teil einer [kompilierten Abfrage](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md) verwendet werden.  
  
 Für das in den Beispielen verwendete AdventureWorks Sales\-Modell wurde auf die Tabellen **Contact**, **Address**, **Product**, **SalesOrderHeader** und **SalesOrderDetail** der AdventureWorks\-Beispieldatenbank zurückgegriffen.  
  
 Die Beispiele in diesem Thema beziehen sich auf die folgenden `using`\/`Imports`\-Anweisungen:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## Where  
  
### Beispiel  
 Im folgenden Beispiel werden alle Onlinebestellungen zurückgegeben.  
  
 [!code-csharp[DP L2E Examples#Where1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1)]
 [!code-vb[DP L2E Examples#Where1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1)]  
  
### Beispiel  
 Im folgenden Beispiel werden die Aufträge zurückgegeben, bei denen die Bestellmenge größer als 2 und kleiner als 6 ist.  
  
 [!code-csharp[DP L2E Examples#Where2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2)]
 [!code-vb[DP L2E Examples#Where2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2)]  
  
### Beispiel  
 Im folgenden Beispiel werden alle Produkte mit roter Farbe zurückgegeben.  
  
 [!code-csharp[DP L2E Examples#Where3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3)]
 [!code-vb[DP L2E Examples#Where3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3)]  
  
### Beispiel  
 Im folgenden Beispiel wird die `Where`\-Methode verwendet, um Aufträge zu finden, die nach dem 1. Dezember 2003 eingegangen sind. Anschließend wird die `order.SalesOrderDetail`\-Navigationseigenschaft verwendet, um die Details für jeden Auftrag abzurufen.  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## Where…Contains  
  
### Beispiel  
 Im folgenden Beispiel wird ein Array als Teil einer `Where…Contains`\-Klausel verwendet, um alle Produkte zu suchen, die eine dem Wert im Array entsprechende `ProductModelID` aufweisen.  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#1)]
 [!code-vb[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#1)]  
  
> [!NOTE]
>  Als Teil des Prädikats in einer `Where…Contains`\-Klausel können Sie ein <xref:System.Array>, eine <xref:System.Collections.Generic.List%601> oder eine Auflistung eines beliebigen Typs verwenden, der die <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle implementiert.  Sie können auch eine Auflistung innerhalb einer LINQ to Entities\-Abfrage deklarieren und initialisieren.  Weitere Informationen finden Sie im nächsten Beispiel.  
  
### Beispiel  
 Im folgenden Beispiel werden Arrays in einer `Where…Contains`\-Klausel deklariert und initialisiert, um alle Produkte zu suchen, die eine `ProductModelID` oder `Size` aufweisen, die Werten in den Arrays entspricht.  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#2)]
 [!code-vb[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#2)]  
  
## Siehe auch  
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)