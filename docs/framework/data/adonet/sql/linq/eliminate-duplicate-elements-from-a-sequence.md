---
title: "Ausschlie&#223;en von doppelten Elementen aus einer Sequenz | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Ausschlie&#223;en von doppelten Elementen aus einer Sequenz
Verwenden Sie den <xref:System.Linq.Queryable.Distinct%2A>\-Operator, um doppelte Elemente aus einer Sequenz auszuschließen.  
  
## Beispiel  
 Im folgenden Beispiel wird <xref:System.Linq.Queryable.Distinct%2A> verwendet, um eine Sequenz der eindeutigen Orte auszuwählen, die Kunden aufweisen.  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## Siehe auch  
 [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)