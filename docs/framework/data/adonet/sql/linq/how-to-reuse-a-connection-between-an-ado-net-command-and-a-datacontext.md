---
title: "Vorgehensweise: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem DataContext | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem DataContext
Da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ein Teil der [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]\-Technologiereihe ist und auf Services von [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] basiert, können Sie eine Verbindung zwischen einem [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]\-Befehl und einem <xref:System.Data.Linq.DataContext> wiederverwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die gleiche Verbindung zwischen einem [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]\-Befehl und dem <xref:System.Data.Linq.DataContext> wiederverwendet wird.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [ADO.NET und LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)   
 [Kommunizieren mit der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)