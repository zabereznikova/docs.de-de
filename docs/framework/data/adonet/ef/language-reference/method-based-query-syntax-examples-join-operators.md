---
title: "Beispiele f&#252;r die methodenbasierte Abfragesyntax: Joinoperatoren | Microsoft Docs"
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
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Beispiele f&#252;r die methodenbasierte Abfragesyntax: Joinoperatoren
In diesem Beispiel wird gezeigt, wie Sie mithilfe der <xref:System.Linq.Enumerable.Join%2A>\- und der <xref:System.Linq.Enumerable.GroupJoin%2A>\-Methode unter Verwendung der methodenbasierten Abfragesyntax das [AdventureWorks Sales\-Modell](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) abfragen.  Für das in den Beispielen verwendete "AdventureWorks Sales"\-Modell wurde auf die Tabellen **Contact**, **Address**, **Product**, **SalesOrderHeader** und **SalesOrderDetail** der "AdventureWorks"\-Beispieldatenbank zurückgegriffen.  
  
 Die Beispiele in diesem Thema beziehen sich auf die folgenden `using`\/`Imports`\-Anweisungen:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## GroupJoin  
  
### Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der SalesOrderHeader\-Tabelle und der SalesOrderDetail\-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kunde zu suchen.  Eine Gruppenverknüpfung ist das Äquivalent zu einer linken äußeren Verknüpfung, die jedes Element der ersten \(linken\) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der Contact\-Tabelle und der SalesOrderHeader\-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kontakt zu suchen.  Die Anzahl der Aufträge und die IDs für alle Kontakte werden angezeigt.  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## Join  
  
### Beispiel  
 Im folgenden Beispiel werden die Tabellen **Contact** und **SalesOrderHeader** miteinander verknüpft.  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### Beispiel  
 Im folgenden Beispiel werden die Tabellen **Contact** und **SalesOrderHeader** miteinander verknüpft, und die Ergebnisse werden nach der Kontakt\-ID gruppiert.  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## Siehe auch  
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)