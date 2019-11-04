---
title: Ausführen von Ausdrucksbaumstrukturen
description: Informationen zum Ausführen von Ausdrucksbaumstrukturen, indem sie in Anweisungen einer ausführbaren Zwischensprache (IL) konvertiert werden.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 109e0ac5-2a9c-48b4-ac68-9b6219cdbccf
ms.openlocfilehash: 9af4b346962cb743daddf774e8b3c1f8fa722ae4
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037113"
---
# <a name="executing-expression-trees"></a><span data-ttu-id="a0fc5-103">Ausführen von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="a0fc5-103">Executing Expression Trees</span></span>

[<span data-ttu-id="a0fc5-104">Vorheriges – Framework-Typen, die Ausdrucksbaumstrukturen unterstützen</span><span class="sxs-lookup"><span data-stu-id="a0fc5-104">Previous -- Framework Types Supporting Expression Trees</span></span>](expression-classes.md)

<span data-ttu-id="a0fc5-105">Eine *Ausdrucksbaumstruktur* ist eine Datenstruktur, die Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-105">An *expression tree* is a data structure that represents some code.</span></span>
<span data-ttu-id="a0fc5-106">Es ist ein nicht kompilierter und ausführbarer Code.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-106">It is not compiled and executable code.</span></span> <span data-ttu-id="a0fc5-107">Wenn Sie den .NET-Code ausführen möchten, der durch eine Ausdrucksbaumstruktur dargestellt wird, müssen Sie ihn in ausführbare IL-Anweisungen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-107">If you want to execute the .NET code that is represented by an expression tree, you must convert it into executable IL instructions.</span></span>

## <a name="lambda-expressions-to-functions"></a><span data-ttu-id="a0fc5-108">Lambdaausdrücke zu Funktionen</span><span class="sxs-lookup"><span data-stu-id="a0fc5-108">Lambda Expressions to Functions</span></span>

<span data-ttu-id="a0fc5-109">Sie können jede LambdaExpression oder jeden Typ, der von LambdaExpression in eine ausführbare IL abgeleitet wurde, konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-109">You can convert any LambdaExpression, or any type derived from LambdaExpression into executable IL.</span></span> <span data-ttu-id="a0fc5-110">Andere Ausdruckstypen können nicht direkt in Code konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-110">Other expression types cannot be directly converted into code.</span></span> <span data-ttu-id="a0fc5-111">Diese Einschränkung wirkt sich kaum auf die Praxis aus.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-111">This restriction has little effect in practice.</span></span> <span data-ttu-id="a0fc5-112">Lambdaausdrücke sind die einzigen Typen von Ausdrücken, die Sie ausführen möchten, indem Sie sie in eine ausführbare Zwischensprache (Intermediate Language, IL) konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-112">Lambda expressions are the only types of expressions that you would want to execute by converting to executable intermediate language (IL).</span></span> <span data-ttu-id="a0fc5-113">(Denken Sie darüber nach, was es bedeuten würde, eine `ConstantExpression` direkt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-113">(Think about what it would mean to directly execute a `ConstantExpression`.</span></span> <span data-ttu-id="a0fc5-114">Würde es etwas Nützliches bedeuten?) Jede beliebige Ausdrucksbaumstruktur, die eine `LambdaExpression` ist, oder ein abgeleiteter Typ von `LambdaExpression`, kann in eine IL konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-114">Would it mean anything useful?) Any expression tree that is a `LambdaExpression`, or a type derived from `LambdaExpression` can be converted to IL.</span></span>
<span data-ttu-id="a0fc5-115">Der Ausdruckstyp `Expression<TDelegate>` ist das einzige konkrete Beispiel in den .NET Core-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-115">The expression type `Expression<TDelegate>` is the only concrete example in the .NET Core libraries.</span></span> <span data-ttu-id="a0fc5-116">Hiermit wird ein Ausdruck dargestellt, der jedem Delegattyp zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-116">It's used to represent an expression that maps to any delegate type.</span></span> <span data-ttu-id="a0fc5-117">Da dieser Typ einem Delegattyp zugeordnet ist, kann .NET den Ausdruck untersuchen, und die IL für einen entsprechenden Delegaten generieren, der der Signatur des Lambdaausdrucks entspricht.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-117">Because this type maps to a delegate type, .NET can examine the expression, and generate IL for an appropriate delegate that matches the signature of the lambda expression.</span></span> 

<span data-ttu-id="a0fc5-118">In den meisten Fällen erstellt dies eine einfache Zuordnung zwischen einem Ausdruck und seinem entsprechenden Delegaten.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-118">In most cases, this creates a simple mapping between an expression, and its corresponding delegate.</span></span> <span data-ttu-id="a0fc5-119">Angenommen, eine Ausdrucksbaumstruktur, die durch `Expression<Func<int>>` dargestellt wird, wird in einen Delegaten des Typs `Func<int>` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-119">For example, an expression tree that is represented by `Expression<Func<int>>` would be converted to a delegate of the type `Func<int>`.</span></span> <span data-ttu-id="a0fc5-120">Für einen Lambdaausdruck mit beliebigem Rückgabetyp und Argumentliste besteht ein Delegattyp, der der Zieltyp für den ausführbaren Code ist, der von diesem Lambdaausdruck dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-120">For a lambda expression with any return type and argument list, there exists a delegate type that is the target type for the executable code represented by that lambda expression.</span></span>

<span data-ttu-id="a0fc5-121">Der `LambdaExpression`-Typ enthält `Compile`- und `CompileToMethod`-Member, die Sie verwenden würden, um eine Ausdrucksbaumstruktur in ausführbaren Code zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-121">The `LambdaExpression` type contains `Compile` and `CompileToMethod` members that you would use to convert an expression tree to executable code.</span></span> <span data-ttu-id="a0fc5-122">Die `Compile`-Methode erstellt einen Delegaten.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-122">The `Compile` method creates a delegate.</span></span> <span data-ttu-id="a0fc5-123">Die `CompileToMethod`-Methode aktualisiert ein `MethodBuilder`-Objekt mit der IL, das die kompilierte Ausgabe der Ausdrucksbaumstruktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-123">The `CompileToMethod` method updates a `MethodBuilder` object with the IL that represents the compiled output of the expression tree.</span></span> <span data-ttu-id="a0fc5-124">Beachten Sie, dass `CompileToMethod` nur im Desktop-Framework verfügbar ist, nicht in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-124">Note that `CompileToMethod` is only available in the full desktop framework, not in the .NET Core.</span></span>

<span data-ttu-id="a0fc5-125">Optional können Sie auch einen `DebugInfoGenerator` angeben, der das Symbol „Debuginformationen“ für das generierte Delegatobjekt empfängt.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-125">Optionally, you can also provide a `DebugInfoGenerator` that will receive the symbol debugging information for the generated delegate object.</span></span> <span data-ttu-id="a0fc5-126">Dies ermöglicht es Ihnen, die Ausdrucksbaumstruktur in ein Delegatobjekt zu konvertieren, und über vollständige Debuginformationen über die generierten Delegate zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-126">This enables you to convert the expression tree into a delegate object, and have full debugging information about the generated delegate.</span></span>

<span data-ttu-id="a0fc5-127">Sie würden einen Ausdruck mithilfe des folgenden Code in einen Delegaten konvertieren:</span><span class="sxs-lookup"><span data-stu-id="a0fc5-127">You would convert an expression into a delegate using the following code:</span></span>

```csharp
Expression<Func<int>> add = () => 1 + 2;
var func = add.Compile(); // Create Delegate
var answer = func(); // Invoke Delegate
Console.WriteLine(answer);
```

<span data-ttu-id="a0fc5-128">Beachten Sie, dass der Delegattyp auf den Ausdruckstyp basiert.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-128">Notice that the delegate type is based on the expression type.</span></span> <span data-ttu-id="a0fc5-129">Sie müssen den Rückgabetyp und die Argumentliste kennen, wenn Sie das Delegatobjekt mit strikter Typzuordnung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-129">You must know the return type and the argument list if you want to use the delegate object in a strongly typed manner.</span></span> <span data-ttu-id="a0fc5-130">Die `LambdaExpression.Compile()`-Methode gibt den `Delegate`-Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-130">The `LambdaExpression.Compile()` method returns the `Delegate` type.</span></span> <span data-ttu-id="a0fc5-131">Sie müssen es in den richtigen Delegattyp umwandeln, um Kompilierzeittools die Argumentliste oder den Rückgabetyp überprüfen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-131">You will have to cast it to the correct delegate type to have any compile-time tools check the argument list or return type.</span></span>

## <a name="execution-and-lifetimes"></a><span data-ttu-id="a0fc5-132">Ausführung und Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="a0fc5-132">Execution and Lifetimes</span></span>

<span data-ttu-id="a0fc5-133">Sie führen den Code durch Aufrufen des Delegaten aus, den Sie beim Aufrufen von `LambdaExpression.Compile()` erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-133">You execute the code by invoking the delegate created when you called `LambdaExpression.Compile()`.</span></span> <span data-ttu-id="a0fc5-134">Dies sehen Sie oben, wo `add.Compile()` einen Delegaten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-134">You can see this above where `add.Compile()` returns a delegate.</span></span> <span data-ttu-id="a0fc5-135">Rufen Sie diesen Delegaten durch Aufrufen von `func()` aus, der den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-135">Invoking that delegate, by calling `func()` executes the code.</span></span>

<span data-ttu-id="a0fc5-136">Dieser Delegat stellt den Code in der Ausdrucksbaumstruktur dar.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-136">That delegate represents the code in the expression tree.</span></span> <span data-ttu-id="a0fc5-137">Sie können das Handle für diesen Delegaten beibehalten und es später aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-137">You can retain the handle to that delegate and invoke it later.</span></span> <span data-ttu-id="a0fc5-138">Sie müssen die Ausdrucksbaumstruktur nicht jedes Mal kompilieren, wenn Sie den Code ausführen möchten, den sie darstellt.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-138">You don't need to compile the expression tree each time you want to execute the code it represents.</span></span> <span data-ttu-id="a0fc5-139">(Beachten Sie, dass Ausdrucksbaumstrukturen unveränderlich sind und dass das spätere Kompilieren der gleichen Ausdrucksbaumstruktur einen Delegaten erstellt, der den gleichen Code ausführt.)</span><span class="sxs-lookup"><span data-stu-id="a0fc5-139">(Remember that expression trees are immutable, and compiling the same expression tree later will create a delegate that executes the same code.)</span></span>

<span data-ttu-id="a0fc5-140">Ich rate Ihnen davon ab, zu versuchen, mehr anspruchsvollere Zwischenspeicherungsmechanismen zu erstellen, um die Leistungsfähigkeit durch Vermeiden unnötiger Kompilieraufrufe zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-140">I will caution you against trying to create any more sophisticated caching mechanisms to increase performance by avoiding unnecessary compile calls.</span></span> <span data-ttu-id="a0fc5-141">Das Vergleichen von zwei beliebigen Ausdrucksbaumstrukturen um festzustellen, ob sie den gleichen Algorithmus darstellen, wird auch zum Ausführen sehr zeitaufwändig sein.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-141">Comparing two arbitrary expression trees to determine if they represent the same algorithm will also be time consuming to execute.</span></span> <span data-ttu-id="a0fc5-142">Sie werden wahrscheinlich feststellen, dass die Rechenzeit, die Sie durch Vermeiden zusätzlicher Aufrufe von `LambdaExpression.Compile()` sichern, durch die Zeit für das Ausführen von Code, der zwei verschiedene Ausdrucksbaumstrukturen bestimmt, die zum gleichen ausführbaren Code führen, mehr als verbraucht sein wird.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-142">You'll likely find that the compute time you save avoiding any extra calls to `LambdaExpression.Compile()` will be more than consumed by the time executing code that determines of two different expression trees result in the same executable code.</span></span>

## <a name="caveats"></a><span data-ttu-id="a0fc5-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0fc5-143">Caveats</span></span>

<span data-ttu-id="a0fc5-144">Das Kompilieren eines Lambdaausdrucks in einen Delegaten und das Aufrufen dieses Delegaten, ist einer der einfachsten Vorgänge, die Sie mit einer Ausdrucksbaumstruktur ausführen können.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-144">Compiling a lambda expression to a delegate and invoking that delegate is one of the simplest operations you can perform with an expression tree.</span></span> <span data-ttu-id="a0fc5-145">Trotz dieses einfachen Vorgangs gibt es jedoch Hinweise, die Sie beachten müssen.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-145">However, even with this simple operation, there are caveats you must be aware of.</span></span> 

<span data-ttu-id="a0fc5-146">Lambdaausdrücke erstellen Closures über lokale Variablen, auf die im Ausdruck verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-146">Lambda Expressions create closures over any local variables that are referenced in the expression.</span></span> <span data-ttu-id="a0fc5-147">Sie müssen sicherstellen, dass alle Variablen, die Teil des Delegaten wären, am Speicherort verwendet werden können, wo Sie `Compile` aufrufen sowie beim Ausführen des resultierenden Delegats.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-147">You must guarantee that any variables that would be part of the delegate are usable at the location where you call `Compile`, and when you execute the resulting delegate.</span></span>

<span data-ttu-id="a0fc5-148">Im Allgemeinen stellt der Compiler sicher, dass dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-148">In general, the compiler will ensure that this is true.</span></span> <span data-ttu-id="a0fc5-149">Wenn jedoch der Ausdruck auf eine Variable zugreift, die `IDisposable` implementiert, ist es möglich, dass der Code das Objekt löschen kann, während es weiterhin in der Ausdrucksbaumstruktur aufrechterhalten wird.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-149">However, if your expression accesses a variable that implements `IDisposable`, it's possible that your code might dispose of the object while it is still held by the expression tree.</span></span>

<span data-ttu-id="a0fc5-150">Angenommen, dieser Code funktioniert gut, da `int` nicht `IDisposable` implementiert:</span><span class="sxs-lookup"><span data-stu-id="a0fc5-150">For example, this code works fine, because `int` does not implement `IDisposable`:</span></span>

```csharp
private static Func<int, int> CreateBoundFunc()
{
    var constant = 5; // constant is captured by the expression tree
    Expression<Func<int, int>> expression = (b) => constant + b;
    var rVal = expression.Compile();
    return rVal;
}
```

<span data-ttu-id="a0fc5-151">Der Delegat hat einen Verweis auf die lokale Variable `constant` erfasst.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-151">The delegate has captured a reference to the local variable `constant`.</span></span>
<span data-ttu-id="a0fc5-152">Auf diese Variable wird später zugegriffen, wenn die von `CreateBoundFunc` zurückgegebene Funktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-152">That variable is accessed at any time later, when the function returned by `CreateBoundFunc` executes.</span></span>

<span data-ttu-id="a0fc5-153">Jedoch sollten Sie diese (ausgedachte) Klasse beachten, die `IDisposable` implementiert:</span><span class="sxs-lookup"><span data-stu-id="a0fc5-153">However, consider this (rather contrived) class that implements `IDisposable`:</span></span>

```csharp
public class Resource : IDisposable
{
    private bool isDisposed = false;
    public int Argument
    {
        get
        {
            if (!isDisposed)
                return 5;
            else throw new ObjectDisposedException("Resource");
        }
    }

    public void Dispose()
    {
        isDisposed = true;
    }
}
```

<span data-ttu-id="a0fc5-154">Wenn Sie es in einem Ausdruck verwenden, wie unten dargestellt, erhalten Sie eine `ObjectDisposedException` beim Ausführen von Code, auf den die `Resource.Argument`-Eigenschaft verweist:</span><span class="sxs-lookup"><span data-stu-id="a0fc5-154">If you use it in an expression as shown below, you'll get an `ObjectDisposedException` when you execute the code referenced by the `Resource.Argument` property:</span></span>

```csharp
private static Func<int, int> CreateBoundResource()
{
    using (var constant = new Resource()) // constant is captured by the expression tree
    {
        Expression<Func<int, int>> expression = (b) => constant.Argument + b;
        var rVal = expression.Compile();
        return rVal;
    }
}
```

<span data-ttu-id="a0fc5-155">Der Delegat, der von dieser Methode zurückgegeben wurde, wurde über das `constant`-Objekt geschlossen, das verworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-155">The delegate returned from this method has closed over the `constant` object, which has been disposed of.</span></span> <span data-ttu-id="a0fc5-156">(Es wurde verworfen, da es in einer `using`-Anweisung deklariert wurde.)</span><span class="sxs-lookup"><span data-stu-id="a0fc5-156">(It's been disposed, because it was declared in a `using` statement.)</span></span> 

<span data-ttu-id="a0fc5-157">Nun, wenn Sie den von dieser Methode zurückgegebenen Delegaten ausführen, müssen Sie eine `ObjectDisposedException` haben, die zum Zeitpunkt der Ausführung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-157">Now, when you execute the delegate returned from this method, you'll have a `ObjectDisposedException` thrown at the point of execution.</span></span>

<span data-ttu-id="a0fc5-158">Es scheint sonderbar, einen Laufzeitfehler zu haben, der ein Kompilierzeitkonstrukt darstellt, aber das ist nun mal gang und gäbe, wenn wir mit Ausdrucksbaumstrukturen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-158">It does seem strange to have a runtime error representing a compile-time construct, but that's the world we enter when we work with expression trees.</span></span>

<span data-ttu-id="a0fc5-159">Es gibt viele Permutationen dieses Problem, daher ist es schwierig, eine allgemeine Anleitung zu bieten, um dies zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-159">There are a lot of permutations of this problem, so it's hard to offer general guidance to avoid it.</span></span> <span data-ttu-id="a0fc5-160">Seien Sie mit dem Zugriff auf lokale Variablen beim Definieren von Ausdrücken vorsichtig. Dies gilt auch beim Zugreifen auf Status im aktuellen Objekt (dargestellt durch `this`), wenn Sie eine Ausdrucksbaumstruktur erstellen, die durch eine öffentliche API zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-160">Be careful about accessing local variables when defining expressions, and be careful about accessing state in the current object (represented by `this`) when creating an expression tree that can be returned by a public API.</span></span>

<span data-ttu-id="a0fc5-161">Der Code in einem Ausdruck kann auf Methoden oder Eigenschaften in anderen Assemblys verweisen.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-161">The code in your expression may reference methods or properties in other assemblies.</span></span> <span data-ttu-id="a0fc5-162">Auf diese Assembly muss zugegriffen werden können, wenn der Ausdruck definiert ist, und wenn sie kompiliert wird und das resultierende Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-162">That assembly must be accessible when the expression is defined, and when it is compiled, and when the resulting delegate is invoked.</span></span> <span data-ttu-id="a0fc5-163">Sie werden einer `ReferencedAssemblyNotFoundException` in Fällen begegnen, in denen es nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-163">You'll be met with a `ReferencedAssemblyNotFoundException` in cases where it is not present.</span></span>

## <a name="summary"></a><span data-ttu-id="a0fc5-164">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="a0fc5-164">Summary</span></span>

<span data-ttu-id="a0fc5-165">Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, können kompiliert werden, um einen Delegaten zu erstellen, den Sie ausführen können.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-165">Expression Trees that represent lambda expressions can be compiled to create a delegate that you can execute.</span></span> <span data-ttu-id="a0fc5-166">Dies bietet einen Mechanismus, um den durch eine Ausdrucksbaumstruktur dargestellten Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-166">This provides one mechanism to execute the code represented by an expression tree.</span></span>

<span data-ttu-id="a0fc5-167">Die Ausdrucksbaumstruktur stellt den Code dar, der für jedes angegebene Konstrukt ausgeführt werden würde, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-167">The Expression Tree does represent the code that would execute for any given construct you create.</span></span> <span data-ttu-id="a0fc5-168">Solange die Umgebung, in der Sie den Code kompilieren und ausführen, der Umgebung entspricht, in der Sie den Ausdruck erstellen, funktioniert alles wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-168">As long as the environment where you compile and execute the code matches the environment where you create the expression, everything works as expected.</span></span> <span data-ttu-id="a0fc5-169">Wenn dies nicht der Fall ist, sind die Fehler sehr berechenbar, und sie werden in den ersten Tests von Code mithilfe der Ausdrucksbaumstrukturen abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="a0fc5-169">When that doesn't happen, the errors are very predictable, and they will be caught in your first tests of any code using the expression trees.</span></span>

[<span data-ttu-id="a0fc5-170">Weiter – Interpretieren von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="a0fc5-170">Next -- Interpreting Expressions</span></span>](expression-trees-interpreting.md)
