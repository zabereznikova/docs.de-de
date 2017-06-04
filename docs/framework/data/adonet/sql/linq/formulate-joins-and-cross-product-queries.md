---
title: "Formulieren von Joins und produkt&#252;bergreifenden Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Formulieren von Joins und produkt&#252;bergreifenden Abfragen
In den folgenden Beispielen wird gezeigt, wie Ergebnisse aus mehreren Tabellen kombiniert werden.  
  
## Beispiel  
 Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `From`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`from`\-Klausel in C\#\), um alle Bestellungen für Kunden aus London auszuwählen.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## Beispiel  
 Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `Where`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`where`\-Klausel in C\#\), um nicht mehr lieferbare `Products` herauszufiltern, deren `Supplier` sich in den Vereinigten Staaten befindet.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## Beispiel  
 Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `From`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`from`\-Klausel in C\#\), um Mitarbeiter in Seattle herauszufiltern und deren Gebiete anzuzeigen.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## Beispiel  
 Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `Select`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`select`\-Klausel in C\#\), um Mitarbeiterpaare herauszufiltern, bei denen ein Mitarbeiter dem anderen untersteht und bei denen beide Mitarbeiter aus der gleichen `City` stammen.  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## Beispiel  
 Im folgenden [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\-Beispiel wird nach allen Kunden und Bestellungen gesucht, es wird sichergestellt, dass die Bestellungen den Kunden zugeordnet werden und dass für jeden Kunden in der Liste ein Kontaktname angegeben wird.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Tabellen explizit verknüpft, und die Ergebnisse aus beiden Tabellen werden projiziert.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## Beispiel  
 Im folgenden Beispiel werden explizit drei Tabellen verknüpft, und Ergebnisse aus diesen werden projiziert.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## Beispiel  
 Im folgenden Beispiel wird das Erreichen einer `LEFT OUTER JOIN` mithilfe von `DefaultIfEmpty()` veranschaulicht.  Die `DefaultIfEmpty()`\-Methode gibt NULL zurück, wenn es keine `Order` für den `Employee` gibt.  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## Beispiel  
 Das folgende Beispiel projiziert einen `let`\-Ausdruck, der sich aus einem Join ergibt.  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## Beispiel  
 Im folgenden Beispiel wird ein `join` mit einem zusammengesetzten Schlüssel gezeigt.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## Beispiel  
 Das folgende Beispiel zeigt die Konstruktion eines `join`, bei dem eine Seite auf NULL festgelegt werden kann und die andere nicht.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## Siehe auch  
 [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)