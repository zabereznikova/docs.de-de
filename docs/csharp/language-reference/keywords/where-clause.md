---
title: "where-Klausel (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "whereclause_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "where-Klausel [C#]"
  - "where-Schlüsselwort [C#]"
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# where-Klausel (C#-Referenz)
Die `where`\-Klausel wird in einem Abfrageausdruck verwendet, um anzugeben, welche Elemente aus der Datenquelle im Abfrageausdruck zurückgegeben werden.  Sie wendet eine boolesche Bedingung \(*Prädikat*\) auf die einzelnen Quellelemente an \(auf die durch die Bereichsvariable verwiesen wird\) und gibt diejenigen zurück, für die die angegebene Bedingung den Wert true hat.  Ein einzelner Abfrageausdruck kann mehrere `where`\-Klauseln enthalten, und eine einzelne Klausel kann mehrere Teilausdrücke des Prädikats enthalten.  
  
## Beispiel  
 Im folgenden Beispiel werden durch die `where`\-Klausel alle Zahlen herausgefiltert, die größer als fünf sind.  Wenn Sie die `where`\-Klausel entfernen, werden alle Zahlen aus der Datenquelle zurückgegeben.  Der Ausdruck `num < 5` ist das Prädikat, das auf jedes Element angewendet wird.  
  
 [!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## Beispiel  
 Innerhalb einer einzelnen `where` \-Klausel können Sie mit dem Operator [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) und dem Operator [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) so viele Prädikate wie nötig angeben.  Im folgenden Beispiel gibt die Abfrage zwei Prädikate an, um nur die geraden Zahlen auszuwählen, die kleiner als fünf sind.  
  
 [!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## Beispiel  
 Eine `where`\-Klausel enthält möglicherweise eine oder mehrere Methoden, die boolesche Werte zurückgeben.  Im folgenden Beispiel wird mithilfe der `where`\-Klausel eine Methode verwendet, um zu bestimmen, ob der aktuelle Wert der Bereichsvariable gerade oder ungerade ist.  
  
 [!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## Hinweise  
 Die `where`\-Klausel ist ein Filtermechanismus.  Sie kann fast überall in einem Abfrageausdruck platziert werden, darf aber nicht die erste oder letzte Klausel sein.  Eine `where`\-Klausel kann entweder vor oder nach einer [group](../../../csharp/language-reference/keywords/group-clause.md)\-Klausel erscheinen, je nach dem, ob Sie die Quellelemente vor oder nach dem Gruppieren filtern müssen.  
  
 Ist ein angegebenes Prädikat nicht für die Elemente in der Datenquelle gültig, tritt ein Kompilierzeitfehler auf.  Dies ist ein Vorteil der starken Typüberprüfung, die von [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] bereitgestellt wird.  
  
 Während der Kompilierung wird das `where`\-Schlüsselwort in einen Aufruf der <xref:System.Linq.Enumerable.Where%2A>\-Standardabfrageoperator\-Methode konvertiert.  
  
## Siehe auch  
 [Abfrageschlüsselwörter \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [from\-Klausel](../../../csharp/language-reference/keywords/from-clause.md)   
 [select\-Klausel](../../../csharp/language-reference/keywords/select-clause.md)   
 [Filtering Data](../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)