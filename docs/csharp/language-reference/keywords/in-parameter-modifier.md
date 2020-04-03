---
title: Modifizierer für in-Parameter – C#-Verweis
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 20956f9e25b6830a8876824a4c9dad1dbc4c4f3e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249369"
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="35b9c-102">Modifizierer für in-Parameter (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="35b9c-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="35b9c-103">Das Schlüsselwort `in` bewirkt, dass Argumente per Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="35b9c-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="35b9c-104">Es stellt den formalen Parameter als Alias für das Argument dar, das eine Variable sein muss.</span><span class="sxs-lookup"><span data-stu-id="35b9c-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="35b9c-105">Anders ausgedrückt, jede Operation mit dem Parameter wird mit dem Argument durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="35b9c-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="35b9c-106">Es verhält sich ähnlich wie die Schlüsselwörter [ref](ref.md) und [out](out-parameter-modifier.md). Der einzige Unterschied besteht darin, dass `in`-Argumente nicht von der aufgerufenen Methode modifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="35b9c-106">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="35b9c-107">Obwohl `ref`-Argumente modifiziert werden können, müssen `out`-Argumente von der aufgerufenen Methode geändert werden. Die Änderungen werden im Aufrufkontext angezeigt.</span><span class="sxs-lookup"><span data-stu-id="35b9c-107">Whereas `ref` arguments may be modified, `out` arguments must be modified by the called method, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="35b9c-108">Das vorausgehende Beispiel veranschaulicht, dass der `in`-Modifizierer an der Aufrufstelle normalerweise nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="35b9c-108">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="35b9c-109">Er ist nur in der Methodendeklaration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35b9c-109">It is only required in the method declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="35b9c-110">Das `in`-Schlüsselwort kann ebenfalls mit einem generischen Typparameter verwendet werden, um als der Bestandteil einer `foreach`-Anweisung oder einer `join`-Klausel in einer LINQ-Abfrage anzugeben, dass der Typparameter kontravariant ist.</span><span class="sxs-lookup"><span data-stu-id="35b9c-110">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="35b9c-111">Weitere Informationen zur Verwendung des `in`-Schlüsselworts in diesen Kontexten und entsprechende Links finden Sie unter [in](in.md).</span><span class="sxs-lookup"><span data-stu-id="35b9c-111">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
<span data-ttu-id="35b9c-112">Variablen, die als `in`-Argumente übergeben wurden, müssen initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="35b9c-112">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="35b9c-113">Es kann jedoch sein, dass die aufgerufene Methode keinen Wert zuweist oder das Argument ändert.</span><span class="sxs-lookup"><span data-stu-id="35b9c-113">However, the called method may not assign a value or modify the argument.</span></span>  

<span data-ttu-id="35b9c-114">Die `in`-Parametermodifizierer steht in C# 7.2 und höher zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="35b9c-114">The `in` parameter modifier is available in C# 7.2 and later.</span></span> <span data-ttu-id="35b9c-115">Frühere Versionen generieren den Compilerfehler `CS8107` (Das Feature „schreibgeschützte Verweise“ ist in C# 7.0 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35b9c-115">Previous versions generate compiler error `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span></span> <span data-ttu-id="35b9c-116">Verwenden Sie Sprachversion 7.2 oder höher.). Hinweise zum Konfigurieren der Compilersprachversion finden Sie unter [Auswählen der C#-Sprachversion](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="35b9c-116">Please use language version 7.2 or greater.") To configure the compiler language version, see [Select the C# language version](../configure-language-version.md).</span></span>

<span data-ttu-id="35b9c-117">Die Schlüsselwörter `in`, `ref` und `out` werden nicht als Teil der Methodensignatur zum Zwecke der Überladungsauflösung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="35b9c-117">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="35b9c-118">Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`- oder `in`-Argument übernimmt und die andere ein `out`-Argument.</span><span class="sxs-lookup"><span data-stu-id="35b9c-118">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="35b9c-119">Der folgende Code wird z. B. nicht kompiliert:</span><span class="sxs-lookup"><span data-stu-id="35b9c-119">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="35b9c-120">Das Überladen bei vorhandenem `in` ist zulässig:</span><span class="sxs-lookup"><span data-stu-id="35b9c-120">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="35b9c-121">Regeln zur Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="35b9c-121">Overload resolution rules</span></span>

<span data-ttu-id="35b9c-122">Die Regeln zur Auflösung von Methodenüberladungen bei der Übergabe von Argumenten als Wert und durch `in` lassen sich nachvollziehen, wenn die Motivation für `in`-Argumente bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="35b9c-122">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="35b9c-123">Wenn Methoden mit `in`-Parametern definiert werden, kann unter Umständen eine Leistungsoptimierung erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="35b9c-123">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="35b9c-124">Einige `struct`-Typargumente beanspruchen viel Speicherplatz. Wenn dann in Schleifen mit vielen Durchläufen oder kritischen Codepfaden Methoden aufgerufen werden, ist der Aufwand zum Kopieren dieser Strukturen enorm.</span><span class="sxs-lookup"><span data-stu-id="35b9c-124">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="35b9c-125">Durch die Deklaration von `in`-Parametern in Methoden wird festgelegt, dass Argumente sicher als Verweis übergeben werden, da die aufgerufene Methode nicht den Zustand des Arguments ändert.</span><span class="sxs-lookup"><span data-stu-id="35b9c-125">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="35b9c-126">Durch die Übergabe dieser Argumente als Verweis wird ein möglicherweise aufwendiges Kopieren vermieden.</span><span class="sxs-lookup"><span data-stu-id="35b9c-126">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span>

<span data-ttu-id="35b9c-127">Die Angabe von `in` für Argumente an der Aufrufstelle ist üblicherweise optional.</span><span class="sxs-lookup"><span data-stu-id="35b9c-127">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="35b9c-128">Zwischen der Übergabe eines Arguments als Wert und der Übergabe als Verweis mithilfe des `in`-Modifizierers besteht kein semantischer Unterschied.</span><span class="sxs-lookup"><span data-stu-id="35b9c-128">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="35b9c-129">Der `in`-Modifizierer an der Aufrufstelle ist optional, da nicht kenntlich gemacht werden muss, dass sich der Wert des Arguments ändern kann.</span><span class="sxs-lookup"><span data-stu-id="35b9c-129">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="35b9c-130">Explizit geben Sie den `in`-Modifizierer an der Aufrufstelle an, wenn Sie sicherstellen möchten, dass das Argument als Verweis und nicht als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="35b9c-130">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="35b9c-131">Die explizite Verwendung von `in` hat die folgenden beiden Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="35b9c-131">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="35b9c-132">Erstens wird der Compiler durch die Angabe von `in` an der Aufrufstelle dazu gezwungen, die Methode mit dem übereinstimmenden `in`-Parameter auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="35b9c-132">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="35b9c-133">Wenn dies nicht der Fall ist und sich zwei Methoden nur durch die Angabe von `in` unterscheiden, wird die Methode überladen, für die Argumente als Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="35b9c-133">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="35b9c-134">Zweitens wird durch `in` festgelegt, dass ein Argument als Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="35b9c-134">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="35b9c-135">Das mit `in` verwendete Argument muss einen Speicherort darstellen, auf den direkt verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="35b9c-135">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="35b9c-136">Es gelten die gleichen allgemeinen Regeln für `out`- und `ref`-Argumente: Sie können keine Konstanten, normale Eigenschaften oder andere Ausdrücke, die Werte erzeugen, verwenden.</span><span class="sxs-lookup"><span data-stu-id="35b9c-136">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="35b9c-137">Wird `in` an der Aufrufstelle weggelassen, wird der Compiler darüber informiert, dass die Erstellung einer temporären Variable und deren Übergabe als schreibgeschützter Verweis an die Methode zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="35b9c-137">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="35b9c-138">Der Compiler erstellt in diesem Fall eine temporäre Variable, um mehrere Einschränkungen im Zusammenhang mit `in`-Argumenten zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="35b9c-138">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="35b9c-139">Eine temporäre Variable ermöglicht als Konstanten zur Kompilierzeit `in`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="35b9c-139">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="35b9c-140">Eine temporäre Variable ermöglicht Eigenschaften oder andere Ausdrücke für `in`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="35b9c-140">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="35b9c-141">Eine temporäre Variable ermöglicht Argumente, bei denen eine implizite Konvertierung des Argumenttyps in den Parametertyp vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="35b9c-141">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="35b9c-142">In den oben beschriebenen Fällen erstellt der Compiler eine temporäre Variable, die den Wert einer Konstante, einer Eigenschaft oder eines anderen Ausdrucks speichert.</span><span class="sxs-lookup"><span data-stu-id="35b9c-142">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="35b9c-143">Das folgende Codebeispiel veranschaulicht diese Regeln:</span><span class="sxs-lookup"><span data-stu-id="35b9c-143">The following code illustrates these rules:</span></span>

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

<span data-ttu-id="35b9c-144">Gehen wir nun davon aus, dass eine weitere Methode verfügbar ist, für die Argumente als Wert übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="35b9c-144">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="35b9c-145">Wie im folgenden Codebeispiel zu sehen ist, ändern sich die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="35b9c-145">The results change as shown in the following code:</span></span>

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

<span data-ttu-id="35b9c-146">Nur beim letzten Methodenaufruf wird das Argument als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="35b9c-146">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="35b9c-147">Im obigen Code wird aus Gründen der Einfachheit `int` als Argumenttyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="35b9c-147">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="35b9c-148">Da auf den meisten modernen Computern `int` nicht größer ist als ein Verweis, ergibt sich kein Vorteil daraus, einen einzelnen `int`-Wert als schreibgeschützten Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="35b9c-148">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span>

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="35b9c-149">Einschränkungen für `in`-Parameter</span><span class="sxs-lookup"><span data-stu-id="35b9c-149">Limitations on `in` parameters</span></span>

<span data-ttu-id="35b9c-150">Sie können keines der Schlüsselwörter `in`, `ref` und `out` für die folgenden Methodentypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="35b9c-150">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="35b9c-151">Asynchrone Methoden, die Sie mit dem [async](async.md)-Modifizierer definieren.</span><span class="sxs-lookup"><span data-stu-id="35b9c-151">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="35b9c-152">Iterator-Methoden, die eine [yield return](yield.md)- oder `yield break`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="35b9c-152">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>
- <span data-ttu-id="35b9c-153">Das erste Argument einer Erweiterungsmethode kann nur dann einen `in`-Modifizierer verwenden, wenn dieses Argument eine Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="35b9c-153">The first argument of an extension method cannot have the `in` modifier unless that argument is a struct.</span></span>
- <span data-ttu-id="35b9c-154">Das erste Argument einer Erweiterungsmethode, wenn es sich bei diesem Argument um einen generischen Typ handelt (selbst dann, wenn dieser Typ auf eine Struktur beschränkt ist).</span><span class="sxs-lookup"><span data-stu-id="35b9c-154">The first argument of an extension method where that argument is a generic type (even when that type is constrained to be a struct.)</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="35b9c-155">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="35b9c-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="35b9c-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35b9c-156">See also</span></span>

- [<span data-ttu-id="35b9c-157">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="35b9c-157">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="35b9c-158">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="35b9c-158">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="35b9c-159">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="35b9c-159">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="35b9c-160">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="35b9c-160">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="35b9c-161">Schreiben von sicherem und effizientem Code</span><span class="sxs-lookup"><span data-stu-id="35b9c-161">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
