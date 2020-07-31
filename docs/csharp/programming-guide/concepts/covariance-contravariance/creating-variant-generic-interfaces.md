---
title: Erstellen varianter generischer Schnittstellen (C#)
description: Hier erfahren Sie, wie Sie generische Varianzschnittstellen mit generischen Ko- oder Kontravarianztypparametern erstellen.
ms.date: 07/20/2015
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
ms.openlocfilehash: 38b32784b681e748cd508c3d431fd4b18ec2c81a
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105720"
---
# <a name="creating-variant-generic-interfaces-c"></a><span data-ttu-id="ebfca-103">Erstellen varianter generischer Schnittstellen (C#)</span><span class="sxs-lookup"><span data-stu-id="ebfca-103">Creating Variant Generic Interfaces (C#)</span></span>

<span data-ttu-id="ebfca-104">Sie können generische Typparameter in Schnittstellen als Kovariante oder als Kontravariante deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ebfca-104">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="ebfca-105">*Kovarianz* ermöglicht Schnittstellenmethoden, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter definiert.</span><span class="sxs-lookup"><span data-stu-id="ebfca-105">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="ebfca-106">*Kontravarianz* ermöglicht Schnittstellenmethoden, Argumenttypen zu verwenden, die weniger stark abgeleitet sind, als durch die generischen Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="ebfca-106">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="ebfca-107">Eine generische Schnittstelle mit ko- oder kontravarianten generischen Typparametern wird als *variant* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ebfca-107">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>

> [!NOTE]
> <span data-ttu-id="ebfca-108">In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ebfca-108">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="ebfca-109">Die Liste der varianten Schnittstellen in .NET finden Sie unter [Varianz in generischen Schnittstellen (C#)](./variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="ebfca-109">For the list of the variant interfaces in .NET, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md).</span></span>

## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="ebfca-110">Deklarieren von varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ebfca-110">Declaring Variant Generic Interfaces</span></span>

<span data-ttu-id="ebfca-111">Sie können variante generische Schnittstellen deklarieren, indem Sie die `in`- und `out`-Schlüsselwörter für generische Typparameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebfca-111">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebfca-112">`ref`-, `in`- und `out`-Parameter in C# können nicht variant sein.</span><span class="sxs-lookup"><span data-stu-id="ebfca-112">`ref`, `in`, and `out` parameters in C# cannot be variant.</span></span> <span data-ttu-id="ebfca-113">Auch Werttypen unterstützen keine Varianz.</span><span class="sxs-lookup"><span data-stu-id="ebfca-113">Value types also do not support variance.</span></span>

<span data-ttu-id="ebfca-114">Sie können einen generischen Typparameter mithilfe des Schlüsselworts `out` als Kovariante deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ebfca-114">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="ebfca-115">Der kovariante Typ muss die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="ebfca-115">The covariant type must satisfy the following conditions:</span></span>

- <span data-ttu-id="ebfca-116">Der Typ wird nur als Rückgabetyp von Schnittstellenmethoden verwendet, und nicht als Typ von Methodenargumenten.</span><span class="sxs-lookup"><span data-stu-id="ebfca-116">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="ebfca-117">Dies wird im folgenden Beispiel veranschaulicht, in dem der Typ `R` als Kovariante deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="ebfca-117">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        R GetSomething();
        // The following statement generates a compiler error.
        // void SetSomething(R sampleArg);

    }
    ```

    <span data-ttu-id="ebfca-118">Es gibt allerdings eine Ausnahme zu dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="ebfca-118">There is one exception to this rule.</span></span> <span data-ttu-id="ebfca-119">Wenn Sie einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als generischen Typparameter für den Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebfca-119">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="ebfca-120">Dies wird im folgenden Beispiel von Typ `R` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ebfca-120">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="ebfca-121">Weitere Informationen finden Sie unter [Varianz in Delegaten (C#)](./variance-in-delegates.md) und [Verwenden von Varianz für die generischen Delegaten Func und Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="ebfca-121">For more information, see [Variance in Delegates (C#)](./variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        void DoSomething(Action<R> callback);
    }
    ```

- <span data-ttu-id="ebfca-122">Der Typ wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebfca-122">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="ebfca-123">Der folgende Code veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="ebfca-123">This is illustrated in the following code.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        // The following statement generates a compiler error
        // because you can use only contravariant or invariant types
        // in generic constraints.
        // void DoSomething<T>() where T : R;
    }
    ```

<span data-ttu-id="ebfca-124">Sie können einen generischen Typparameter mithilfe des Schlüsselworts `in` als Kovariante deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ebfca-124">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="ebfca-125">Der kontravariante Typ kann nur als Typ von Methodenargumenten und nicht von Schnittstellenmethoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebfca-125">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="ebfca-126">Der kontravariante Typ kann auch für generische Einschränkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebfca-126">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="ebfca-127">Der folgende Code zeigt, wie eine kontravariante Schnittstelle deklariert und eine generische Einschränkung für eine ihrer Methoden verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ebfca-127">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>

```csharp
interface IContravariant<in A>
{
    void SetSomething(A sampleArg);
    void DoSomething<T>() where T : A;
    // The following statement generates a compiler error.
    // A GetSomething();
}
```

<span data-ttu-id="ebfca-128">Bei unterschiedlichen Typparametern ist jedoch auch die Verwendung verschiedener Ko- und Kontravarianzen in der gleichen Schnittstelle möglich, wie im folgenden Codebeispiel veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="ebfca-128">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>

```csharp
interface IVariant<out R, in A>
{
    R GetSomething();
    void SetSomething(A sampleArg);
    R GetSetSomethings(A sampleArg);
}
```

## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="ebfca-129">Implementieren von varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ebfca-129">Implementing Variant Generic Interfaces</span></span>

<span data-ttu-id="ebfca-130">Sie können variante generische Schnittstellen in Klassen implementieren, indem Sie die gleiche Syntax verwenden, die für invariante Schnittstellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ebfca-130">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="ebfca-131">Im folgenden Codebeispiel wird veranschaulicht, wie eine kovariante Schnittstelle in einer generischen Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ebfca-131">The following code example shows how to implement a covariant interface in a generic class.</span></span>

```csharp
interface ICovariant<out R>
{
    R GetSomething();
}
class SampleImplementation<R> : ICovariant<R>
{
    public R GetSomething()
    {
        // Some code.
        return default(R);
    }
}
```

<span data-ttu-id="ebfca-132">Klassen, die variante Schnittstellen implementieren, sind nicht variant.</span><span class="sxs-lookup"><span data-stu-id="ebfca-132">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="ebfca-133">Betrachten Sie hierzu den folgenden Beispielcode:</span><span class="sxs-lookup"><span data-stu-id="ebfca-133">For example, consider the following code.</span></span>

```csharp
// The interface is covariant.
ICovariant<Button> ibutton = new SampleImplementation<Button>();
ICovariant<Object> iobj = ibutton;

// The class is invariant.
SampleImplementation<Button> button = new SampleImplementation<Button>();
// The following statement generates a compiler error
// because classes are invariant.
// SampleImplementation<Object> obj = button;
```

## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="ebfca-134">Erweitern von varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ebfca-134">Extending Variant Generic Interfaces</span></span>

<span data-ttu-id="ebfca-135">Wenn Sie eine variante generische Schnittstelle erweitern, müssen Sie mit den `in`- und `out`-Schlüsselwörtern explizit angeben, ob Varianz von der abgeleiteten Schnittstelle unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ebfca-135">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="ebfca-136">Der Compiler leitet eine Varianz nicht von der Schnittstelle ab, die erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="ebfca-136">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="ebfca-137">Beachten Sie z.B. die folgenden Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="ebfca-137">For example, consider the following interfaces.</span></span>

```csharp
interface ICovariant<out T> { }
interface IInvariant<T> : ICovariant<T> { }
interface IExtCovariant<out T> : ICovariant<T> { }
```

<span data-ttu-id="ebfca-138">In der `IInvariant<T>`-Schnittstelle ist der generische Typparameter `T` nicht variant, während in `IExtCovariant<out T>` der Typparameter kovariant ist, obwohl beide Schnittstellen die gleiche Schnittstelle erweitern.</span><span class="sxs-lookup"><span data-stu-id="ebfca-138">In the `IInvariant<T>` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant<out T>` the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="ebfca-139">Die gleiche Regel gilt für kontravariante generische Typparameter.</span><span class="sxs-lookup"><span data-stu-id="ebfca-139">The same rule is applied to contravariant generic type parameters.</span></span>

<span data-ttu-id="ebfca-140">Sie können eine Schnittstelle erstellen, die sowohl die Schnittstelle mit dem kovarianten generischen Typparameter `T` als auch die Schnittstelle mit dem kontravarianten Typparameter implementiert, wenn der generische Typparameter `T` in der erweiternden Schnittstelle nicht variant ist.</span><span class="sxs-lookup"><span data-stu-id="ebfca-140">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="ebfca-141">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ebfca-141">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
interface IContravariant<in T> { }
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }
```

<span data-ttu-id="ebfca-142">Wenn der generische Typparameter `T` jedoch in einer Schnittstelle als Kovariante deklariert wird, können Sie ihn nicht in der erweiternden Schnittstelle als Kontravariante deklarieren oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="ebfca-142">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="ebfca-143">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ebfca-143">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
// The following statement generates a compiler error.
// interface ICoContraVariant<in T> : ICovariant<T> { }
```

### <a name="avoiding-ambiguity"></a><span data-ttu-id="ebfca-144">Vermeiden von Mehrdeutigkeiten</span><span class="sxs-lookup"><span data-stu-id="ebfca-144">Avoiding Ambiguity</span></span>

<span data-ttu-id="ebfca-145">Wenn Sie variante generische Schnittstellen implementieren, kann Varianz manchmal zu Mehrdeutigkeit führen.</span><span class="sxs-lookup"><span data-stu-id="ebfca-145">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="ebfca-146">Diese Mehrdeutigkeit sollte vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="ebfca-146">Such ambiguity should be avoided.</span></span>

<span data-ttu-id="ebfca-147">Wenn Sie z.B. die gleiche variante generische Schnittstelle explizit mit unterschiedlichen generischen Typparametern in einer Klasse implementieren, kann dies zu Mehrdeutigkeit führen.</span><span class="sxs-lookup"><span data-stu-id="ebfca-147">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="ebfca-148">Der Compiler erzeugt in diesem Fall keinen Fehler. Es wird jedoch nicht angegeben, welche Schnittstellenimplementierung zur Laufzeit ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ebfca-148">The compiler does not produce an error in this case, but it's not specified which interface implementation will be chosen at run time.</span></span> <span data-ttu-id="ebfca-149">Diese Mehrdeutigkeit kann zu schwer erkennbaren Fehlern im Code führen.</span><span class="sxs-lookup"><span data-stu-id="ebfca-149">This ambiguity could lead to subtle bugs in your code.</span></span> <span data-ttu-id="ebfca-150">Betrachten Sie folgendes Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="ebfca-150">Consider the following code example.</span></span>

```csharp
// Simple class hierarchy.
class Animal { }
class Cat : Animal { }
class Dog : Animal { }

// This class introduces ambiguity
// because IEnumerable<out T> is covariant.
class Pets : IEnumerable<Cat>, IEnumerable<Dog>
{
    IEnumerator<Cat> IEnumerable<Cat>.GetEnumerator()
    {
        Console.WriteLine("Cat");
        // Some code.
        return null;
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        // Some code.
        return null;
    }

    IEnumerator<Dog> IEnumerable<Dog>.GetEnumerator()
    {
        Console.WriteLine("Dog");
        // Some code.
        return null;
    }
}
class Program
{
    public static void Test()
    {
        IEnumerable<Animal> pets = new Pets();
        pets.GetEnumerator();
    }
}
```

<span data-ttu-id="ebfca-151">In diesem Beispiel ist nicht angegeben, wie die `pets.GetEnumerator`-Methode zwischen `Cat` und `Dog` auswählt.</span><span class="sxs-lookup"><span data-stu-id="ebfca-151">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="ebfca-152">Dies könnte Probleme im Code verursachen.</span><span class="sxs-lookup"><span data-stu-id="ebfca-152">This could cause problems in your code.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebfca-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebfca-153">See also</span></span>

- [<span data-ttu-id="ebfca-154">Varianz in generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ebfca-154">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)
- [<span data-ttu-id="ebfca-155">Verwenden von Varianz für die generischen Delegaten Func und Action (C#)</span><span class="sxs-lookup"><span data-stu-id="ebfca-155">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
