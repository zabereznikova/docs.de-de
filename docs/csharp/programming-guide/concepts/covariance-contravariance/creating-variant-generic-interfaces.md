---
title: Erstellen varianter generischer Schnittstellen (C#)
ms.date: 07/20/2015
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
ms.openlocfilehash: a8e3e010c0e5d5490aee35603cad4fd6c1dc29e0
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990044"
---
# <a name="creating-variant-generic-interfaces-c"></a><span data-ttu-id="5fadf-102">Erstellen varianter generischer Schnittstellen (C#)</span><span class="sxs-lookup"><span data-stu-id="5fadf-102">Creating Variant Generic Interfaces (C#)</span></span>

<span data-ttu-id="5fadf-103">Sie können generische Typparameter in Schnittstellen als Kovariante oder als Kontravariante deklarieren.</span><span class="sxs-lookup"><span data-stu-id="5fadf-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="5fadf-104">*Kovarianz* ermöglicht Schnittstellenmethoden, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter definiert.</span><span class="sxs-lookup"><span data-stu-id="5fadf-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="5fadf-105">*Kontravarianz* ermöglicht Schnittstellenmethoden, Argumenttypen zu verwenden, die weniger stark abgeleitet sind, als durch die generischen Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="5fadf-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="5fadf-106">Eine generische Schnittstelle mit ko- oder kontravarianten generischen Typparametern wird als *variant* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5fadf-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>

> [!NOTE]
> <span data-ttu-id="5fadf-107">In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5fadf-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="5fadf-108">Die Liste der varianten Schnittstellen in .NET finden Sie unter [Varianz in generischen Schnittstellen (C#)](./variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="5fadf-108">For the list of the variant interfaces in .NET, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md).</span></span>

## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="5fadf-109">Deklarieren von varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5fadf-109">Declaring Variant Generic Interfaces</span></span>

<span data-ttu-id="5fadf-110">Sie können variante generische Schnittstellen deklarieren, indem Sie die `in`- und `out`-Schlüsselwörter für generische Typparameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="5fadf-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fadf-111">`ref`-, `in`- und `out`-Parameter in C# können nicht variant sein.</span><span class="sxs-lookup"><span data-stu-id="5fadf-111">`ref`, `in`, and `out` parameters in C# cannot be variant.</span></span> <span data-ttu-id="5fadf-112">Auch Werttypen unterstützen keine Varianz.</span><span class="sxs-lookup"><span data-stu-id="5fadf-112">Value types also do not support variance.</span></span>

<span data-ttu-id="5fadf-113">Sie können einen generischen Typparameter mithilfe des Schlüsselworts `out` als Kovariante deklarieren.</span><span class="sxs-lookup"><span data-stu-id="5fadf-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="5fadf-114">Der kovariante Typ muss die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="5fadf-114">The covariant type must satisfy the following conditions:</span></span>

- <span data-ttu-id="5fadf-115">Der Typ wird nur als Rückgabetyp von Schnittstellenmethoden verwendet, und nicht als Typ von Methodenargumenten.</span><span class="sxs-lookup"><span data-stu-id="5fadf-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="5fadf-116">Dies wird im folgenden Beispiel veranschaulicht, in dem der Typ `R` als Kovariante deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="5fadf-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        R GetSomething();
        // The following statement generates a compiler error.
        // void SetSomething(R sampleArg);

    }
    ```

    <span data-ttu-id="5fadf-117">Es gibt allerdings eine Ausnahme zu dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="5fadf-117">There is one exception to this rule.</span></span> <span data-ttu-id="5fadf-118">Wenn Sie einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als generischen Typparameter für den Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="5fadf-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="5fadf-119">Dies wird im folgenden Beispiel von Typ `R` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5fadf-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="5fadf-120">Weitere Informationen finden Sie unter [Varianz in Delegaten (C#)](./variance-in-delegates.md) und [Verwenden von Varianz für die generischen Delegaten Func und Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="5fadf-120">For more information, see [Variance in Delegates (C#)](./variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        void DoSomething(Action<R> callback);
    }
    ```

- <span data-ttu-id="5fadf-121">Der Typ wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fadf-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="5fadf-122">Der folgende Code veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="5fadf-122">This is illustrated in the following code.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        // The following statement generates a compiler error
        // because you can use only contravariant or invariant types
        // in generic constraints.
        // void DoSomething<T>() where T : R;
    }
    ```

<span data-ttu-id="5fadf-123">Sie können einen generischen Typparameter mithilfe des Schlüsselworts `in` als Kovariante deklarieren.</span><span class="sxs-lookup"><span data-stu-id="5fadf-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="5fadf-124">Der kontravariante Typ kann nur als Typ von Methodenargumenten und nicht von Schnittstellenmethoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5fadf-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="5fadf-125">Der kontravariante Typ kann auch für generische Einschränkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5fadf-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="5fadf-126">Der folgende Code zeigt, wie eine kontravariante Schnittstelle deklariert und eine generische Einschränkung für eine ihrer Methoden verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5fadf-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>

```csharp
interface IContravariant<in A>
{
    void SetSomething(A sampleArg);
    void DoSomething<T>() where T : A;
    // The following statement generates a compiler error.
    // A GetSomething();
}
```

<span data-ttu-id="5fadf-127">Bei unterschiedlichen Typparametern ist jedoch auch die Verwendung verschiedener Ko- und Kontravarianzen in der gleichen Schnittstelle möglich, wie im folgenden Codebeispiel veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="5fadf-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>

```csharp
interface IVariant<out R, in A>
{
    R GetSomething();
    void SetSomething(A sampleArg);
    R GetSetSomethings(A sampleArg);
}
```

## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="5fadf-128">Implementieren von varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5fadf-128">Implementing Variant Generic Interfaces</span></span>

<span data-ttu-id="5fadf-129">Sie können variante generische Schnittstellen in Klassen implementieren, indem Sie die gleiche Syntax verwenden, die für invariante Schnittstellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5fadf-129">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="5fadf-130">Im folgenden Codebeispiel wird veranschaulicht, wie eine kovariante Schnittstelle in einer generischen Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="5fadf-130">The following code example shows how to implement a covariant interface in a generic class.</span></span>

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

<span data-ttu-id="5fadf-131">Klassen, die variante Schnittstellen implementieren, sind nicht variant.</span><span class="sxs-lookup"><span data-stu-id="5fadf-131">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="5fadf-132">Betrachten Sie hierzu den folgenden Beispielcode:</span><span class="sxs-lookup"><span data-stu-id="5fadf-132">For example, consider the following code.</span></span>

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

## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="5fadf-133">Erweitern von varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5fadf-133">Extending Variant Generic Interfaces</span></span>

<span data-ttu-id="5fadf-134">Wenn Sie eine variante generische Schnittstelle erweitern, müssen Sie mit den `in`- und `out`-Schlüsselwörtern explizit angeben, ob Varianz von der abgeleiteten Schnittstelle unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5fadf-134">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="5fadf-135">Der Compiler leitet eine Varianz nicht von der Schnittstelle ab, die erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="5fadf-135">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="5fadf-136">Beachten Sie z.B. die folgenden Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="5fadf-136">For example, consider the following interfaces.</span></span>

```csharp
interface ICovariant<out T> { }
interface IInvariant<T> : ICovariant<T> { }
interface IExtCovariant<out T> : ICovariant<T> { }
```

<span data-ttu-id="5fadf-137">In der `IInvariant<T>`-Schnittstelle ist der generische Typparameter `T` nicht variant, während in `IExtCovariant<out T>` der Typparameter kovariant ist, obwohl beide Schnittstellen die gleiche Schnittstelle erweitern.</span><span class="sxs-lookup"><span data-stu-id="5fadf-137">In the `IInvariant<T>` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant<out T>` the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="5fadf-138">Die gleiche Regel gilt für kontravariante generische Typparameter.</span><span class="sxs-lookup"><span data-stu-id="5fadf-138">The same rule is applied to contravariant generic type parameters.</span></span>

<span data-ttu-id="5fadf-139">Sie können eine Schnittstelle erstellen, die sowohl die Schnittstelle mit dem kovarianten generischen Typparameter `T` als auch die Schnittstelle mit dem kontravarianten Typparameter implementiert, wenn der generische Typparameter `T` in der erweiternden Schnittstelle nicht variant ist.</span><span class="sxs-lookup"><span data-stu-id="5fadf-139">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="5fadf-140">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5fadf-140">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
interface IContravariant<in T> { }
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }
```

<span data-ttu-id="5fadf-141">Wenn der generische Typparameter `T` jedoch in einer Schnittstelle als Kovariante deklariert wird, können Sie ihn nicht in der erweiternden Schnittstelle als Kontravariante deklarieren oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="5fadf-141">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="5fadf-142">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5fadf-142">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
// The following statement generates a compiler error.
// interface ICoContraVariant<in T> : ICovariant<T> { }
```

### <a name="avoiding-ambiguity"></a><span data-ttu-id="5fadf-143">Vermeiden von Mehrdeutigkeiten</span><span class="sxs-lookup"><span data-stu-id="5fadf-143">Avoiding Ambiguity</span></span>

<span data-ttu-id="5fadf-144">Wenn Sie variante generische Schnittstellen implementieren, kann Varianz manchmal zu Mehrdeutigkeit führen.</span><span class="sxs-lookup"><span data-stu-id="5fadf-144">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="5fadf-145">Diese Mehrdeutigkeit sollte vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="5fadf-145">Such ambiguity should be avoided.</span></span>

<span data-ttu-id="5fadf-146">Wenn Sie z.B. die gleiche variante generische Schnittstelle explizit mit unterschiedlichen generischen Typparametern in einer Klasse implementieren, kann dies zu Mehrdeutigkeit führen.</span><span class="sxs-lookup"><span data-stu-id="5fadf-146">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="5fadf-147">Der Compiler erzeugt in diesem Fall keinen Fehler. Es wird jedoch nicht angegeben, welche Schnittstellenimplementierung zur Laufzeit ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="5fadf-147">The compiler does not produce an error in this case, but it's not specified which interface implementation will be chosen at run time.</span></span> <span data-ttu-id="5fadf-148">Diese Mehrdeutigkeit kann zu schwer erkennbaren Fehlern im Code führen.</span><span class="sxs-lookup"><span data-stu-id="5fadf-148">This ambiguity could lead to subtle bugs in your code.</span></span> <span data-ttu-id="5fadf-149">Betrachten Sie folgendes Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="5fadf-149">Consider the following code example.</span></span>

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

<span data-ttu-id="5fadf-150">In diesem Beispiel ist nicht angegeben, wie die `pets.GetEnumerator`-Methode zwischen `Cat` und `Dog` auswählt.</span><span class="sxs-lookup"><span data-stu-id="5fadf-150">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="5fadf-151">Dies könnte Probleme im Code verursachen.</span><span class="sxs-lookup"><span data-stu-id="5fadf-151">This could cause problems in your code.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fadf-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fadf-152">See also</span></span>

- [<span data-ttu-id="5fadf-153">Varianz in generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5fadf-153">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)
- [<span data-ttu-id="5fadf-154">Verwenden von Varianz für die generischen Delegaten Func und Action (C#)</span><span class="sxs-lookup"><span data-stu-id="5fadf-154">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
