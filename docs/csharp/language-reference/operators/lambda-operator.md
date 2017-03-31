---
title: =&gt;-Operator (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a75967e61d2c674e87e321de1fb6e4062cca4f19
ms.lasthandoff: 03/13/2017

---
# <a name="gt-operator-c-reference"></a>=&gt;-Operator (C#-Referenz)
Das `=>`-Token wird als Lambdaoperator bezeichnet. Es wird in *Lambdaausdrücken* verwendet, um die Eingabevariablen auf der linken Seite vom Lambdatext auf der rechten Seite zu trennen. Lambdaausdrücke sind mit anonymen Methoden vergleichbare Inlineausdrücke, sie sind aber flexibler. Sie werden häufig in LINQ-Abfragen verwendet, die in Methodensyntax ausgedrückt werden. Weitere Informationen finden Sie unter [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Das folgende Beispiel zeigt zwei Methoden zum Suchen und Anzeigen der Länge der kürzesten Zeichenfolge in einem Array von Zeichenfolgen. Im ersten Teil des Beispiels wird ein Lambdaausdruck (`w => w.Length`) auf jedes Element des `words`-Arrays angewendet, und dann wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um die kleinste Länge zu finden. Zum Vergleich zeigt der zweite Teil des Beispiels eine längere Lösung, bei der Abfragesyntax verwendet wird, um das gleiche zu erreichen.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="remarks"></a>Hinweise  
 Der Operator `=>` verfügt über die gleiche Rangfolge wie der Zuweisungsoperator (`=`) und ist rechtsassoziativ.  
  
 Sie können den Typ der Eingabevariable explizit angeben oder vom Compiler ableiten lassen; in jedem Fall ist die Variable zur Kompilierzeit stark typisiert. Wenn Sie einen Typ angeben, müssen Sie den Typnamen und den Variablennamen wie im folgenden Beispiel gezeigt in Klammern setzen.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck für die Überladung des Standardabfrageoperators <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> geschrieben wird, der zwei Argumente akzeptiert. Da der Lambda-Ausdruck über mehr als einen Parameter verfügt, müssen die Parameter in Klammern stehen. Der zweite Parameter `index` stellt den Index des aktuellen Elements in der Auflistung dar. Der `Where`-Ausdruck gibt alle Zeichenfolgen zurück, deren Länge ihre jeweilige Indexposition im Array unterschreitet.  
  
```cs  
static void Main(string[] args)  
{  
    string[] digits = { "zero", "one", "two", "three", "four", "five",   
            "six", "seven", "eight", "nine" };  
  
    Console.WriteLine("Example that uses a lambda expression:");  
    var shortDigits = digits.Where((digit, index) => digit.Length < index);  
    foreach (var sD in shortDigits)  
    {  
        Console.WriteLine(sD);  
    }  
  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Lambda-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
