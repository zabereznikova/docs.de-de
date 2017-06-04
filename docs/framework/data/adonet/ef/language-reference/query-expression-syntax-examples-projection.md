---
title: "Beispiele f&#252;r die Abfrageausdruckssyntax: Projektion | Microsoft Docs"
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
ms.assetid: 079926c5-e6b5-4fb9-b4cf-9c63886dd626
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Beispiele f&#252;r die Abfrageausdruckssyntax: Projektion
In diesem Thema wird anhand von Beispielen gezeigt, wie Sie mithilfe der `Select`\-Methode und den `From … From …` \-Schlüsselwörtern das [AdventureWorks Sales\-Modell](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) unter Verwendung der Abfrageausdruckssyntax abfragen.  `From … From …` ist die abfragebasierte Entsprechung der `SelectMany`\-Methode.  Für das in den Beispielen verwendete AdventureWorks Sales\-Modell wurde auf die Tabellen **Contact**, **Address**, **Product**, **SalesOrderHeader** und **SalesOrderDetail** der AdventureWorks\-Beispieldatenbank zurückgegriffen.  
  
 Die Beispiele in diesem Thema beziehen sich auf die folgenden `using`\/`Imports`\-Anweisungen:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## Auswahl  
  
### Beispiel  
 Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Select%2A>\-Methode verwendet, um alle Zeilen der Tabelle `Product` zurückzugeben und die Produktnamen anzuzeigen.  
  
 [!code-csharp[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple1)]  
  
### Beispiel  
 Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Select%2A> verwendet, um eine Sequenz zurückzugeben, die nur aus Produktnamen besteht.  
  
 [!code-csharp[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2)]  
  
### Beispiel  
 Im folgenden Beispiel wird die <xref:System.Linq.Queryable.Select%2A>\-Methode verwendet, um die `Product.Name`\-Eigenschaft und die `Product.ProductID`\-Eigenschaft auf eine Abfolge anonymer Typen zu projizieren.  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes)]  
  
## From … From … \(SelectMany\)  
  
### Beispiel  
 Im folgenden Beispiel wird `From … From …` \(das Äquivalent der <xref:System.Linq.Enumerable.SelectMany%2A>\-Methode\) verwendet, um alle Aufträge auszuwählen, bei denen `TotalDue` kleiner als 500,00 ist.  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### Beispiel  
 Im folgenden Beispiel wird `From … From …` \(das Äquivalent der <xref:System.Linq.Enumerable.SelectMany%2A>\-Methode\) verwendet, um alle Aufträge auszuwählen, bei denen die Bestellung am 1. Oktober 2002 oder später eingegangen ist.  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### Beispiel  
 Im folgenden Beispiel wird `From … From …` \(das Äquivalent der <xref:System.Linq.Enumerable.SelectMany%2A>\-Methode\) verwendet, um alle Aufträge auszuwählen, bei denen die Bestellsumme größer als 10000,00 ist. Mithilfe der `From`\-Zuweisung wird vermieden, dass die Summe zweimal angefordert wird.  
  
 [!code-csharp[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## Siehe auch  
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)