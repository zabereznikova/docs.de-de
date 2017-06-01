---
title: "Z&#228;hlen der Anzahl von Elementen in einer Sequenz | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Z&#228;hlen der Anzahl von Elementen in einer Sequenz
Verwenden Sie den <xref:System.Linq.Enumerable.Count%2A>\-Operator, um die Anzahl von Elementen in einer Sequenz zu zählen.  
  
 Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, wird eine Ausgabe von `91` erzeugt.  
  
## Beispiel  
 Im folgenden Beispiel wird die Anzahl von `Customers` \(Kunden\) in der Datenbank gezählt.  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## Beispiel  
 Im folgenden Beispiel wird die Anzahl von Produkten in der Datenbank gezählt, die nicht eingestellt wurden.  
  
 Wenn Sie dieses Beispiel mit der Beispieldatenbank Northwind ausführen, wird eine Ausgabe von `69` erzeugt.  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## Siehe auch  
 [Aggregatabfragen](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)   
 [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)