---
title: "Ermitteln, ob Any- oder All-Elemente in einer Sequenz eine Bedingung erf&#252;llen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Ermitteln, ob Any- oder All-Elemente in einer Sequenz eine Bedingung erf&#252;llen
Der <xref:System.Linq.Enumerable.All%2A>\-Operator gibt `true` zurück, wenn alle Elemente in einer Sequenz eine Bedingung erfüllen.  
  
 Der <xref:System.Linq.Queryable.Any%2A>\-Operator gibt `true` zurück, wenn ein beliebiges Element in einer Sequenz eine Bedingung erfüllt.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Sequenz von Kunden mit mindestens einer Bestellung zurückgegeben.  Die `Where`\/`where`\-Klausel gilt als `true`, wenn der betreffende `Customer` \(Kunde\) eine beliebige `Order` \(Bestellung\) aufweist.  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## Beispiel  
 Der folgende Visual Basic\-Code ermittelt die Liste der Kunden, die noch keine Bestellungen übermittelt haben. Außerdem wird sichergestellt, dass für jeden Kunden in dieser Liste Kontaktinformationen angegeben werden.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## Beispiel  
 Im folgenden C\#\-Beispiel wird eine Sequenz von Kunden zurückgegeben, deren Bestellungen einen `ShipCity` \(Lieferort\) aufweisen, der mit "C" anfängt.  Außerdem werden Kunden ohne bisherige Bestellungen zurückgegeben.  \(Per Definition gibt der <xref:System.Linq.Queryable.All%2A>\-Operator bei einer leeren Sequenz `true` zurück.\) Kunden ohne Bestellungen werden mithilfe des `Count`\-Operators von der Konsolenausgabe ausgeschlossen.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## Siehe auch  
 [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)