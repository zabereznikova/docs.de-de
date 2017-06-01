---
title: "Vorgehensweise: Behandeln von zusammengesetzten Schl&#252;sseln in Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Behandeln von zusammengesetzten Schl&#252;sseln in Abfragen
Einige Operatoren können nur ein Argument annehmen.  Muss Ihr Argument mehrere Datenbankspalten aufnehmen, müssen Sie einen anonymen Typ erstellen, um die Kombination darzustellen.  
  
## Beispiel  
 Das folgende Beispiel zeigt eine Abfrage, die den `GroupBy`\-Operator aufruft. Dieser kann nur ein `key`\-Argument aufnehmen.  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## Beispiel  
 Die gleiche Situation betrifft Joins wie im folgenden Beispiel:  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## Siehe auch  
 [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)