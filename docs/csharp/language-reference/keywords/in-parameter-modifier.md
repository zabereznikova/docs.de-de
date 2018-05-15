---
title: Modifizierer für in-Parameter (C#-Verweis)
ms.date: 03/06/2018
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: aa6720430a1d93d7eacb098962c09efad09a179f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="c4be6-102">Modifizierer für in-Parameter (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="c4be6-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="c4be6-103">Das Schlüsselwort `in` bewirkt, dass Argumente per Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c4be6-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="c4be6-104">Es ähnelt zwar den Schlüsselwörtern [ref](ref.md) oder [out](out-parameter-modifier.md), jedoch können `in`-Argumente nicht von der aufgerufenen Methode verändert werden, `ref`-Argumente hingegen schon. `out`-Argumente müssen hingegen vom Aufrufer verändert werden. Diese Veränderungen können im aufrufenden Kontext überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="c4be6-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method, whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="c4be6-105">Das vorausgehende Beispiel veranschaulicht, dass der `in`-Modifizierer an der Aufrufstelle nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c4be6-105">The preceding example demonstrates the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="c4be6-106">Er ist nur in der Methodendeklaration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4be6-106">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="c4be6-107">Das `in`-Schlüsselwort kann ebenfalls mit einem generischen Typparameter verwendet werden, um als der Bestandteil einer `foreach`-Anweisung oder einer `join`-Klausel in einer LINQ-Abfrage anzugeben, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="c4be6-107">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="c4be6-108">Weitere Informationen zur Verwendung des `in`-Schlüsselworts in diesen Kontexten und entsprechende Links finden Sie unter [in](in.md).</span><span class="sxs-lookup"><span data-stu-id="c4be6-108">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
 <span data-ttu-id="c4be6-109">Variablen, die als `in`-Argumente übergeben wurden, müssen initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c4be6-109">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="c4be6-110">Es kann jedoch sein, dass die aufgerufene Methode keinen Wert zuweist oder das Argument ändert.</span><span class="sxs-lookup"><span data-stu-id="c4be6-110">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="c4be6-111">Obwohl die Schlüsselwörter `in`, `ref` und `out` unterschiedliche Laufzeitverhalten hervorrufen, gelten sie zum Zeitpunkt der Kompilierung nicht als Teil der Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="c4be6-111">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="c4be6-112">Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`- oder `in`-Argument übernimmt und die andere ein `out`-Argument.</span><span class="sxs-lookup"><span data-stu-id="c4be6-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="c4be6-113">Der folgende Code wird z. B. nicht kompiliert:</span><span class="sxs-lookup"><span data-stu-id="c4be6-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="c4be6-114">Das Überladen bei vorhandenem `in` ist zulässig:</span><span class="sxs-lookup"><span data-stu-id="c4be6-114">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="c4be6-115">Regeln zur Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="c4be6-115">Overload resolution rules</span></span>

<span data-ttu-id="c4be6-116">Die Regeln zur Auflösung von Methodenüberladungen bei der Übergabe von Argumenten als Wert und durch `in` lassen sich nachvollziehen, wenn die Motivation für `in`-Argumente bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="c4be6-116">You can understand the overload resolution rules for methods with by value vs. `in` arguments through understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="c4be6-117">Wenn Methoden mit `in`-Parametern definiert werden, kann unter Umständen eine Leistungsoptimierung erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="c4be6-117">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="c4be6-118">Einige `struct`-Typargumente beanspruchen viel Speicherplatz. Wenn dann in Schleifen mit vielen Durchläufen oder kritischen Codepfaden Methoden aufgerufen werden, ist der Aufwand zum Kopieren dieser Strukturen enorm.</span><span class="sxs-lookup"><span data-stu-id="c4be6-118">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="c4be6-119">Durch die Deklaration von `in`-Parametern in Methoden wird festgelegt, dass Argumente sicher als Verweis übergeben werden, da die aufgerufene Methode nicht den Zustand des Arguments ändert.</span><span class="sxs-lookup"><span data-stu-id="c4be6-119">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="c4be6-120">Durch die Übergabe dieser Argumente als Verweis wird ein möglicherweise aufwendiges Kopieren vermieden.</span><span class="sxs-lookup"><span data-stu-id="c4be6-120">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span> 

<span data-ttu-id="c4be6-121">Die Angabe von `in` für Argumente an der Aufrufstelle ist üblicherweise optional.</span><span class="sxs-lookup"><span data-stu-id="c4be6-121">Specifying `in` on arguments at the call site is typically optional.</span></span> <span data-ttu-id="c4be6-122">Zwischen der Übergabe eines Arguments als Wert und der Übergabe als Verweis mithilfe des `in`-Modifizierers besteht kein semantischer Unterschied.</span><span class="sxs-lookup"><span data-stu-id="c4be6-122">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="c4be6-123">Der `in`-Modifizierer an der Aufrufstelle ist optional, da nicht kenntlich gemacht werden muss, dass sich der Wert des Arguments ändern kann.</span><span class="sxs-lookup"><span data-stu-id="c4be6-123">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="c4be6-124">Explizit geben Sie den `in`-Modifizierer an der Aufrufstelle an, wenn Sie sicherstellen möchten, dass das Argument als Verweis und nicht als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c4be6-124">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="c4be6-125">Die explizite Verwendung von `in` hat zwei Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="c4be6-125">Explicitly using `in` has two effects:</span></span>

<span data-ttu-id="c4be6-126">Erstens wird der Compiler durch die Angabe von `in` an der Aufrufstelle dazu gezwungen, die Methode mit dem übereinstimmenden `in`-Parameter auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c4be6-126">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="c4be6-127">Wenn dies nicht der Fall ist und sich zwei Methoden nur durch die Angabe von `in` unterscheiden, wird die Methode überladen, für die Argumente als Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c4be6-127">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="c4be6-128">Zweitens wird durch `in` festgelegt, dass ein Argument als Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c4be6-128">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="c4be6-129">Das mit `in` verwendete Argument muss einen Speicherort darstellen, auf den direkt verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c4be6-129">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="c4be6-130">Es gelten dieselben Regeln wie für `out`- und `ref`-Argumente: Sie können keine Konstanten, normale Eigenschaften oder andere Ausdrücke, die Werte erzeugen, verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4be6-130">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="c4be6-131">Wird `in` an der Aufrufstelle weggelassen, wird der Compiler darüber informiert, dass die Erstellung einer temporären Variable und deren Übergabe als schreibgeschützter Verweis an die Methode zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="c4be6-131">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="c4be6-132">Der Compiler erstellt in diesem Fall eine temporäre Variable, um mehrere Einschränkungen im Zusammenhang mit `in`-Argumenten zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="c4be6-132">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="c4be6-133">Eine temporäre Variable ermöglicht als Konstanten zur Kompilierzeit `in`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="c4be6-133">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="c4be6-134">Eine temporäre Variable ermöglicht Eigenschaften oder andere Ausdrücke für `in`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="c4be6-134">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="c4be6-135">Eine temporäre Variable ermöglicht Argumente, bei denen eine implizite Konvertierung des Argumenttyps in den Parametertyp vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="c4be6-135">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="c4be6-136">In den oben beschriebenen Fällen erstellt der Compiler eine temporäre Variable, die den Wert einer Konstante, einer Eigenschaft oder eines anderen Ausdrucks speichert.</span><span class="sxs-lookup"><span data-stu-id="c4be6-136">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="c4be6-137">Das folgende Codebeispiel veranschaulicht diese Regeln:</span><span class="sxs-lookup"><span data-stu-id="c4be6-137">The following code illustrates these rules:</span></span>

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="c4be6-138">Gehen wir nun davon aus, dass eine weitere Methode verfügbar ist, für die Argumente als Wert übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="c4be6-138">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="c4be6-139">Wie im folgenden Codebeispiel zu sehen ist, ändern sich die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="c4be6-139">The results change as shown in the following code:</span></span>

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="c4be6-140">Nur beim letzten Methodenaufruf wird das Argument als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="c4be6-140">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="c4be6-141">Im obigen Code wird aus Gründen der Einfachheit `int` als Argumenttyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4be6-141">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="c4be6-142">Da auf den meisten modernen Computern `int` nicht größer ist als ein Verweis, ergibt sich kein Vorteil daraus, einen einzelnen `int`-Wert als schreibgeschützten Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c4be6-142">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span> 

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="c4be6-143">Einschränkungen für `in`-Parameter</span><span class="sxs-lookup"><span data-stu-id="c4be6-143">Limitations on `in` parameters</span></span>

<span data-ttu-id="c4be6-144">Sie können keines der Schlüsselwörter `in`, `ref` und `out` für die folgenden Methodentypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="c4be6-144">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="c4be6-145">Asynchrone Methoden, die Sie mit dem [async](async.md)-Modifizierer definieren.</span><span class="sxs-lookup"><span data-stu-id="c4be6-145">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="c4be6-146">Iterator-Methoden, die eine [yield return](yield.md)- oder `yield break`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="c4be6-146">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="c4be6-147">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c4be6-147">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c4be6-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4be6-148">See Also</span></span>  
 [<span data-ttu-id="c4be6-149">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c4be6-149">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="c4be6-150">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c4be6-150">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="c4be6-151">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c4be6-151">C# Keywords</span></span>](index.md)  
 <span data-ttu-id="c4be6-152">[Methodenparameter ](method-parameters.md) [Verweissemantik mit Werttypen](../../reference-semantics-with-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="c4be6-152">[Method Parameters](method-parameters.md) [Reference Semantics with Value Types](../../reference-semantics-with-value-types.md)</span></span>
