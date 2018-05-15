---
title: Implizit typisierte lokale Variablen (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: a3cb2490247a6e9fdb51b73d405173d29263393c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="c079a-102">Implizit typisierte lokale Variablen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c079a-102">Implicitly Typed Local Variables (C# Programming Guide)</span></span>
<span data-ttu-id="c079a-103">Lokale Variablen können deklariert werden, ohne einen expliziten Typ anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c079a-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="c079a-104">Das `var`-Schlüsselwort weist den Compiler an, den Typ der Variablen vom Ausdruck auf der rechten Seite der Initialisierungsanweisung abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c079a-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="c079a-105">Der hergeleitete Typ ist möglicherweise ein integrierter Typ, ein anonymer Typ, ein benutzerdefinierter Typ oder ein Typ, der in der .NET Framework-Klassenbibliothek definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c079a-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="c079a-106">Weitere Informationen zur Initialisierung von Arrays mithilfe von `var` finden Sie unter [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="c079a-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
 <span data-ttu-id="c079a-107">Die folgenden Beispiele veranschaulichen verschiedene Arten, wie Sie lokale Variablen mit `var` deklarieren können:</span><span class="sxs-lookup"><span data-stu-id="c079a-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]  
  
 <span data-ttu-id="c079a-108">Es ist von großer Bedeutung zu verstehen, dass das `var`-Schlüsselwort nicht „variant“ bedeutet, und das es nicht darauf hinweist, dass die Variable schwach typisiert oder spät gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="c079a-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="c079a-109">Es bedeutet nur, dass der Compiler den angemessensten Typen bestimmt und zuweist.</span><span class="sxs-lookup"><span data-stu-id="c079a-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>  
  
 <span data-ttu-id="c079a-110">Das `var`-Schlüsselwort kann in folgendem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c079a-110">The `var` keyword may be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="c079a-111">Für lokale Variablen (Variablen, die im Geltungsbereich der Methode deklariert wurden), wie in vorherigem Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c079a-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>  
  
-   <span data-ttu-id="c079a-112">In einer [for](../../../csharp/language-reference/keywords/for.md)-Initialisierungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="c079a-112">In a [for](../../../csharp/language-reference/keywords/for.md) initialization statement.</span></span>  
  
    ```  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   <span data-ttu-id="c079a-113">In einer [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Initialisierungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="c079a-113">In a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) initialization statement.</span></span>  
  
    ```  
    foreach(var item in list){...}  
    ```  
  
-   <span data-ttu-id="c079a-114">In einer [using](../../../csharp/language-reference/keywords/using-statement.md)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c079a-114">In a [using](../../../csharp/language-reference/keywords/using-statement.md) statement.</span></span>  
  
    ```  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 <span data-ttu-id="c079a-115">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="c079a-115">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>  
  
## <a name="var-and-anonymous-types"></a><span data-ttu-id="c079a-116">var und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="c079a-116">var and Anonymous Types</span></span>  
 <span data-ttu-id="c079a-117">In vielen Fällen ist der Einsatz von `var` optional und nur eine praktische Syntax.</span><span class="sxs-lookup"><span data-stu-id="c079a-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="c079a-118">Wenn eine Variable allerdings mit einem anonymen Typ initialisiert wird, müssen Sie die Variable als `var` deklarieren, wenn Sie zu einem späteren Zeitpunkt auf die Eigenschaften des Objekts zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="c079a-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="c079a-119">Das ist ein häufiges Szenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdrücken.</span><span class="sxs-lookup"><span data-stu-id="c079a-119">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="c079a-120">Weitere Informationen finden Sie unter [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="c079a-120">For more information, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="c079a-121">Aus der Perspektive Ihres Quellcodes hat ein anonymer Typ keinen Namen.</span><span class="sxs-lookup"><span data-stu-id="c079a-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="c079a-122">Wenn eine Abfragevariable mit `var` initialisiert wurde, ist es deshalb nur möglich, auf die Eigenschaften in der zurückgegebenen Objektsequenz zuzugreifen, wenn Sie `var` in der `foreach`-Anweisung als Typen der Iterationvariablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c079a-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="c079a-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c079a-123">Remarks</span></span>  
 <span data-ttu-id="c079a-124">Die folgenden Einschränkungen gelten für implizit typisierte Variablendeklarationen:</span><span class="sxs-lookup"><span data-stu-id="c079a-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>  
  
-   <span data-ttu-id="c079a-125">`var` kann nur verwendet werden, wenn eine lokale Variable deklariert und in derselben Anweisung initialisiert wird; die Variable kann weder mit NULL noch mit einer Methodengruppe oder einer anonymen Funktion initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c079a-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>  
  
-   <span data-ttu-id="c079a-126">`var` kann nicht für Felder im Klassenbereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c079a-126">`var` cannot be used on fields at class scope.</span></span>  
  
-   <span data-ttu-id="c079a-127">Variablen, die mit `var` deklariert wurden, können nicht im Initialisierungsausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c079a-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="c079a-128">Sprich, dieser Ausdruck ist gültig`: int i = (i = 20);`, aber dieser Ausdruck führt zu einem Kompilierzeitfehler: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="c079a-128">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>  
  
-   <span data-ttu-id="c079a-129">Es können nicht mehrere implizit typisierte Variablen in derselben Anweisung initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c079a-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>  
  
-   <span data-ttu-id="c079a-130">Wenn sich ein Typ mit dem Namen `var` im Geltungsbereich befindet, löst sich das `var`-Schlüsselwort zu diesem Typnamen auf und wird nicht als Teil der Deklaration einer implizit typisierten lokalen Variablen behandelt.</span><span class="sxs-lookup"><span data-stu-id="c079a-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>  
  
 <span data-ttu-id="c079a-131">`var` erweist sich auch bei Abfrageausdrücken als nützlich, deren genauer konstruierter Typ der Abfragevariable schwer ermittelbar ist.</span><span class="sxs-lookup"><span data-stu-id="c079a-131">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="c079a-132">Dies kann bei Gruppierungs- und Sortierungsvorgängen auftreten.</span><span class="sxs-lookup"><span data-stu-id="c079a-132">This can occur with grouping and ordering operations.</span></span>  
  
 <span data-ttu-id="c079a-133">Das `var`-Schlüsselwort erweist sich auch als nützlich, wenn es umständlich ist, den Variablentypen mit der Tastatur einzugeben – oder wenn der Typ offensichtlich ist, oder nicht zur Lesbarkeit des Codes beiträgt.</span><span class="sxs-lookup"><span data-stu-id="c079a-133">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="c079a-134">`var` ist z.B. bei geschachtelten generischen Typen wie die, die in Gruppenvorgängen verwendet werden, auf diese Weise nützlich.</span><span class="sxs-lookup"><span data-stu-id="c079a-134">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="c079a-135">In der folgenden Abfrage ist der Typ der Abfragevariablen `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="c079a-135">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="c079a-136">Solange dies Ihnen und denen, die Ihren Code verwalten müssen, klar ist, spricht nichts dagegen, implizite Typisierung aus Gründen der Zweckmäßigkeit und der Kürze zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c079a-136">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]  
  
 <span data-ttu-id="c079a-137">Durch den Gebrauch von `var` besteht aber zumindest die Möglichkeit, dass Ihr Code für andere Entwickler schwerer zu verstehen ist.</span><span class="sxs-lookup"><span data-stu-id="c079a-137">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="c079a-138">Aus diesem Grund wird `var` in der C#-Dokumentation nur dann verwendet, wenn es tatsächlich erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c079a-138">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c079a-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c079a-139">See Also</span></span>  
 [<span data-ttu-id="c079a-140">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c079a-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c079a-141">Implizit typisierte Arrays</span><span class="sxs-lookup"><span data-stu-id="c079a-141">Implicitly Typed Arrays</span></span>](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)  
 [<span data-ttu-id="c079a-142">Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck</span><span class="sxs-lookup"><span data-stu-id="c079a-142">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)  
 [<span data-ttu-id="c079a-143">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="c079a-143">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="c079a-144">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="c079a-144">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [<span data-ttu-id="c079a-145">var</span><span class="sxs-lookup"><span data-stu-id="c079a-145">var</span></span>](../../../csharp/language-reference/keywords/var.md)  
 [<span data-ttu-id="c079a-146">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="c079a-146">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="c079a-147">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="c079a-147">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="c079a-148">for</span><span class="sxs-lookup"><span data-stu-id="c079a-148">for</span></span>](../../../csharp/language-reference/keywords/for.md)  
 [<span data-ttu-id="c079a-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="c079a-149">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="c079a-150">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c079a-150">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
