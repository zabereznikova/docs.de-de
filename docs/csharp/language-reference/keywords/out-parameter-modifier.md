---
title: "Modifizierer für out-Parameter (C#-Verweis)"
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c0686d8bb0dec2a5ea6dd92491e58c93b7ee53a8
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="0981a-102">Modifizierer für out-Parameter (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="0981a-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="0981a-103">Das Schlüsselwort `out` bewirkt, dass Argumente per Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="0981a-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="0981a-104">Dies entspricht dem Schlüsselwort [ref](ref.md), mit Ausnahme davon, dass bei `ref` die Variable initialisiert sein muss, bevor sie übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="0981a-104">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="0981a-105">Es ähnelt auch dem Schlüsselwort [in](in-parameter-modifier.md). Allerdings lässt `in` nicht zu, dass die aufgerufene Methode den Argumentwert verändern kann.</span><span class="sxs-lookup"><span data-stu-id="0981a-105">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="0981a-106">Um einen Parameter `out` zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode das Schlüsselwort `out` explizit verwenden.</span><span class="sxs-lookup"><span data-stu-id="0981a-106">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="0981a-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0981a-107">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="0981a-108">Das Schlüsselwort `out` kann auch mit einem generischen Typparameter verwendet werden, um anzugeben, dass der Typparameter kovariant ist.</span><span class="sxs-lookup"><span data-stu-id="0981a-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="0981a-109">Weitere Informationen zur Verwendung des Schlüsselworts `out` in diesem Kontext finden Sie unter [out (generischer Modifizierer)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="0981a-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="0981a-110">Variablen, die als `out`-Argumente übergeben wurden, müssen nicht initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="0981a-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="0981a-111">Die aufgerufene Methode ist jedoch erforderlich, um einen Wert zuzuweisen, bevor die Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0981a-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="0981a-112">Obwohl die Schlüsselwörter `in`, `ref` und `out` unterschiedliche Laufzeitverhalten hervorrufen, gelten sie zum Zeitpunkt der Kompilierung nicht als Teil der Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="0981a-112">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="0981a-113">Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`- oder `in`-Argument übernimmt und die andere ein `out`-Argument.</span><span class="sxs-lookup"><span data-stu-id="0981a-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="0981a-114">Der folgende Code wird z. B. nicht kompiliert:</span><span class="sxs-lookup"><span data-stu-id="0981a-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="0981a-115">Überladen ist zwar legal, wenn jedoch eine Methode ein `ref`-, `in`- oder `out`-Argument übernimmt und die andere über keinen dieser Modifizierer verfügt, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0981a-115">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="0981a-116">Der Compiler wählt die beste Überladung aus, indem er die Parametermodifizierer auf der Aufrufsite den im Methodenaufruf verwendeten Parametermodifizierern zuordnet.</span><span class="sxs-lookup"><span data-stu-id="0981a-116">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="0981a-117">Eigenschaften sind keine Variablen und können daher nicht als `out`-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="0981a-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
 <span data-ttu-id="0981a-118">Weitere Informationen zum Übergeben von Arrays finden Sie unter [Übergeben von Arrays mit „ref“ und „out“](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="0981a-118">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="0981a-119">Sie können keines der Schlüsselwörter `in`, `ref` und `out` für die folgenden Methodentypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="0981a-119">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="0981a-120">Asynchrone Methoden, die Sie mit dem [async](../../../csharp/language-reference/keywords/async.md)-Modifizierer definieren.</span><span class="sxs-lookup"><span data-stu-id="0981a-120">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="0981a-121">Iterator-Methoden, die eine [yield return](../../../csharp/language-reference/keywords/yield.md)- oder `yield break`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="0981a-121">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="0981a-122">Deklarieren von `out`-Argumenten</span><span class="sxs-lookup"><span data-stu-id="0981a-122">Declaring `out` arguments</span></span>   

 <span data-ttu-id="0981a-123">Das Deklarieren einer Methode mit `out`-Argumenten ist nützlich, wenn eine Methode mehrere Werte zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="0981a-123">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="0981a-124">Im folgenden Beispiel wird `out` verwendet, um mit einem Methodenaufruf drei Variablen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="0981a-124">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="0981a-125">Beachten Sie, dass das dritte Argument Null zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0981a-125">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="0981a-126">Dadurch können Methoden Werte optional zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0981a-126">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

 <span data-ttu-id="0981a-127">Das [Try-Muster](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) umfasst die Rückgabe eines `bool`, um anzugeben, ob ein Vorgang erfolgreich war oder fehlschlug, und die Rückgabe des Werts, der durch den Vorgang in einem `out`-Argument erzeugt wurde.</span><span class="sxs-lookup"><span data-stu-id="0981a-127">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="0981a-128">Eine Reihe von Analysemethoden, z.B. [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@))), verwendet dieses Muster.</span><span class="sxs-lookup"><span data-stu-id="0981a-128">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="0981a-129">Aufrufen einer Methode mit einem `out`-Argument</span><span class="sxs-lookup"><span data-stu-id="0981a-129">Calling a method with an `out` argument</span></span>

<span data-ttu-id="0981a-130">In C# 6 und früheren Versionen müssen Sie eine Variable in einer separaten Anweisung deklarieren, bevor Sie es als ein `out`-Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="0981a-130">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="0981a-131">Das folgende Beispiel deklariert eine Variable namens `number`, bevor sie an die Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) übergeben wird, die versucht, eine Zeichenfolge in eine Zahl umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="0981a-131">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="0981a-132">Ab C# 7 können Sie in der Argumentliste des Methodenaufrufs anstatt in einer separaten Variablendeklaration die `out`-Variable deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0981a-132">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="0981a-133">Dies erzeugt kompakteren, lesbaren Code und verhindert auch, dass Sie versehentlich der Variable vor dem Aufruf der Methode einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0981a-133">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="0981a-134">Das folgende Beispiel ähnelt dem vorherigen Beispiel, außer dass es die `number`-Variable im Aufruf der Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@))) definiert.</span><span class="sxs-lookup"><span data-stu-id="0981a-134">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="0981a-135">Im vorherigen Beispiel ist die `number`-Variable stark als `int` typisiert.</span><span class="sxs-lookup"><span data-stu-id="0981a-135">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="0981a-136">Sie können auch eine implizit typisierte lokale Variable deklarieren, wie es im folgenden Beispiel getan wird.</span><span class="sxs-lookup"><span data-stu-id="0981a-136">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="0981a-137">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="0981a-137">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0981a-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0981a-138">See Also</span></span>  
 [<span data-ttu-id="0981a-139">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0981a-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0981a-140">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0981a-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0981a-141">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0981a-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0981a-142">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="0981a-142">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
