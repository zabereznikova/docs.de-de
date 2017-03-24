---
title: "Operator =&gt; (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "=>_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lambda-Operator [C#]"
  - "=>-Operator [C#]"
  - "Lambda-Ausdrücke [C#], Operator =>"
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Operator =&gt; (C#-Referenz)
Das `=>`\-Token wird als Operator Lambda bezeichnet.  Es wird in *Lambda\-Ausdrücken* verwendet, um die Eingabevariablen auf der linken Seite von dem Lambda\-Text auf der rechten Seite zu trennen.  Bei Lambda\-Ausdrücken handelt es sich um Inlineausdrücke, die anonymen Methoden ähneln, jedoch flexibler sind. Sie werden häufig in LINQ\-Abfragen in Methodensyntax verwendet.  Weitere Informationen finden Sie unter [Lambda\-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Im folgenden Beispiel werden zwei Möglichkeiten veranschaulicht, die Länge der kürzesten Zeichenfolge in einem Zeichenfolgenarray zu suchen und anzuzeigen.  Der erste Teil des Beispiels wird ein Lambda\-Ausdruck \(`w => w.Length`\) auf jedes Element des Arrays `words` und verwendet dann die <xref:System.Linq.Enumerable.Min%2A>\-Methode, um die kleinste Länge zu suchen.  Für Vergleich zeigt der zweite Teil des Beispiels eine längere Lösung an, die Abfragesyntax verwendet, um die gleichen Schritt auszuführen.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## Hinweise  
 Der Operator `=>` verfügt über die gleiche Rangfolge wie der Zuweisungsoperator \(`=`\) und ist rechtsassoziativ.  
  
 Sie können den Typ der Eingabevariable explizit angeben oder lassen den Compiler ihn ableiten; in jedem Fall ist die Variable zur Kompilierzeit stark typisiert.  Wenn Sie einen Typ angeben, müssen Sie den Typnamen und den Variablennamen in Klammern im folgenden Beispiel gezeigt, einschließen.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Lambda\-Ausdruck für die Überladung des Standardabfrageoperators <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> geschrieben wird, der zwei Argumente akzeptiert.  Da der Lambda\-Ausdruck mehr als einen \- Parameter verfügt, müssen die Parameter in Klammern stehen.  Der zweite Parameter, `index`, stellt den Index des aktuellen Elements in der Auflistung dar.  Der `Where` Ausdruck gibt alle Zeichenfolgen, deren Länge kleiner sind, als ihre Indexpositionen im Array zurück.  
  
```c#  
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
  
    // Compare the following code, which arrives at the same list of short  
    // digits but takes more work to get there.  
    Console.WriteLine("\nExample that uses a for loop:");  
    List<string> shortDigits2 = new List<string>();  
    for (var i = 0; i < digits.Length; i++)  
    {  
        if (digits[i].Length < i)  
            shortDigits2.Add(digits[i]);  
    }  
  
    foreach (var d in shortDigits2)  
    {  
        Console.WriteLine(d);  
    }  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
  
    // Example that uses a for loop:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Lambda\-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)