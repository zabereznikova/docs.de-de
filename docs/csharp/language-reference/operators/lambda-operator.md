---
title: =&gt;-Operator (C#-Referenz)
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 45d4753724ed094408e8cbc5353998a67071b0e4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="271a1-102">=&gt;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="271a1-102">=&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="271a1-103">Das `=>`-Token wird als Lambdaoperator bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="271a1-103">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="271a1-104">Es wird in *Lambdaausdrücken* verwendet, um die Eingabevariablen auf der linken Seite vom Lambdatext auf der rechten Seite zu trennen.</span><span class="sxs-lookup"><span data-stu-id="271a1-104">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="271a1-105">Lambdaausdrücke sind mit anonymen Methoden vergleichbare Inlineausdrücke, sie sind aber flexibler. Sie werden häufig in LINQ-Abfragen verwendet, die in Methodensyntax ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="271a1-105">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="271a1-106">Weitere Informationen finden Sie unter [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="271a1-106">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="271a1-107">Das folgende Beispiel zeigt zwei Methoden zum Suchen und Anzeigen der Länge der kürzesten Zeichenfolge in einem Array von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="271a1-107">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="271a1-108">Im ersten Teil des Beispiels wird ein Lambdaausdruck (`w => w.Length`) auf jedes Element des `words`-Arrays angewendet, und dann wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um die kleinste Länge zu finden.</span><span class="sxs-lookup"><span data-stu-id="271a1-108">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="271a1-109">Zum Vergleich zeigt der zweite Teil des Beispiels eine längere Lösung, bei der Abfragesyntax verwendet wird, um das gleiche zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="271a1-109">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="271a1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="271a1-110">Remarks</span></span>  
 <span data-ttu-id="271a1-111">Der Operator `=>` verfügt über die gleiche Rangfolge wie der Zuweisungsoperator (`=`) und ist rechtsassoziativ.</span><span class="sxs-lookup"><span data-stu-id="271a1-111">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="271a1-112">Sie können den Typ der Eingabevariable explizit angeben oder vom Compiler ableiten lassen; in jedem Fall ist die Variable zur Kompilierzeit stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="271a1-112">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="271a1-113">Wenn Sie einen Typ angeben, müssen Sie den Typnamen und den Variablennamen wie im folgenden Beispiel gezeigt in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="271a1-113">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
## <a name="example"></a><span data-ttu-id="271a1-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="271a1-114">Example</span></span>  
 <span data-ttu-id="271a1-115">Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck für die Überladung des Standardabfrageoperators <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> geschrieben wird, der zwei Argumente akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="271a1-115">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> that takes two arguments.</span></span> <span data-ttu-id="271a1-116">Da der Lambda-Ausdruck über mehr als einen Parameter verfügt, müssen die Parameter in Klammern stehen.</span><span class="sxs-lookup"><span data-stu-id="271a1-116">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="271a1-117">Der zweite Parameter `index` stellt den Index des aktuellen Elements in der Auflistung dar.</span><span class="sxs-lookup"><span data-stu-id="271a1-117">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="271a1-118">Der `Where`-Ausdruck gibt alle Zeichenfolgen zurück, deren Länge ihre jeweilige Indexposition im Array unterschreitet.</span><span class="sxs-lookup"><span data-stu-id="271a1-118">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="271a1-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="271a1-119">See Also</span></span>  
 <span data-ttu-id="271a1-120">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="271a1-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="271a1-121">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="271a1-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="271a1-122">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="271a1-122">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)

