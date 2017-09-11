---
title: Erstellen von Varianten generischen Schnittstellen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a2cbf0a204a5a3af45f55a14c011518c7021f5b4
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="54007-102">Erstellen von Varianten generischen Schnittstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54007-102">Creating Variant Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="54007-103">Sie können deklarieren, generischen Typparametern in Schnittstellen als kovariant oder kontravariant.</span><span class="sxs-lookup"><span data-stu-id="54007-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="54007-104">*Kovarianz* ermöglicht Schnittstellenmethoden, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter definiert.</span><span class="sxs-lookup"><span data-stu-id="54007-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="54007-105">*Kontravarianz* ermöglicht Schnittstellenmethoden Argumenttypen zu verwenden, die weniger stark abgeleitet sind, als durch die generischen Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="54007-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="54007-106">Eine generische Schnittstelle mit ko- oder kontravarianten generischen Typparametern heißt *Variante*.</span><span class="sxs-lookup"><span data-stu-id="54007-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54007-107">Varianz-Unterstützung für mehrere vorhandene generische Schnittstellen wurde in .NET Framework 4 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="54007-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="54007-108">Die Liste der Varianten Schnittstellen in .NET Framework finden Sie unter [Varianz in generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="54007-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="54007-109">Deklarieren von Varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="54007-109">Declaring Variant Generic Interfaces</span></span>  
 <span data-ttu-id="54007-110">Sie können Variante generische Schnittstellen deklarieren, indem die `in` und `out` Schlüsselwörter für generische Typparameter.</span><span class="sxs-lookup"><span data-stu-id="54007-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="54007-111"> `ByRef`-Parameter in Visual Basic nicht Variant-Wert.</span><span class="sxs-lookup"><span data-stu-id="54007-111"> `ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="54007-112">Varianz unterstützt Werttypen auch nicht.</span><span class="sxs-lookup"><span data-stu-id="54007-112">Value types also do not support variance.</span></span>  
  
 <span data-ttu-id="54007-113">Sie können einen generischen Typparameter kovariant deklarieren, indem die `out` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="54007-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="54007-114">Der kovariante Typ muss Folgendes erfüllen:</span><span class="sxs-lookup"><span data-stu-id="54007-114">The covariant type must satisfy the following conditions:</span></span>  
  
-   <span data-ttu-id="54007-115">Der Typ wird nur als Rückgabetyp von Schnittstellenmethoden verwendet und nicht als Typ von Methodenargumenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="54007-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="54007-116">Dies wird im folgenden Beispiel, in dem veranschaulicht den Typ `R` als kovariant deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="54007-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     <span data-ttu-id="54007-117">Es gibt allerdings eine Ausnahme zu dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="54007-117">There is one exception to this rule.</span></span> <span data-ttu-id="54007-118">Wenn Sie einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als einen generischen Typparameter für den Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="54007-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="54007-119">Dies wird durch den Typ veranschaulicht `R` im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="54007-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="54007-120">Weitere Informationen finden Sie unter [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) und [mithilfe von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="54007-120">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   <span data-ttu-id="54007-121">Der Typ wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="54007-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="54007-122">Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="54007-122">This is illustrated in the following code.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 <span data-ttu-id="54007-123">Sie können einen generischen Typparameter als Kontravariante deklarieren, indem die `in` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="54007-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="54007-124">Der kontravariante Typ kann nur als Typ von Methodenargumenten und nicht als Rückgabetyp von Schnittstellenmethoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="54007-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="54007-125">Der kontravariante Typ kann auch für generische Einschränkungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="54007-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="54007-126">Der folgende Code zeigt, wie eine kontravariante Schnittstelle deklariert und eine generische Einschränkung für eine seiner Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="54007-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 <span data-ttu-id="54007-127">Es ist auch möglich, Kovarianz und Kontravarianz in derselben Schnittstelle, aber für unterschiedliche Typparameter unterstützen, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="54007-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 <span data-ttu-id="54007-128">In Visual Basic können Sie Ereignisse in Varianten Schnittstellen deklarieren, ohne den Delegattyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="54007-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="54007-129">Außerdem eine Variante Schnittstelle kann jedoch keine geschachtelten Klassen, Enumerationen und Strukturen, Schnittstellen geschachtelt haben.</span><span class="sxs-lookup"><span data-stu-id="54007-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="54007-130">Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="54007-130">This is illustrated in the following code.</span></span>  
  
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
  
## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="54007-131">Implementieren von Varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="54007-131">Implementing Variant Generic Interfaces</span></span>  
 <span data-ttu-id="54007-132">Variante generische Schnittstellen in Klassen zu implementieren, mit der gleichen Syntax, die für invariante Schnittstellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="54007-132">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="54007-133">Im folgenden Codebeispiel wird veranschaulicht, wie eine kovariante Schnittstelle in einer generischen Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="54007-133">The following code example shows how to implement a covariant interface in a generic class.</span></span>  
  
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
  
 <span data-ttu-id="54007-134">Klassen, die Variante Schnittstellen zu implementieren sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="54007-134">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="54007-135">Betrachten Sie hierzu den folgenden Beispielcode:</span><span class="sxs-lookup"><span data-stu-id="54007-135">For example, consider the following code.</span></span>  
  
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
  
## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="54007-136">Erweitern von Varianten generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="54007-136">Extending Variant Generic Interfaces</span></span>  
 <span data-ttu-id="54007-137">Wenn Sie eine Variante generische Schnittstelle erweitern, müssen Sie die `in` und `out` Schlüsselwörter explizit angeben, ob Varianz von der abgeleitete Schnittstelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54007-137">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="54007-138">Der Compiler leitet sich nicht auf die Abweichung von der Schnittstelle aus, der erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="54007-138">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="54007-139">Betrachten Sie beispielsweise die folgenden Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="54007-139">For example, consider the following interfaces.</span></span>  
  
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
  
 <span data-ttu-id="54007-140">In der `Invariant(Of T)` Schnittstelle, die generischen Typparameter `T` ist unveränderlich, während in `IExtCovariant (Of Out T)`der Typparameter ist kovariant, obwohl beide Schnittstellen die gleiche Schnittstelle erweitern.</span><span class="sxs-lookup"><span data-stu-id="54007-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="54007-141">Die gleiche Regel gilt für kontravariante generische Typparameter.</span><span class="sxs-lookup"><span data-stu-id="54007-141">The same rule is applied to contravariant generic type parameters.</span></span>  
  
 <span data-ttu-id="54007-142">Sie können eine Schnittstelle, die die Schnittstelle, in dem der generische Typparameter, erweitert erstellen `T` ist kovariant sowie die Schnittstelle mit dem kontravarianten in der erweiternden Schnittstelle den generische Typparameter `T` ist unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="54007-142">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="54007-143">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="54007-143">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="54007-144">Jedoch, wenn ein generischer Typparameter `T` ist kovariant in einer Schnittstelle deklariert, Deklaration kann nicht über kontravariante in der erweiternden Schnittstelle (oder umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="54007-144">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="54007-145">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="54007-145">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a><span data-ttu-id="54007-146">Vermeiden von Mehrdeutigkeit</span><span class="sxs-lookup"><span data-stu-id="54007-146">Avoiding Ambiguity</span></span>  
 <span data-ttu-id="54007-147">Wenn Sie eine Variante generische Schnittstellen implementieren, kann Varianz manchmal zu Mehrdeutigkeit führen.</span><span class="sxs-lookup"><span data-stu-id="54007-147">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="54007-148">Dies sollte vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="54007-148">This should be avoided.</span></span>  
  
 <span data-ttu-id="54007-149">Wenn Sie explizit die gleiche Variante generische Schnittstelle mit unterschiedlichen generischen Typparametern in einer Klasse implementieren, können sie z. B. Mehrdeutigkeit erstellen.</span><span class="sxs-lookup"><span data-stu-id="54007-149">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="54007-150">Der Compiler einen Fehler in diesem Fall erzeugt, aber es ist nicht angegeben, welche Implementierung zur Laufzeit ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="54007-150">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="54007-151">Dies kann zu schwer erkennbaren Fehlern im Code führen.</span><span class="sxs-lookup"><span data-stu-id="54007-151">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="54007-152">Betrachten Sie das folgende Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="54007-152">Consider the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54007-153">Mit `Option Strict Off`, Visual Basic generiert eine Warnung der Compiler, wenn eine Implementierung von mehrdeutiger vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="54007-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="54007-154">Mit `Option Strict On`, Visual Basic wird ein Compilerfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="54007-154">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>  
  
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
  
 <span data-ttu-id="54007-155">In diesem Beispiel ist nicht angegeben wie die `pets.GetEnumerator` Methode wählt zwischen `Cat` und `Dog`.</span><span class="sxs-lookup"><span data-stu-id="54007-155">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="54007-156">Dies kann Probleme im Code verursachen.</span><span class="sxs-lookup"><span data-stu-id="54007-156">This could cause problems in your code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54007-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54007-157">See Also</span></span>  
 <span data-ttu-id="54007-158">[Varianz in generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="54007-158">[Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span></span>  
<span data-ttu-id="54007-159"> [Verwenden von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="54007-159"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
