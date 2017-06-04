---
title: "Beispiele f&#252;r die methodenbasierte Abfragesyntax: Projektion | Microsoft Docs"
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
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Beispiele f&#252;r die methodenbasierte Abfragesyntax: Projektion
In diesem Beispiel wird gezeigt, wie Sie mithilfe der <xref:System.Linq.Enumerable.Select%2A>\-Methode und der <xref:System.Linq.Enumerable.SelectMany%2A>\-Methode unter Verwendung der methodenbasierten Abfragesyntax das [AdventureWorks Sales\-Modell](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) abfragen.  Für das in den Beispielen verwendete "AdventureWorks Sales"\-Modell wurde auf die Tabellen **Contact**, **Address**, **Product**, **SalesOrderHeader** und **SalesOrderDetail** der "AdventureWorks"\-Beispieldatenbank zurückgegriffen.  
  
 Die Beispiele in diesem Thema beziehen sich auf die folgenden `using`\/`Imports`\-Anweisungen:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## Auswahl  
  
### Beispiel  
 Im folgenden Beispiel wird die <xref:System.Linq.Queryable.Select%2A>\-Methode verwendet, um die `Product.Name`\-Eigenschaft und die `Product.ProductID`\-Eigenschaft auf eine Abfolge anonymer Typen zu projizieren.  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### Beispiel  
 Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Select%2A>\-Methode verwendet, um eine Sequenz zurückzugeben, die nur aus Produktnamen besteht.  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## SelectMany  
  
### Beispiel  
 Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>\-Methode verwendet, um alle Aufträge auszuwählen, bei denen `TotalDue` kleiner als 500,00 ist.  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### Beispiel  
 Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>\-Methode verwendet, um alle Aufträge auszuwählen, die am 1. Oktober 2002 oder später eingegangen sind.  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## Siehe auch  
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)