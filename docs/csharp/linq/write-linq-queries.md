---
title: Schreiben von LINQ-Abfragen in C#
description: Schreiben von Abfragen.
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2e08c8e3594bedeab763895c8b6f7d78a2bbf56d
ms.lasthandoff: 03/13/2017

---

# <a name="write-linq-queries-in-c"></a>Schreiben von LINQ-Abfragen in C#

In diesem Thema werden alle drei Möglichkeiten vorgestellt, mit denen man eine LINQ-Abfrage in C# schreiben kann:  
  
1.  Verwenden der Abfragesyntax.  
  
2.  Verwenden der Methodensyntax.  
  
3.  Verwenden einer Kombination aus Abfragesyntax und Methodensyntax.  
  
 Die folgenden Beispiele veranschaulichen einige einfache LINQ-Abfragen anhand der oben aufgelisteten Herangehensweisen. Im Allgemeinen gilt die Regel, wann immer möglich (1) zu verwenden, und (2) und (3) wenn nötig.  
  
> [!NOTE]
>  Diese Abfragen funktionieren auf Grundlage einfacher im Speicher enthaltener Auflistungen; die grundlegende Syntax entspricht jedoch genau der in „LINQ to Entities“ und „LINQ to XML“ verwendeten Syntax.  
  
## <a name="example"></a>Beispiel  
  
## <a name="query-syntax"></a>Abfragesyntax  
 Die empfohlene Methode, die meisten Abfragen zu schreiben, ist die Verwendung der *Abfragesyntax* zum Erstellen von *Abfrageausdrücken*. Im folgenden Beispiel werden drei Abfrageausdrücke gezeigt. Der erste Abfrageausdruck veranschaulicht, wie man Ergebnisse durch Anwenden von Bedingungen mit einer `where`-Klausel filtern und einschränken kann. Er gibt alle Elemente in der Quellsequenz zurück, deren Wert größer als 7 oder kleiner als 3 ist. Der zweite Ausdruck veranschaulicht, wie man die zurückgegebenen Ergebnisse sortiert. Der dritte Ausdruck veranschaulicht, wie man Ergebnisse nach einem Schlüssel gruppiert. Diese Abfrage gibt basierend auf dem ersten Buchstaben des Worts zwei Gruppen zurück.  
  
 [!code-cs[csProgGuideLINQ#5](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]  
  
 Beachten Sie, dass der Typ der Abfragen <xref:System.Collections.Generic.IEnumerable%601> ist. Alle diese Abfragen können mithilfe von `var` geschrieben werden, wie im folgenden Beispiel gezeigt wird:  
  
 `var query = from num in numbers...`  
  
 In allen vorherigen Beispielen werden die Abfragen nicht ausgeführt, bis Sie die Iteration über die Abfragevariable in einer `foreach`- oder einer anderen Anweisung durchlaufen haben. Weitere Informationen finden Sie unter [Introduction to LINQ Queries (Einführung in LINQ-Abfragen)](../programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
## <a name="example"></a>Beispiel  
  
## <a name="method-syntax"></a>Methodensyntax  
 Einige Abfragevorgänge müssen als Methodenaufruf ausgedrückt werden. Die am häufigsten vorkommenden Methoden dieser Art sind die, die einzelne numerische Singleton-Werte zurückgeben, z.B. <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> und so weiter. Diese Methoden müssen in einer Abfrage immer zuletzt aufgerufen werden, da sie nur einen einzelnen Wert darstellen und nicht als Quelle für einen zusätzlichen Abfragevorgang dienen können. Im folgenden Beispiel wird ein Methodenaufruf in einem Abfrageausdruck dargestellt:  
  
 [!code-cs[csProgGuideLINQ#6](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]  
  
## <a name="example"></a>Beispiel  
 Wenn die Methode über Aktions- oder Func-Parameter verfügt, werden diese in Form eines [Lambdaausdruckes](../programming-guide/statements-expressions-operators/lambda-expressions.md) zur Verfügung gestellt, wie im folgenden Beispiel gezeigt wird:  
  
 [!code-cs[csProgGuideLINQ#7](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]  
  
 Von den vorherigen Abfragen wird nur die vierte Abfrage sofort ausgeführt. Das liegt daran, dass sie einen einzelnen Wert zurückgibt und keine generische <xref:System.Collections.Generic.IEnumerable%601>-Auflistung. Die Methode selbst muss `foreach` verwenden, um einen Wert zu berechnen.  
  
 Alle vorherigen Abfragen können mithilfe von implizierter Typisierung mit [var](../language-reference/keywords/var.md) geschrieben werden. Dies wird im folgenden Beispiel gezeigt:  
  
 [!code-cs[csProgGuideLINQ#8](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]  
  
## <a name="example"></a>Beispiel  
  
## <a name="mixed-query-and-method-syntax"></a>Gemischte Abfrage und Methodensyntax  
 In diesem Beispiel wird veranschaulicht, wie Sie die Methodensyntax auf die Ergebnisse einer Abfrageklausel anwenden können. Umschließen Sie einfach den Abfrageausdruck mit Klammern, wenden Sie anschließend den Punktoperator an, und rufen Sie die Methode auf. Im folgenden Beispiel wird von der siebten Abfrage die Anzahl der Zahlen zurückgegeben, deren Wert zwischen 3 und 7 liegt. Im Allgemeinen ist es jedoch besser, eine zweite Variable zu verwenden, um das Ergebnis des zweiten Methodenaufrufs zu speichern. Auf diese Weise ist es unwahrscheinlicher, dass dieses Ergebnis mit dem Ergebnis der Abfrage verwechselt wird.  
  
 [!code-cs[csProgGuideLINQ#9](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]  
  
 Da Abfrage Nr.7 einen einzelnen Wert und keine Auflistung zurückgibt, wird die Abfrage sofort ausgeführt.  
  
 Die vorherige Abfrage kann mithilfe der implizierten Typisierung mit `var` wie folgt geschrieben werden:  
  
```csharp  
var numCount = (from num in numbers...  
```  
  
 Sie kann folgendermaßen in Methodensyntax geschrieben werden:  
  
```csharp  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 Sie kann mithilfe der implizierten Typisierung wie folgt geschrieben werden:  
  
```csharp  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## <a name="see-also"></a>Siehe auch  
  [Exemplarische Vorgehensweise: Schreiben von Abfragen in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [LINQ-Abfrageausdrücke](index.md)   
 [where-Klausel](../language-reference/keywords/where-clause.md)
