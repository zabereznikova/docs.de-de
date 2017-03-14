---
title: "Gewusst wie: Verwenden von Lambda-Ausdr&#252;cken in einer Abfrage (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Lambda-Ausdrücke [C#], in LINQ"
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Gewusst wie: Verwenden von Lambda-Ausdr&#252;cken in einer Abfrage (C#-Programmierhandbuch)
Sie verwenden zwar keine Lambda\-Ausdrücke direkt in der Abfragesyntax, aber in Methodenaufrufen. Außerdem können Abfrageausdrücke Methodenaufrufe enthalten.  Einige Abfrageoperationen können sogar nur unter Verwendung von Methodensyntax ausgedrückt werden.  Weitere Informationen über den Unterschied zwischen Abfragesyntax und Methodensyntax finden Sie unter [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Umgang mit einem Lambda\-Ausdruck in einer methodenbasierten Abfrage veranschaulicht, indem der <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName>\-Standardabfrageoperator verwendet wird.  Beachten Sie, dass die <xref:System.Linq.Enumerable.Where%2A>\-Methode in diesem Beispiel einen Eingabeparameter des Delegattyps <xref:System.Func%601> hat. Dieser Typ ist ein Delegat, der eine ganze Zahl als Eingabe erfordert und einen booleschen Wert zurückgibt.  Der Lambda\-Ausdruck kann in diesen Delegattyp konvertiert werden.  Wäre dies eine [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]\-Abfrage, die die <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>\-Methode verwendet, wäre der Parameter vom Typ `Expression<Func\<int,bool>>`, aber der Lambda\-Ausdruck würde genau gleich aussehen.  Weitere Informationen über den Ausdruckstyp finden Sie unter <xref:System.Linq.Expressions.Expression?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung eines Lambda\-Ausdrucks in dem Methodenaufruf eines Abfrageausdrucks veranschaulicht.  Der Lambda\-Ausdruck ist erforderlich, da der <xref:System.Linq.Enumerable.Sum%2A>\-Standardabfrageoperator nicht mithilfe von Abfragesyntax aufgerufen werden kann.  
  
 Mit der Abfrage werden die Studierenden zunächst nach ihrer Jahrgangsstufe gruppiert, wie in der `GradeLevel`\-Enumeration definiert.  Dann werden für jede Gruppe die Ergebnisse pro Student addiert.  Dies erfordert zwei `Sum`\-Operationen.  Mit der inneren `Sum` wird das Gesamtergebnis für jeden Studenten berechnet, und mit der äußeren `Sum` wird eine kombinierte laufende Summe für alle Studenten in der Gruppe berechnet.  
  
 [!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]  
  
## Kompilieren des Codes  
 Um diesen Code auszuführen, kopieren Sie die Methode und fügen sie in die `StudentClass`\-Klasse ein, die in [Gewusst wie: Abfragen einer Auflistung von Objekten](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) bereitgestellt wird, und rufen sie über die `Main`\-Methode auf.  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Ausdrucksbaumstrukturen](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)