---
title: "orderby-Klausel (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "orderby"
  - "orderby_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "orderby-Klausel [C#]"
  - "orderby-Schlüsselwort [C#]"
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# orderby-Klausel (C#-Referenz)
In einem Abfrageausdruck bewirkt die `orderby`\-Klausel, dass die zurückgegebene Sequenz oder Untersequenz \(Gruppe\) entweder in aufsteigender oder absteigender Reihenfolge sortiert wird.  Mehrere Schlüssel können angegeben werden, um einen oder mehrere sekundäre Sortiervorgänge auszuführen.  Die Sortierung wird vom Standardvergleich für den Typ des Elements ausgeführt.  Standardmäßig wird eine aufsteigende Sortierreihenfolge verwendet.  Sie können auch einen benutzerdefinierten Vergleich angeben.  Er ist jedoch nur bei einer methodenbasierten Syntax verfügbar.  Weitere Informationen finden Sie unter [Sorting Data](../../../visual-basic/programming-guide/concepts/linq/sorting-data.md).  
  
## Beispiel  
 Im folgenden Beispiel sortiert die erste Abfrage die Wörter in alphabetischer Reihenfolge beginnend bei A, und die zweite Abfrage sortiert die gleichen Wörter in absteigender Reihenfolge.  \(Das `ascending`\-Schlüsselwort ist der Standardsortierwert und muss nicht angegeben werden.\)  
  
 [!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine primäre Sortierung der Nachnamen der Studenten und dann eine sekundäre Sortierung der Vornamen durchgeführt.  
  
 [!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## Hinweise  
 Bei der Kompilierung übersetzt die `orderby`\-Klausel den Aufruf in die <xref:System.Linq.Enumerable.OrderBy%2A>\-Methode.  Mehrere Schlüssel in der `orderby`\-Klausel werden in <xref:System.Linq.Enumerable.ThenBy%2A>\-Methodenaufrufe übersetzt.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [Abfrageschlüsselwörter \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)