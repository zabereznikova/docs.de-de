---
title: Modifizierer für out-Parameter – C#-Verweis
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 57308992268e1285cfeb82b28e2abf213e7a831b
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805861"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="b8a3f-102">Modifizierer für out-Parameter (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="b8a3f-102">out parameter modifier (C# Reference)</span></span>

<span data-ttu-id="b8a3f-103">Das Schlüsselwort `out` bewirkt, dass Argumente per Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="b8a3f-104">Es stellt den formalen Parameter als Alias für das Argument dar, das eine Variable sein muss.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="b8a3f-105">Anders ausgedrückt, jede Operation mit dem Parameter wird mit dem Argument durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="b8a3f-106">Dies entspricht dem Schlüsselwort [ref](ref.md), mit Ausnahme davon, dass bei `ref` die Variable initialisiert sein muss, bevor sie übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-106">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="b8a3f-107">Es ähnelt auch dem Schlüsselwort [in](in-parameter-modifier.md). Allerdings lässt `in` nicht zu, dass die aufgerufene Methode den Argumentwert verändern kann.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-107">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="b8a3f-108">Um einen Parameter `out` zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode das Schlüsselwort `out` explizit verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-108">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="b8a3f-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b8a3f-109">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE]
> <span data-ttu-id="b8a3f-110">Das Schlüsselwort `out` kann auch mit einem generischen Typparameter verwendet werden, um anzugeben, dass der Typparameter kovariant ist.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-110">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="b8a3f-111">Weitere Informationen zur Verwendung des Schlüsselworts `out` in diesem Kontext finden Sie unter [out (generischer Modifizierer)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="b8a3f-111">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="b8a3f-112">Variablen, die als `out`-Argumente übergeben wurden, müssen nicht initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-112">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="b8a3f-113">Die aufgerufene Methode ist jedoch erforderlich, um einen Wert zuzuweisen, bevor die Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-113">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="b8a3f-114">Die Schlüsselwörter `in`, `ref` und `out` werden nicht als Teil der Methodensignatur zum Zwecke der Überladungsauflösung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-114">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="b8a3f-115">Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`- oder `in`-Argument übernimmt und die andere ein `out`-Argument.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-115">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="b8a3f-116">Der folgende Code wird z. B. nicht kompiliert:</span><span class="sxs-lookup"><span data-stu-id="b8a3f-116">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="b8a3f-117">Überladen ist zwar legal, wenn jedoch eine Methode ein `ref`-, `in`- oder `out`-Argument übernimmt und die andere über keinen dieser Modifizierer verfügt, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b8a3f-117">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="b8a3f-118">Der Compiler wählt die beste Überladung aus, indem er die Parametermodifizierer auf der Aufrufsite den im Methodenaufruf verwendeten Parametermodifizierern zuordnet.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-118">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>

<span data-ttu-id="b8a3f-119">Eigenschaften sind keine Variablen und können daher nicht als `out`-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-119">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="b8a3f-120">Sie können keines der Schlüsselwörter `in`, `ref` und `out` für die folgenden Methodentypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="b8a3f-120">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="b8a3f-121">Asynchrone Methoden, die Sie mit dem [async](./async.md)-Modifizierer definieren.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-121">Async methods, which you define by using the [async](./async.md) modifier.</span></span>  
  
- <span data-ttu-id="b8a3f-122">Iterator-Methoden, die eine [yield return](./yield.md)- oder `yield break`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-122">Iterator methods, which include a [yield return](./yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="b8a3f-123">Für [Erweiterungsmethoden](../../programming-guide/classes-and-structs/extension-methods.md) gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="b8a3f-123">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="b8a3f-124">Das `out`-Schlüsselwort kann nicht für das erste Argument einer Erweiterungsmethode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-124">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="b8a3f-125">Das `ref`-Schlüsselwort kann nicht für das erste Argument einer Erweiterungsmethode verwendet werden, wenn es sich bei dem Argument nicht um eine Struktur handelt oder ein generischer Typ nicht auf eine Struktur beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-125">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="b8a3f-126">Das `in`-Schlüsselwort kann nur verwendet werden, wenn das erste Argument eine Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-126">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="b8a3f-127">Das `in`-Schlüsselwort kann nicht für einen generischen Typ verwendet werden – selbst bei einer Beschränkung auf eine Struktur.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-127">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="declaring-out-parameters"></a><span data-ttu-id="b8a3f-128">Deklarieren eines `out`-Parameters</span><span class="sxs-lookup"><span data-stu-id="b8a3f-128">Declaring `out` parameters</span></span>

<span data-ttu-id="b8a3f-129">Das Deklarieren einer Methode mit `out`-Argumenten ist eine gängige Methode, um mehrere Werte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-129">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="b8a3f-130">Ab C# 7.0 sollten Sie [Tupel](../../tuples.md) für ähnliche Szenarien berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-130">Beginning with C# 7.0, consider [tuples](../../tuples.md) for similar scenarios.</span></span> <span data-ttu-id="b8a3f-131">Im folgenden Beispiel wird `out` verwendet, um mit einem Methodenaufruf drei Variablen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-131">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="b8a3f-132">Das dritte Argument ist NULL zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-132">The third argument is assigned to null.</span></span> <span data-ttu-id="b8a3f-133">Dadurch können Methoden Werte optional zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-133">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="b8a3f-134">Aufrufen einer Methode mit einem `out`-Argument</span><span class="sxs-lookup"><span data-stu-id="b8a3f-134">Calling a method with an `out` argument</span></span>

<span data-ttu-id="b8a3f-135">In C# 6 und früheren Versionen müssen Sie eine Variable in einer separaten Anweisung deklarieren, bevor Sie es als ein `out`-Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-135">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="b8a3f-136">Das folgende Beispiel deklariert eine Variable namens `number`, bevor sie an die Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) übergeben wird, die versucht, eine Zeichenfolge in eine Zahl umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-136">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="b8a3f-137">Ab C# 7.0 können Sie in der Argumentliste des Methodenaufrufs anstatt in einer separaten Variablendeklaration die `out`-Variable deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-137">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="b8a3f-138">Dies erzeugt kompakteren, lesbaren Code und verhindert auch, dass Sie versehentlich der Variable vor dem Aufruf der Methode einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-138">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="b8a3f-139">Das folgende Beispiel ähnelt dem vorherigen Beispiel, außer dass es die `number`-Variable im Aufruf der Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@))) definiert.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-139">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  

<span data-ttu-id="b8a3f-140">Im vorherigen Beispiel ist die `number`-Variable stark als `int` typisiert.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-140">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="b8a3f-141">Sie können auch eine implizit typisierte lokale Variable deklarieren, wie es im folgenden Beispiel getan wird.</span><span class="sxs-lookup"><span data-stu-id="b8a3f-141">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="b8a3f-142">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b8a3f-142">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b8a3f-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8a3f-143">See also</span></span>

- [<span data-ttu-id="b8a3f-144">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b8a3f-144">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b8a3f-145">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b8a3f-145">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b8a3f-146">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b8a3f-146">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="b8a3f-147">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="b8a3f-147">Method Parameters</span></span>](./method-parameters.md)
