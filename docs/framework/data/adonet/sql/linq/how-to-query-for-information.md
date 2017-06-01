---
title: "Vorgehensweise: Abfragen von Informationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Abfragen von Informationen
Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden die gleiche Syntax wie Abfragen in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  Der einzige Unterschied besteht darin, dass die in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Abfragen referenzierten Objekte den Elementen in einer Datenbank zugewiesen werden.  Weitere Informationen finden Sie unter [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die Sie in entsprechende SQL\-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server.  
  
 Einige Funktionen von [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]\-Abfragen benötigen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Anwendungen besondere Aufmerksamkeit.  Weitere Informationen finden Sie unter [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).  
  
## Beispiel  
 Die folgende Abfrage fordert eine Liste von Kunden aus London an.  In diesem Beispiel ist `Customers` eine Tabelle in der Northwind\-Beispieldatenbank.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## Siehe auch  
 [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)   
 [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)