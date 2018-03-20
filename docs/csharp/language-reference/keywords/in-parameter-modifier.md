---
title: "Modifizierer für in-Parameter (C#-Verweis)"
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 035aac3e6b902f607e533b709713eb1d07c9774a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="a1ae4-102">Modifizierer für in-Parameter (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="a1ae4-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="a1ae4-103">Das Schlüsselwort `in` bewirkt, dass Argumente per Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="a1ae4-104">Es ähnelt zwar den Schlüsselwörtern [ref](ref.md) oder [out](out-parameter-modifier.md), jedoch können `in`-Argumente nicht von der aufgerufenen Methode verändert werden, `ref`-Argumente hingegen schon. `out`-Argumente müssen hingegen vom Aufrufer verändert werden. Diese Veränderungen können im aufrufenden Kontext überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method, whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="a1ae4-105">Das vorausgehende Beispiel veranschaulicht, dass der `in`-Bezeichner für die Aufrufsite nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-105">The preceding example demonstrates that the `in` modifier is unnecessary at the call site.</span></span> <span data-ttu-id="a1ae4-106">Er ist nur in der Methodendeklaration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-106">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="a1ae4-107">Das `in`-Schlüsselwort kann ebenfalls mit einem generischen Typparameter verwendet werden, um als der Bestandteil einer `foreach`-Anweisung oder einer `join`-Klausel in einer LINQ-Abfrage anzugeben, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-107">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="a1ae4-108">Weitere Informationen zur Verwendung des `in`-Schlüsselworts in diesen Kontexten und entsprechende Links finden Sie unter [in](in.md).</span><span class="sxs-lookup"><span data-stu-id="a1ae4-108">For more information on the use of the `in` keyword in these contexts, see [in](in.md) which provides links to all those uses.</span></span>
  
 <span data-ttu-id="a1ae4-109">Variablen, die als `in`-Argumente übergeben wurden, müssen initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-109">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="a1ae4-110">Es kann jedoch sein, dass die aufgerufene Methode keinen Wert zuweist oder das Argument ändert.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-110">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="a1ae4-111">Obwohl die Schlüsselwörter `in`, `ref` und `out` unterschiedliche Laufzeitverhalten hervorrufen, gelten sie zum Zeitpunkt der Kompilierung nicht als Teil der Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-111">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="a1ae4-112">Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`- oder `in`-Argument übernimmt und die andere ein `out`-Argument.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="a1ae4-113">Der folgende Code wird z. B. nicht kompiliert:</span><span class="sxs-lookup"><span data-stu-id="a1ae4-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="a1ae4-114">Überladungen sind zwar zulässig, wenn `in` vorhanden ist, es wird dadurch jedoch eine Compilerwarnung generiert:</span><span class="sxs-lookup"><span data-stu-id="a1ae4-114">Overloading based on the presence of `in` is allowed, but generates a compiler warning:</span></span>  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

<span data-ttu-id="a1ae4-115">Eigenschaften oder Konstanten können als `in`-Parameter übergeben werden, da die aufrufende Methode deren Werte möglicherweise nicht verändern kann.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-115">Properties or constants may be passed as `in` parameters, because the calling method may not modify their values.</span></span>
  
<span data-ttu-id="a1ae4-116">Sie können keines der Schlüsselwörter `in`, `ref` und `out` für die folgenden Methodentypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="a1ae4-116">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="a1ae4-117">Asynchrone Methoden, die Sie mit dem [async](../../../csharp/language-reference/keywords/async.md)-Modifizierer definieren.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-117">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
- <span data-ttu-id="a1ae4-118">Iterator-Methoden, die eine [yield return](../../../csharp/language-reference/keywords/yield.md)- oder `yield break`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-118">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="a1ae4-119">In der Regel deklarieren Sie `in`-Argumente, damit keine Kopiervorgänge durchgeführt werden müssen, die für das Übergeben von Argumenten nach Werten notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-119">You typically declare `in` arguments to avoid the copy operations necessary for passing arguments by value.</span></span> <span data-ttu-id="a1ae4-120">Dies ist besonders nützlich, wenn Argumente Strukturen oder Arrays mit Strukturen darstellen.</span><span class="sxs-lookup"><span data-stu-id="a1ae4-120">This is most useful when arguments are structures or arrays of structures.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a1ae4-121">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="a1ae4-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a1ae4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1ae4-122">See Also</span></span>  
 [<span data-ttu-id="a1ae4-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a1ae4-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a1ae4-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a1ae4-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a1ae4-125">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a1ae4-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a1ae4-126">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="a1ae4-126">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
