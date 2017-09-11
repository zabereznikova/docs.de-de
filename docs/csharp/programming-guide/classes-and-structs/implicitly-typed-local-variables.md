---
title: Implizit typisierte lokale Variablen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cc02c0f7ef5fbbbf3c60188426a8027f6a60fb89
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="aa7d4-102">Implizit typisierte lokale Variablen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="aa7d4-102">Implicitly Typed Local Variables (C# Programming Guide)</span></span>
<span data-ttu-id="aa7d4-103">Lokale Variablen können deklariert werden, ohne einen expliziten Typ anzugeben.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="aa7d4-104">Das `var`-Schlüsselwort weist den Compiler an, den Typ der Variablen vom Ausdruck auf der rechten Seite der Initialisierungsanweisung abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="aa7d4-105">Der hergeleitete Typ ist möglicherweise ein integrierter Typ, ein anonymer Typ, ein benutzerdefinierter Typ oder ein Typ, der in der .NET Framework-Klassenbibliothek definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="aa7d4-106">Weitere Informationen zur Initialisierung von Arrays mithilfe von `var` finden Sie unter [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="aa7d4-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
 <span data-ttu-id="aa7d4-107">Die folgenden Beispiele veranschaulichen verschiedene Arten, wie Sie lokale Variablen mit `var` deklarieren können:</span><span class="sxs-lookup"><span data-stu-id="aa7d4-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>  
  
 <span data-ttu-id="aa7d4-108">[!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="aa7d4-108">[!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]</span></span>  
  
 <span data-ttu-id="aa7d4-109">Es ist von großer Bedeutung zu verstehen, dass das `var`-Schlüsselwort nicht „variant“ bedeutet, und das es nicht darauf hinweist, dass die Variable schwach typisiert oder spät gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-109">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="aa7d4-110">Es bedeutet nur, dass der Compiler den angemessensten Typen bestimmt und zuweist.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-110">It just means that the compiler determines and assigns the most appropriate type.</span></span>  
  
 <span data-ttu-id="aa7d4-111">Das `var`-Schlüsselwort kann in folgendem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="aa7d4-111">The `var` keyword may be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="aa7d4-112">Für lokale Variablen (Variablen, die im Geltungsbereich der Methode deklariert wurden), wie in vorherigem Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-112">On local variables (variables declared at method scope) as shown in the previous example.</span></span>  
  
-   <span data-ttu-id="aa7d4-113">In einer [for](../../../csharp/language-reference/keywords/for.md)-Initialisierungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-113">In a [for](../../../csharp/language-reference/keywords/for.md) initialization statement.</span></span>  
  
    ```  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   <span data-ttu-id="aa7d4-114">In einer [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Initialisierungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-114">In a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) initialization statement.</span></span>  
  
    ```  
    foreach(var item in list){...}  
    ```  
  
-   <span data-ttu-id="aa7d4-115">In einer [using](../../../csharp/language-reference/keywords/using-statement.md)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-115">In a [using](../../../csharp/language-reference/keywords/using-statement.md) statement.</span></span>  
  
    ```  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 <span data-ttu-id="aa7d4-116">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="aa7d4-116">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>  
  
## <a name="var-and-anonymous-types"></a><span data-ttu-id="aa7d4-117">var und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="aa7d4-117">var and Anonymous Types</span></span>  
 <span data-ttu-id="aa7d4-118">In vielen Fällen ist der Einsatz von `var` optional und nur eine praktische Syntax.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-118">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="aa7d4-119">Wenn eine Variable allerdings mit einem anonymen Typ initialisiert wird, müssen Sie die Variable als `var` deklarieren, wenn Sie zu einem späteren Zeitpunkt auf die Eigenschaften des Objekts zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-119">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="aa7d4-120">Das ist ein häufiges Szenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdrücken.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-120">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="aa7d4-121">Weitere Informationen finden Sie unter [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="aa7d4-121">For more information, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="aa7d4-122">Aus der Perspektive Ihres Quellcodes hat ein anonymer Typ keinen Namen.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-122">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="aa7d4-123">Wenn eine Abfragevariable mit `var` initialisiert wurde, ist es deshalb nur möglich, auf die Eigenschaften in der zurückgegebenen Objektsequenz zuzugreifen, wenn Sie `var` in der `foreach`-Anweisung als Typen der Iterationvariablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-123">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>  
  
 <span data-ttu-id="aa7d4-124">[!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="aa7d4-124">[!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa7d4-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa7d4-125">Remarks</span></span>  
 <span data-ttu-id="aa7d4-126">Die folgenden Einschränkungen gelten für implizit typisierte Variablendeklarationen:</span><span class="sxs-lookup"><span data-stu-id="aa7d4-126">The following restrictions apply to implicitly-typed variable declarations:</span></span>  
  
-   <span data-ttu-id="aa7d4-127">`var` kann nur verwendet werden, wenn eine lokale Variable deklariert und in derselben Anweisung initialisiert wird; die Variable kann weder mit NULL noch mit einer Methodengruppe oder einer anonymen Funktion initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-127">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>  
  
-   <span data-ttu-id="aa7d4-128">`var` kann nicht für Felder im Klassenbereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-128">`var` cannot be used on fields at class scope.</span></span>  
  
-   <span data-ttu-id="aa7d4-129">Variablen, die mit `var` deklariert wurden, können nicht im Initialisierungsausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-129">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="aa7d4-130">Sprich, dieser Ausdruck ist gültig`: int i = (i = 20);`, aber dieser Ausdruck führt zu einem Kompilierzeitfehler: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="aa7d4-130">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>  
  
-   <span data-ttu-id="aa7d4-131">Es können nicht mehrere implizit typisierte Variablen in derselben Anweisung initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-131">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>  
  
-   <span data-ttu-id="aa7d4-132">Wenn sich ein Typ mit dem Namen `var` im Geltungsbereich befindet, löst sich das `var`-Schlüsselwort zu diesem Typnamen auf und wird nicht als Teil der Deklaration einer implizit typisierten lokalen Variablen behandelt.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-132">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>  
  
 <span data-ttu-id="aa7d4-133">`var` erweist sich auch bei Abfrageausdrücken als nützlich, deren genauer konstruierter Typ der Abfragevariable schwer ermittelbar ist.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-133">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="aa7d4-134">Dies kann bei Gruppierungs- und Sortierungsvorgängen auftreten.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-134">This can occur with grouping and ordering operations.</span></span>  
  
 <span data-ttu-id="aa7d4-135">Das `var`-Schlüsselwort erweist sich auch als nützlich, wenn es umständlich ist, den Variablentypen mit der Tastatur einzugeben – oder wenn der Typ offensichtlich ist, oder nicht zur Lesbarkeit des Codes beiträgt.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-135">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="aa7d4-136">`var` ist z.B. bei geschachtelten generischen Typen wie die, die in Gruppenvorgängen verwendet werden, auf diese Weise nützlich.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-136">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="aa7d4-137">In der folgenden Abfrage ist der Typ der Abfragevariablen `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-137">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="aa7d4-138">Solange dies Ihnen und denen, die Ihren Code verwalten müssen, klar ist, spricht nichts dagegen, implizite Typisierung aus Gründen der Zweckmäßigkeit und der Kürze zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-138">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>  
  
 <span data-ttu-id="aa7d4-139">[!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="aa7d4-139">[!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]</span></span>  
  
 <span data-ttu-id="aa7d4-140">Durch den Gebrauch von `var` besteht aber zumindest die Möglichkeit, dass Ihr Code für andere Entwickler schwerer zu verstehen ist.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-140">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="aa7d4-141">Aus diesem Grund wird `var` in der C#-Dokumentation nur dann verwendet, wenn es tatsächlich erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="aa7d4-141">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa7d4-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa7d4-142">See Also</span></span>  
 <span data-ttu-id="aa7d4-143">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="aa7d4-144">[Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-144">[Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md) </span></span>  
 <span data-ttu-id="aa7d4-145">[Vorgehensweise: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-145">[How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md) </span></span>  
 <span data-ttu-id="aa7d4-146">[Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-146">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="aa7d4-147">[Objekt- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-147">[Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span></span>  
 <span data-ttu-id="aa7d4-148">["var"](../../../csharp/language-reference/keywords/var.md) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-148">[var](../../../csharp/language-reference/keywords/var.md) </span></span>  
 <span data-ttu-id="aa7d4-149">[LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-149">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="aa7d4-150">[LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-150">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="aa7d4-151">[for](../../../csharp/language-reference/keywords/for.md) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-151">[for](../../../csharp/language-reference/keywords/for.md) </span></span>  
 <span data-ttu-id="aa7d4-152">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="aa7d4-152">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 [<span data-ttu-id="aa7d4-153">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aa7d4-153">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

