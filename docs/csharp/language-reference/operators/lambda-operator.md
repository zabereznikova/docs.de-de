---
title: =&gt;-Operator (C#-Referenz)
ms.date: 10/02/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44cb0485aefa8b0ab10a00ae0525180020ce436d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="2dd63-102">=&gt;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2dd63-102">=&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="2dd63-103">Der `=>`-Operator kann auf zweierlei Weise in C# verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="2dd63-103">The `=>` operator can be used in two ways in C#:</span></span>

- <span data-ttu-id="2dd63-104">Als [Lambdaoperator](#lamba-operator) in einem [Lambdaausdruck](../../lambda-expressions.md) trennt er die Eingabevariablen vom Lambdatext.</span><span class="sxs-lookup"><span data-stu-id="2dd63-104">As the [lambda operator](#lamba-operator) in a [lambda expression](../../lambda-expressions.md), it separates the input variables from the lambda body.</span></span>
 
- <span data-ttu-id="2dd63-105">In einer [Ausdruckskörperdefinition](#expression-body-definition) trennt er einen Membernamen von der Memberimplementierung.</span><span class="sxs-lookup"><span data-stu-id="2dd63-105">In an [expression body definition](#expression-body-definition), it separates a member name from the member implementation.</span></span> 

## <a name="lambda-operator"></a><span data-ttu-id="2dd63-106">Lambdaoperator</span><span class="sxs-lookup"><span data-stu-id="2dd63-106">Lambda operator</span></span>

<span data-ttu-id="2dd63-107">Das `=>`-Token wird als Lambdaoperator bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2dd63-107">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="2dd63-108">Es wird in *Lambdaausdrücken* verwendet, um die Eingabevariablen auf der linken Seite vom Lambdatext auf der rechten Seite zu trennen.</span><span class="sxs-lookup"><span data-stu-id="2dd63-108">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="2dd63-109">Lambdaausdrücke sind mit anonymen Methoden vergleichbare Inlineausdrücke, sie sind aber flexibler. Sie werden häufig in LINQ-Abfragen verwendet, die in Methodensyntax ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="2dd63-109">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="2dd63-110">Weitere Informationen finden Sie unter [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2dd63-110">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="2dd63-111">Das folgende Beispiel zeigt zwei Methoden zum Suchen und Anzeigen der Länge der kürzesten Zeichenfolge in einem Array von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2dd63-111">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="2dd63-112">Im ersten Teil des Beispiels wird ein Lambdaausdruck (`w => w.Length`) auf jedes Element des `words`-Arrays angewendet, und dann wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um die kleinste Länge zu finden.</span><span class="sxs-lookup"><span data-stu-id="2dd63-112">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="2dd63-113">Zum Vergleich zeigt der zweite Teil des Beispiels eine längere Lösung, bei der Abfragesyntax verwendet wird, um das gleiche zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="2dd63-113">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
### <a name="remarks"></a><span data-ttu-id="2dd63-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2dd63-114">Remarks</span></span>  
 <span data-ttu-id="2dd63-115">Der Operator `=>` verfügt über die gleiche Rangfolge wie der Zuweisungsoperator (`=`) und ist rechtsassoziativ.</span><span class="sxs-lookup"><span data-stu-id="2dd63-115">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="2dd63-116">Sie können den Typ der Eingabevariablen explizit angeben oder vom Compiler ableiten lassen; in jedem Fall ist die Variable zur Kompilierzeit stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="2dd63-116">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="2dd63-117">Wenn Sie einen Typ angeben, müssen Sie den Typnamen und den Variablennamen wie im folgenden Beispiel gezeigt in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="2dd63-117">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a><span data-ttu-id="2dd63-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2dd63-118">Example</span></span>  
 <span data-ttu-id="2dd63-119">Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck für die Überladung des Standardabfrageoperators <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> geschrieben wird, der zwei Argumente akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="2dd63-119">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> that takes two arguments.</span></span> <span data-ttu-id="2dd63-120">Da der Lambdaausdruck über mehr als einen Parameter verfügt, müssen die Parameter in Klammern stehen.</span><span class="sxs-lookup"><span data-stu-id="2dd63-120">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="2dd63-121">Der zweite Parameter `index` stellt den Index des aktuellen Elements in der Auflistung dar.</span><span class="sxs-lookup"><span data-stu-id="2dd63-121">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="2dd63-122">Der `Where`-Ausdruck gibt alle Zeichenfolgen zurück, deren Länge ihre jeweilige Indexposition im Array unterschreitet.</span><span class="sxs-lookup"><span data-stu-id="2dd63-122">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
## <a name="expression-body-definition"></a><span data-ttu-id="2dd63-123">Ausdruckskörperdefinition</span><span class="sxs-lookup"><span data-stu-id="2dd63-123">Expression body definition</span></span>

<span data-ttu-id="2dd63-124">Eine Ausdruckskörperdefinition gibt die Implementierung eines Members in einer stark komprimierten lesbaren Form an.</span><span class="sxs-lookup"><span data-stu-id="2dd63-124">An expression body definition provides a member's implementation in a highly condensed, readable form.</span></span> <span data-ttu-id="2dd63-125">Die allgemeine Syntax sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="2dd63-125">It has the following general syntax:</span></span>

```csharp
member => expression;
```
<span data-ttu-id="2dd63-126">wobei *expression* ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="2dd63-126">where *expression* is a valid expression.</span></span> <span data-ttu-id="2dd63-127">Beachten Sie, dass *expression* nur dann ein *Anweisungsausdruck* sein kann, wenn der Rückgabetyp des Members `void` oder der Member ein Konstruktor oder Finalizer ist.</span><span class="sxs-lookup"><span data-stu-id="2dd63-127">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor or a finalizer.</span></span>

<span data-ttu-id="2dd63-128">Ausdruckskörperdefinitionen für Methoden und Anweisungen zum Abrufen von Eigenschaften werden seit C# 6 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2dd63-128">Expression body definitions for methods and property get statements are supported starting with C# 6.</span></span> <span data-ttu-id="2dd63-129">Ausdruckskörperdefinitionen für Konstruktoren, Finalizer, Anweisungen zum Festlegen von Eigenschaften und Indexer werden seit C# 7 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2dd63-129">Expression body definitions for constructors, finalizers, property set statements, and indexers are supported starting with C# 7.</span></span>

<span data-ttu-id="2dd63-130">Im Folgenden finden Sie eine Ausdruckskörperdefinition für eine `Person.ToString`-Methode:</span><span class="sxs-lookup"><span data-stu-id="2dd63-130">The following is an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="2dd63-131">Es handelt sich um eine verkürzte Version der folgenden Methodendefinition:</span><span class="sxs-lookup"><span data-stu-id="2dd63-131">It is a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
<span data-ttu-id="2dd63-132">Ausführlichere Informationen zu Ausdruckskörperdefinitionen finden Sie unter [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="2dd63-132">For more detailed information on expression body definitions, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2dd63-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dd63-133">See Also</span></span>  
<span data-ttu-id="2dd63-134">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2dd63-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="2dd63-135">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2dd63-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
<span data-ttu-id="2dd63-136">[Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="2dd63-136">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
<span data-ttu-id="2dd63-137">[Ausdruckskörpermember ](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="2dd63-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>