---
title: "Vorgehensweise: Inline-Aufrufen von benutzerdefinierten Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Inline-Aufrufen von benutzerdefinierten Funktionen
Obwohl Sie benutzerdefinierte Funktionen inline aufrufen können, werden in einer Abfrage enthaltene Funktionen, deren Ausführung umgeleitet wird, bis zur Ausführung der Abfrage verzögert.  Weitere Informationen finden Sie unter [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
 Wenn Sie die gleiche Funktion außerhalb einer Abfrage ausführen, erstellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine einfache Abfrage aus der call expression\-Methode.  Folgendes befindet sich in der SQL\-Syntax \(der `@p0`\-Parameter ist an die übergebene Konstante gebunden\):  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erstellt Folgendes:  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## Beispiel  
 In der folgenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Abfrage sehen Sie einen Inline\-Abruf für die benutzerdefinierte `ReverseCustName`\-Funktionsmethode.  Die Funktion wird nicht sofort ausgeführt, da die Abfrageausführung verzögert wird.  Die für diese Abfrage erstellte SQL\-Anweisung wird in einen Aufruf der benutzerdefinierten Funktion in der Datenbank übersetzt \(siehe SQL\-Code nach der Abfrage\).  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## Siehe auch  
 [Benutzerdefinierte Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)