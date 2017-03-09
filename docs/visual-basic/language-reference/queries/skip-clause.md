---
title: "Skip Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySkip"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], Skip"
  - "Skip statement"
  - "Skip clause"
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Skip Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Überspringt eine festgelegte Anzahl von Elementen in einer Auflistung und gibt anschließend die übrigen Elemente zurück.  
  
## Syntax  
  
```  
Skip count  
```  
  
## Teile  
 `count`  
 Erforderlich.  Ein Wert oder ein Ausdruck, dessen Auswertung die Anzahl von Elementen der Sequenz ergibt, die übersprungen werden soll.  
  
## Hinweise  
 Durch die `Skip`\-Klausel umgeht eine Abfrage Elemente am Anfang einer Ergebnisliste, und die verbleibenden Elemente werden zurückgegeben.  Die Anzahl der zu überspringenden Elemente wird durch den `count`\-Parameter identifiziert.  
  
 Die `Skip`\-Klausel kann zusammen mit der `Take`\-Klausel verwendet werden, um einen Datenbereich aus einem beliebigen Abschnitt einer Abfrage zurückzugeben.  Hierfür wird der `Skip`\-Klausel der Index des ersten Elements des Bereichs und der `Take`\-Klausel die Größe des Bereichs übergeben.  
  
 Bei der Verwendung der `Skip`\-Klausel in einer Abfrage sollte sichergestellt werden, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, in der die vorgesehenen Ergebnisse von der `Skip`\-Klausel umgangen werden können.  Weitere Informationen zum Sortieren von Abfrageergebnissen finden Sie unter [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Mit der `SkipWhile`\-Klausel kann anhand einer angegebenen Bedingung festgelegt werden, dass nur bestimmte Elemente ignoriert werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die `Skip`\-Klausel zusammen mit der `Take`\-Klausel verwendet, um die Ergebnisse einer Abfrage seitenweise zurückzugeben.  Die `GetCustomers`\-Funktion verwendet die `Skip`\-Klausel, um die Kunden in der Liste bis zum angegebenen Indexstartwert zu übergehen. Die `Take`\-Klausel wird verwendet, um eine Seite mit Kunden ab diesem Indexwert zurückzugeben.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#1)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Take Clause](../../../visual-basic/language-reference/queries/take-clause.md)