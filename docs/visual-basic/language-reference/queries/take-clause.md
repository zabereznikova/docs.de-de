---
title: "Take Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryTake"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Take statement"
  - "queries [Visual Basic], Take"
  - "Take clause"
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Take Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück.  
  
## Syntax  
  
```  
Take count  
```  
  
## Teile  
 `count`  
 Erforderlich.  Ein Wert oder ein Ausdruck, dessen Auswertung die Anzahl von Elementen der Sequenz ergibt, die zurückgegeben werden soll.  
  
## Hinweise  
 Durch Angabe der `Take`\-Klausel umfasst eine Abfrage eine angegebene Anzahl zusammenhängender Elemente vom Anfang einer Ergebnisliste.  Die Anzahl der einzuschließenden Elemente wird durch den `count`\-Parameter festgelegt.  
  
 Die `Take`\-Klausel kann zusammen mit der `Skip`\-Klausel verwendet werden, um einen Datenbereich aus einem beliebigen Abschnitt einer Abfrage zurückzugeben.  Hierfür wird der `Skip`\-Klausel der Index des ersten Elements des Bereichs und der `Take`\-Klausel die Größe des Bereichs übergeben.  In diesem Fall muss die `Take`\-Klausel nach der `Skip`\-Klausel angegeben werden.  
  
 Bei der Verwendung der `Take`\-Klausel in einer Abfrage sollte sichergestellt werden, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, in der die vorgesehenen Ergebnisse von der `Take`\-Klausel eingeschlossen werden können.  Weitere Informationen zum Sortieren von Abfrageergebnissen finden Sie unter [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Mit der `TakeWhile`\-Klausel kann anhand einer angegebenen Bedingung festgelegt werden, dass nur bestimmte Elemente zurückgegeben werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die `Take`\-Klausel zusammen mit der `Skip`\-Klausel verwendet, um die Ergebnisse einer Abfrage seitenweise zurückzugeben.  Die `Skip`\-Klausel wird von der GetCustomers\-Funktion verwendet, um die Kunden in der Liste bis zum angegebenen Indexstartwert zu übergehen. Die `Take`\-Klausel wird verwendet, um eine Seite mit Kunden ab diesem Indexwert zurückzugeben.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md)   
 [Skip Clause](../../../visual-basic/language-reference/queries/skip-clause.md)