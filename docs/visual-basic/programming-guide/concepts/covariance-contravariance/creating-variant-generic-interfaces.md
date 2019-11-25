---
title: Erstellen von varianten generischen Schnittstellen
ms.date: 07/20/2015
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
ms.openlocfilehash: 74362b9d9effab028bebb9e9ecf72ac0111366d3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347073"
---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="bd2c9-102">Creating Variant Generic Interfaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-102">Creating Variant Generic Interfaces (Visual Basic)</span></span>

<span data-ttu-id="bd2c9-103">Sie können generische Typparameter in Schnittstellen als Kovariante oder als Kontravariante deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="bd2c9-104">*Kovarianz* ermöglicht Schnittstellenmethoden, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter definiert.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="bd2c9-105">*Kontravarianz* ermöglicht Schnittstellenmethoden, Argumenttypen zu verwenden, die weniger stark abgeleitet sind, als durch die generischen Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="bd2c9-106">Eine generische Schnittstelle mit ko- oder kontravarianten generischen Typparametern wird als *variant* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>

> [!NOTE]
> <span data-ttu-id="bd2c9-107">In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="bd2c9-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="bd2c9-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>

## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="bd2c9-109">Deklarieren von varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bd2c9-109">Declaring Variant Generic Interfaces</span></span>

<span data-ttu-id="bd2c9-110">Sie können variante generische Schnittstellen deklarieren, indem Sie die `in`- und `out`-Schlüsselwörter für generische Typparameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd2c9-111">`ByRef` parameters in Visual Basic cannot be variant.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-111">`ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="bd2c9-112">Auch Werttypen unterstützen keine Varianz.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-112">Value types also do not support variance.</span></span>

<span data-ttu-id="bd2c9-113">Sie können einen generischen Typparameter mithilfe des Schlüsselworts `out` als Kovariante deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="bd2c9-114">Der kovariante Typ muss die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="bd2c9-114">The covariant type must satisfy the following conditions:</span></span>

- <span data-ttu-id="bd2c9-115">Der Typ wird nur als Rückgabetyp von Schnittstellenmethoden verwendet, und nicht als Typ von Methodenargumenten.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="bd2c9-116">Dies wird im folgenden Beispiel veranschaulicht, in dem der Typ `R` als Kovariante deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>

    ```vb
    Interface ICovariant(Of Out R)
        Function GetSomething() As R
        ' The following statement generates a compiler error.
        ' Sub SetSomething(ByVal sampleArg As R)
    End Interface
    ```

    <span data-ttu-id="bd2c9-117">Es gibt allerdings eine Ausnahme zu dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-117">There is one exception to this rule.</span></span> <span data-ttu-id="bd2c9-118">Wenn Sie einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als generischen Typparameter für den Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="bd2c9-119">Dies wird im folgenden Beispiel von Typ `R` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="bd2c9-120">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="bd2c9-120">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

    ```vb
    Interface ICovariant(Of Out R)
        Sub DoSomething(ByVal callback As Action(Of R))
    End Interface
    ```

- <span data-ttu-id="bd2c9-121">Der Typ wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="bd2c9-122">Der folgende Code veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-122">This is illustrated in the following code.</span></span>

    ```vb
    Interface ICovariant(Of Out R)
        ' The following statement generates a compiler error
        ' because you can use only contravariant or invariant types
        ' in generic constraints.
        ' Sub DoSomething(Of T As R)()
    End Interface
    ```

<span data-ttu-id="bd2c9-123">Sie können einen generischen Typparameter mithilfe des Schlüsselworts `in` als Kovariante deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="bd2c9-124">Der kontravariante Typ kann nur als Typ von Methodenargumenten und nicht von Schnittstellenmethoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="bd2c9-125">Der kontravariante Typ kann auch für generische Einschränkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="bd2c9-126">Der folgende Code zeigt, wie eine kontravariante Schnittstelle deklariert und eine generische Einschränkung für eine ihrer Methoden verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>

```vb
Interface IContravariant(Of In A)
    Sub SetSomething(ByVal sampleArg As A)
    Sub DoSomething(Of T As A)()
    ' The following statement generates a compiler error.
    ' Function GetSomething() As A
End Interface
```

<span data-ttu-id="bd2c9-127">Bei unterschiedlichen Typparametern ist jedoch auch die Verwendung verschiedener Ko- und Kontravarianzen in der gleichen Schnittstelle möglich, wie im folgenden Codebeispiel veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>

```vb
Interface IVariant(Of Out R, In A)
    Function GetSomething() As R
    Sub SetSomething(ByVal sampleArg As A)
    Function GetSetSomething(ByVal sampleArg As A) As R
End Interface
```

<span data-ttu-id="bd2c9-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="bd2c9-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="bd2c9-130">Der folgende Code veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-130">This is illustrated in the following code.</span></span>

```vb
Interface ICovariant(Of Out R)
    ' The following statement generates a compiler error.
    ' Event SampleEvent()
    ' The following statement specifies the delegate type and
    ' does not generate an error.
    Event AnotherEvent As EventHandler

    ' The following statements generate compiler errors,
    ' because a variant interface cannot have
    ' nested enums, classes, or structures.

    'Enum SampleEnum : test : End Enum
    'Class SampleClass : End Class
    'Structure SampleStructure : Dim value As Integer : End Structure

    ' Variant interfaces can have nested interfaces.
    Interface INested : End Interface
End Interface
```

## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="bd2c9-131">Implementieren von varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bd2c9-131">Implementing Variant Generic Interfaces</span></span>

<span data-ttu-id="bd2c9-132">Sie können variante generische Schnittstellen in Klassen implementieren, indem Sie die gleiche Syntax verwenden, die für invariante Schnittstellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-132">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="bd2c9-133">Im folgenden Codebeispiel wird veranschaulicht, wie eine kovariante Schnittstelle in einer generischen Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-133">The following code example shows how to implement a covariant interface in a generic class.</span></span>

```vb
Interface ICovariant(Of Out R)
    Function GetSomething() As R
End Interface

Class SampleImplementation(Of R)
    Implements ICovariant(Of R)
    Public Function GetSomething() As R _
    Implements ICovariant(Of R).GetSomething
        ' Some code.
    End Function
End Class
```

<span data-ttu-id="bd2c9-134">Klassen, die variante Schnittstellen implementieren, sind nicht variant.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-134">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="bd2c9-135">Betrachten Sie hierzu den folgenden Beispielcode:</span><span class="sxs-lookup"><span data-stu-id="bd2c9-135">For example, consider the following code.</span></span>

```vb
 The interface is covariant.
Dim ibutton As ICovariant(Of Button) =
    New SampleImplementation(Of Button)
Dim iobj As ICovariant(Of Object) = ibutton

' The class is invariant.
Dim button As SampleImplementation(Of Button) =
    New SampleImplementation(Of Button)
' The following statement generates a compiler error
' because classes are invariant.
' Dim obj As SampleImplementation(Of Object) = button
```

## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="bd2c9-136">Erweitern von varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bd2c9-136">Extending Variant Generic Interfaces</span></span>

<span data-ttu-id="bd2c9-137">Wenn Sie eine variante generische Schnittstelle erweitern, müssen Sie mit den `in`- und `out`-Schlüsselwörtern explizit angeben, ob Varianz von der abgeleiteten Schnittstelle unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-137">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="bd2c9-138">Der Compiler leitet eine Varianz nicht von der Schnittstelle ab, die erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-138">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="bd2c9-139">Beachten Sie z.B. die folgenden Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-139">For example, consider the following interfaces.</span></span>

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T)
End Interface

Interface IExtCovariant(Of Out T)
    Inherits ICovariant(Of T)
End Interface
```

<span data-ttu-id="bd2c9-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="bd2c9-141">Die gleiche Regel gilt für kontravariante generische Typparameter.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-141">The same rule is applied to contravariant generic type parameters.</span></span>

<span data-ttu-id="bd2c9-142">Sie können eine Schnittstelle erstellen, die sowohl die Schnittstelle mit dem kovarianten generischen Typparameter `T` als auch die Schnittstelle mit dem kontravarianten Typparameter implementiert, wenn der generische Typparameter `T` in der erweiternden Schnittstelle nicht variant ist.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-142">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="bd2c9-143">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-143">This is illustrated in the following code example.</span></span>

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IContravariant(Of In T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T), IContravariant(Of T)
End Interface
```

<span data-ttu-id="bd2c9-144">Wenn der generische Typparameter `T` jedoch in einer Schnittstelle als Kovariante deklariert wird, können Sie ihn nicht in der erweiternden Schnittstelle als Kontravariante deklarieren oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-144">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="bd2c9-145">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-145">This is illustrated in the following code example.</span></span>

```vb
Interface ICovariant(Of Out T)
End Interface

' The following statements generate a compiler error.
' Interface ICoContraVariant(Of In T)
'     Inherits ICovariant(Of T)
' End Interface
```

### <a name="avoiding-ambiguity"></a><span data-ttu-id="bd2c9-146">Vermeiden von Mehrdeutigkeiten</span><span class="sxs-lookup"><span data-stu-id="bd2c9-146">Avoiding Ambiguity</span></span>

<span data-ttu-id="bd2c9-147">Wenn Sie variante generische Schnittstellen implementieren, kann Varianz manchmal zu Mehrdeutigkeit führen.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-147">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="bd2c9-148">Dies sollte vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-148">This should be avoided.</span></span>

<span data-ttu-id="bd2c9-149">Wenn Sie z.B. die gleiche variante generische Schnittstelle explizit mit unterschiedlichen generischen Typparametern in einer Klasse implementieren, kann dies zu Mehrdeutigkeit führen.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-149">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="bd2c9-150">Der Compiler erzeugt in diesem Fall keinen Fehler, aber es wird nicht angegeben, welche Schnittstellenimplementierung zur Laufzeit ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-150">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="bd2c9-151">Dies kann zu schwer erkennbaren Fehlern im Code führen.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-151">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="bd2c9-152">Betrachten Sie folgendes Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-152">Consider the following code example.</span></span>

> [!NOTE]
> <span data-ttu-id="bd2c9-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="bd2c9-154">With `Option Strict On`, Visual Basic generates a compiler error.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-154">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>

```vb
' Simple class hierarchy.
Class Animal
End Class

Class Cat
    Inherits Animal
End Class

Class Dog
    Inherits Animal
End Class

' This class introduces ambiguity
' because IEnumerable(Of Out T) is covariant.
Class Pets
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)

    Public Function GetEnumerator() As IEnumerator(Of Cat) _
        Implements IEnumerable(Of Cat).GetEnumerator
        Console.WriteLine("Cat")
        ' Some code.
    End Function

    Public Function GetEnumerator1() As IEnumerator(Of Dog) _
        Implements IEnumerable(Of Dog).GetEnumerator
        Console.WriteLine("Dog")
        ' Some code.
    End Function

    Public Function GetEnumerator2() As IEnumerator _
        Implements IEnumerable.GetEnumerator
        ' Some code.
    End Function
End Class

Sub Main()
    Dim pets As IEnumerable(Of Animal) = New Pets()
    pets.GetEnumerator()
End Sub
```

<span data-ttu-id="bd2c9-155">In diesem Beispiel ist nicht angegeben, wie die `pets.GetEnumerator`-Methode zwischen `Cat` und `Dog` auswählt.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-155">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="bd2c9-156">Dies könnte Probleme im Code verursachen.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-156">This could cause problems in your code.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd2c9-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd2c9-157">See also</span></span>

- [<span data-ttu-id="bd2c9-158">Variance in Generic Interfaces (Visual Basic) (Varianz in generischen Schnittstellen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="bd2c9-158">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="bd2c9-159">Using Variance for Func and Action Generic Delegates (Visual Basic) (Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="bd2c9-159">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
