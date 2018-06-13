---
title: =&gt;-Operator (C#-Referenz)
ms.date: 10/02/2017
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: d1565e262fbd3ebcee2d1576a2a0c8ed3ba8ce38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288225"
---
# <a name="gt-operator-c-reference"></a>=&gt;-Operator (C#-Referenz)

Der `=>`-Operator kann durch zwei Methoden in C# verwendet werden:

- Als [Lambdaoperator](#lamba-operator) in einem [Lambdaausdruck](../../lambda-expressions.md), trennt es die Eingabevariablen vom Lambdatext.
 
- In einer [Ausdruckskörperdefinition](#expression-body-definition) trennt es einen Membernamen von der Memberimplementierung. 

## <a name="lambda-operator"></a>Lambdaoperator

Das `=>`-Token wird als Lambdaoperator bezeichnet. Es wird in *Lambdaausdrücken* verwendet, um die Eingabevariablen auf der linken Seite vom Lambdatext auf der rechten Seite zu trennen. Lambdaausdrücke sind mit anonymen Methoden vergleichbare Inlineausdrücke, sie sind aber flexibler. Sie werden häufig in LINQ-Abfragen verwendet, die in Methodensyntax ausgedrückt werden. Weitere Informationen finden Sie unter [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Das folgende Beispiel zeigt zwei Methoden zum Suchen und Anzeigen der Länge der kürzesten Zeichenfolge in einem Array von Zeichenfolgen. Im ersten Teil des Beispiels wird ein Lambdaausdruck (`w => w.Length`) auf jedes Element des `words`-Arrays angewendet, und dann wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um die kleinste Länge zu finden. Zum Vergleich zeigt der zweite Teil des Beispiels eine längere Lösung, bei der Abfragesyntax verwendet wird, um das gleiche zu erreichen.  
  
```csharp  
string[] words = { "cherry", "apple", "blueberry" };  
  
// Use method syntax to apply a lambda expression to each element  
// of the words array.   
int shortestWordLength = words.Min(w => w.Length);  
Console.WriteLine(shortestWordLength);  
  
// Compare the following code that uses query syntax.  
// Get the lengths of each word in the words array.  
var query = from w in words  
            select w.Length;  
// Apply the Min method to execute the query and get the shortest length.  
int shortestWordLength2 = query.Min();  
Console.WriteLine(shortestWordLength2);  
  
// Output:   
// 5  
// 5  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Operator `=>` verfügt über die gleiche Rangfolge wie der Zuweisungsoperator (`=`) und ist rechtsassoziativ.  
  
 Sie können den Typ der Eingabevariable explizit angeben oder vom Compiler ableiten lassen; in jedem Fall ist die Variable zur Kompilierzeit stark typisiert. Wenn Sie einen Typ angeben, müssen Sie den Typnamen und den Variablennamen wie im folgenden Beispiel gezeigt in Klammern setzen.  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck für die Überladung des Standardabfrageoperators <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> geschrieben wird, der zwei Argumente akzeptiert. Da der Lambda-Ausdruck über mehr als einen Parameter verfügt, müssen die Parameter in Klammern stehen. Der zweite Parameter `index` stellt den Index des aktuellen Elements in der Auflistung dar. Der `Where`-Ausdruck gibt alle Zeichenfolgen zurück, deren Länge ihre jeweilige Indexposition im Array unterschreitet.  
  
```csharp  
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
## <a name="expression-body-definition"></a>Ausdruckskörperdefinition

Eine Ausdruckskörperdefinition ermöglicht die Implementierung eines Members in einer sehr präzisen und lesbaren Form. Sie verwendet die folgende allgemeine Syntax:

```csharp
member => expression;
```
wobei *expression* ein gültiger Ausdruck ist. Beachten Sie, dass *expression* nur dann ein *Anweisungsausdruck* sein kann, wenn der Rückgabetyp des Members `void` ist oder der Member ein Konstruktor oder Finalizer ist.

Ausdruckskörperdefinitionen für Methoden und die Get-Anweisungen der Eigenschaft werden ab C# 6 unterstützt. Ausdruckskörperdefinitionen für Konstruktoren, Finalizer, Set-Anweisungen der Eigenschaft und Indizes werden ab C# 7 unterstützt.

Im Folgenden wird eine Ausdruckskörperdefinition für eine `Person.ToString`-Methode angegeben:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Diese ist eine kompakte Version der folgenden Methodendefinition:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
Ausführlichere Informationen zu Ausdruckskörperdefinitionen finden Sie unter [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="see-also"></a>Siehe auch  
[C#-Referenz](../../../csharp/language-reference/index.md)   
[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
[Lambda-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
[Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)