---
title: Varianz in Delegaten (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cbab7da8c97ca202f8a4d0a1a65b8fa240cca32d
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-delegates-visual-basic"></a><span data-ttu-id="4de49-102">Varianz in Delegaten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4de49-102">Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="4de49-103">Varianz-Unterstützung um Methodensignaturen und Delegattypen in alle Delegaten in c# und Visual Basic wurde in .NET Framework 3.5 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4de49-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic.</span></span> <span data-ttu-id="4de49-104">Dies bedeutet, die Sie zuweisen können Delegaten nicht nur Methoden, die über übereinstimmende Signaturen verfügen, sondern auch Methoden, stärker abgeleitete Typen (Kovarianz) oder Parameter annehmen, die weniger stark abgeleiteten Typen (Kontravarianz sind) als vom Delegattyp angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="4de49-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="4de49-105">Dies schließt die generische und nicht generischen Delegaten.</span><span class="sxs-lookup"><span data-stu-id="4de49-105">This includes both generic and non-generic delegates.</span></span>  
  
 <span data-ttu-id="4de49-106">Betrachten Sie beispielsweise den folgenden Code, der zwei Klassen und zwei Delegaten aufweist: generisch und nicht generisch.</span><span class="sxs-lookup"><span data-stu-id="4de49-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>  
  
```vb  
Public Class First  
End Class  
  
Public Class Second  
    Inherits First  
End Class  
  
Public Delegate Function SampleDelegate(ByVal a As Second) As First  
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R  
```  
  
 <span data-ttu-id="4de49-107">Beim Erstellen von Delegaten, der die `SampleDelegate` oder `SampleDelegate(Of A, R)` Typen, Sie können eine der folgenden Methoden an diesen Delegaten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4de49-107">When you create delegates of the `SampleDelegate` or `SampleDelegate(Of A, R)` types, you can assign any one of the following methods to those delegates.</span></span>  
  
```vb  
' Matching signature.  
Public Shared Function ASecondRFirst(  
    ByVal second As Second) As First  
    Return New First()  
End Function  
  
' The return type is more derived.  
Public Shared Function ASecondRSecond(  
    ByVal second As Second) As Second  
    Return New Second()  
End Function  
  
' The argument type is less derived.  
Public Shared Function AFirstRFirst(  
    ByVal first As First) As First  
    Return New First()  
End Function  
  
' The return type is more derived   
' and the argument type is less derived.  
Public Shared Function AFirstRSecond(  
    ByVal first As First) As Second  
    Return New Second()  
End Function  
```  
  
 <span data-ttu-id="4de49-108">Das folgende Codebeispiel veranschaulicht die implizite Konvertierung zwischen der Methodensignatur und dem Typ des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="4de49-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>  
  
```vb  
' Assigning a method with a matching signature   
' to a non-generic delegate. No conversion is necessary.  
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst  
' Assigning a method with a more derived return type   
' and less derived argument type to a non-generic delegate.  
' The implicit conversion is used.  
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond  
  
' Assigning a method with a matching signature to a generic delegate.  
' No conversion is necessary.  
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst  
' Assigning a method with a more derived return type   
' and less derived argument type to a generic delegate.  
' The implicit conversion is used.  
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond  
```  
  
 <span data-ttu-id="4de49-109">Weitere Beispiele finden Sie unter [Verwenden von Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) und [mithilfe von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="4de49-109">For more examples, see [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="4de49-110">Varianz in generischen Typparametern</span><span class="sxs-lookup"><span data-stu-id="4de49-110">Variance in Generic Type Parameters</span></span>  
 <span data-ttu-id="4de49-111">In .NET Framework 4 und höher können Sie die implizite Konvertierung zwischen Delegaten, aktivieren, sodass generischen Delegaten, die verschiedene Typen von generischen Typparametern angegeben haben, zugewiesen werden können, wenn die Typen von einander gemäß der Varianz geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="4de49-111">In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>  
  
 <span data-ttu-id="4de49-112">Um die implizite Konvertierung zu aktivieren, müssen Sie explizit deklarieren generische Parametern in einen Delegaten als kovariant oder kontravariant mithilfe der `in` oder `out` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4de49-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>  
  
 <span data-ttu-id="4de49-113">Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Delegaten erstellen können, der über einen kovarianten generischen Typparameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="4de49-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>  
  
```vb  
' Type T is declared covariant by using the out keyword.  
Public Delegate Function SampleGenericDelegate(Of Out T)() As T  
Sub Test()  
    Dim dString As SampleGenericDelegate(Of String) = Function() " "  
    ' You can assign delegates to each other,  
    ' because the type T is declared covariant.  
    Dim dObject As SampleGenericDelegate(Of Object) = dString  
End Sub  
```  
  
 <span data-ttu-id="4de49-114">Bei Verwendung des unterstützen nur Varianz entsprechend Methodensignaturen mit Delegattypen und verwenden Sie nicht die `in` und `out` Schlüsselwörter, können Sie feststellen, dass manchmal können Sie Delegaten mit identischen Lambda-Ausdrücke oder Methoden instanziieren, aber nicht, Sie einem Delegaten in einen anderen weisen kann.</span><span class="sxs-lookup"><span data-stu-id="4de49-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>  
  
 <span data-ttu-id="4de49-115">Im folgenden Codebeispiel `SampleGenericDelegate(Of String)` nicht explizit in konvertiert werden `SampleGenericDelegate(Of Object)`, obwohl `String` erbt `Object`.</span><span class="sxs-lookup"><span data-stu-id="4de49-115">In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`.</span></span> <span data-ttu-id="4de49-116">Sie können dieses Problem beheben, indem der generische Parameter markieren `T` mit dem `out` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4de49-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>  
  
```vb  
Public Delegate Function SampleGenericDelegate(Of T)() As T  
Sub Test()  
    Dim dString As SampleGenericDelegate(Of String) = Function() " "  
  
    ' You can assign the dObject delegate  
    ' to the same lambda expression as dString delegate  
    ' because of the variance support for   
    ' matching method signatures with delegate types.  
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "  
  
    ' The following statement generates a compiler error  
    ' because the generic type T is not marked as covariant.  
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString  
  
End Sub  
```  
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="4de49-117">Generische Delegaten mit Varianten Typparametern in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4de49-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>  
 <span data-ttu-id="4de49-118">.NET Framework 4 wurde die Varianz-Unterstützung für generische Typparameter in mehrere vorhandene generische Delegaten:</span><span class="sxs-lookup"><span data-stu-id="4de49-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>  
  
-   <span data-ttu-id="4de49-119">`Action`-Delegaten aus dem <xref:System>-Namespace, z. B. <xref:System.Action%601>und <xref:System.Action%602></xref:System.Action%602> </xref:System.Action%601> </xref:System></span><span class="sxs-lookup"><span data-stu-id="4de49-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>  
  
-   <span data-ttu-id="4de49-120">`Func`-Delegaten aus dem <xref:System>-Namespace, z. B. <xref:System.Func%601>und <xref:System.Func%602></xref:System.Func%602> </xref:System.Func%601> </xref:System></span><span class="sxs-lookup"><span data-stu-id="4de49-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>  
  
-   <span data-ttu-id="4de49-121">Der <xref:System.Predicate%601>Delegat</xref:System.Predicate%601></span><span class="sxs-lookup"><span data-stu-id="4de49-121">The <xref:System.Predicate%601> delegate</span></span>  
  
-   <span data-ttu-id="4de49-122">Der <xref:System.Comparison%601>Delegat</xref:System.Comparison%601></span><span class="sxs-lookup"><span data-stu-id="4de49-122">The <xref:System.Comparison%601> delegate</span></span>  
  
-   <span data-ttu-id="4de49-123">Der <xref:System.Converter%602>Delegat</xref:System.Converter%602></span><span class="sxs-lookup"><span data-stu-id="4de49-123">The <xref:System.Converter%602> delegate</span></span>  
  
 <span data-ttu-id="4de49-124">Weitere Informationen und Beispiele finden Sie unter [mithilfe von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="4de49-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="4de49-125">Deklarieren von Varianten Typparametern in generischen Delegaten</span><span class="sxs-lookup"><span data-stu-id="4de49-125">Declaring Variant Type Parameters in Generic Delegates</span></span>  
 <span data-ttu-id="4de49-126">Wenn für ein generischer Delegaten kovariant oder kontravariante generische Typparameter, es kann als bezeichnet ein *generischen Delegaten*.</span><span class="sxs-lookup"><span data-stu-id="4de49-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>  
  
 <span data-ttu-id="4de49-127">Sie können einen generischen Typparameter kovariant in einem generischen Delegaten deklarieren, indem die `out` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4de49-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="4de49-128">Der kovariante Typ kann nur als Methodenrückgabetyp und nicht als Typ von Methodenargumenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4de49-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="4de49-129">Im folgenden Codebeispiel wird veranschaulicht, wie einen kovarianten generischen Delegat deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="4de49-129">The following code example shows how to declare a covariant generic delegate.</span></span>  
  
<span data-ttu-id="4de49-130"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4de49-130"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4de49-131">Sie können einen generischen Typparameter in einem generischen Delegaten als Kontravariante deklarieren, indem die `in` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4de49-131">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="4de49-132">Der kontravariante Typ kann nur als Typ von Methodenargumenten und nicht als Methodenrückgabetyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4de49-132">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="4de49-133">Im folgenden Codebeispiel wird veranschaulicht, wie einen kontravarianter generischer Delegat deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="4de49-133">The following code example shows how to declare a contravariant generic delegate.</span></span>  
  
<span data-ttu-id="4de49-134"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4de49-134"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
> [!IMPORTANT]
> <span data-ttu-id="4de49-135"> `ByRef`-Parameter in Visual Basic können nicht als Variant gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="4de49-135"> `ByRef` parameters in Visual Basic can't be marked as variant.</span></span>  
  
 <span data-ttu-id="4de49-136">Es ist auch möglich, Varianz und Kovarianz im gleichen Delegaten, aber für unterschiedliche Typparameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4de49-136">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="4de49-137">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4de49-137">This is shown in the following example.</span></span>  
  
<span data-ttu-id="4de49-138"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4de49-138"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="4de49-139">Instanziieren und Aufrufen von Varianten generischen Delegaten</span><span class="sxs-lookup"><span data-stu-id="4de49-139">Instantiating and Invoking Variant Generic Delegates</span></span>  
 <span data-ttu-id="4de49-140">Sie können instanziiert und Variante Delegaten aufrufen, wie Sie instanziieren und aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4de49-140">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="4de49-141">Im folgenden Beispiel wird der Delegat durch einen Lambda-Ausdruck instanziiert.</span><span class="sxs-lookup"><span data-stu-id="4de49-141">In the following example, the delegate is instantiated by a lambda expression.</span></span>  
  
<span data-ttu-id="4de49-142"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4de49-142"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="4de49-143">Kombinieren von Varianten generischen Delegaten</span><span class="sxs-lookup"><span data-stu-id="4de49-143">Combining Variant Generic Delegates</span></span>  
 <span data-ttu-id="4de49-144">Variante Delegaten sollten nicht kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="4de49-144">You should not combine variant delegates.</span></span> <span data-ttu-id="4de49-145">Die <xref:System.Delegate.Combine%2A>Methode unterstützt keine delegatenkonvertierung und erwartet Delegaten genau den gleichen Typ sein.</xref:System.Delegate.Combine%2A></span><span class="sxs-lookup"><span data-stu-id="4de49-145">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="4de49-146">Dies kann zu einer Laufzeitausnahme führen, beim Kombinieren von Delegaten, die entweder mithilfe der <xref:System.Delegate.Combine%2A>-Methode (in c# und Visual Basic) oder mithilfe der `+` -Operator (in c#), wie im folgenden Codebeispiel gezeigt.</xref:System.Delegate.Combine%2A></span><span class="sxs-lookup"><span data-stu-id="4de49-146">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.</span></span>  
  
<span data-ttu-id="4de49-147"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4de49-147"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="4de49-148">Varianz in generischen Typparametern für Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="4de49-148">Variance in Generic Type Parameters for Value and Reference Types</span></span>  
 <span data-ttu-id="4de49-149">Varianz für die generischen Typparameter wird nur für Verweistypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4de49-149">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="4de49-150">Beispielsweise `DVariant(Of Int)`kann implizit in konvertiert `DVariant(Of Object)` oder `DVariant(Of Long)`, da ganze Zahl ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="4de49-150">For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.</span></span>  
  
 <span data-ttu-id="4de49-151">Das folgende Beispiel veranschaulicht, dass Varianz in generischen Typ Parameter nicht für Werttypen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4de49-151">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>  
  
```vb  
' The type T is covariant.  
Public Delegate Function DVariant(Of Out T)() As T  
' The type T is invariant.  
Public Delegate Function DInvariant(Of T)() As T  
Sub Test()  
    Dim i As Integer = 0  
    Dim dInt As DInvariant(Of Integer) = Function() i  
    Dim dVaraintInt As DVariant(Of Integer) = Function() i  
  
    ' All of the following statements generate a compiler error  
    ' because type variance in generic parameters is not supported  
    ' for value types, even if generic type parameters are declared variant.  
    ' Dim dObject As DInvariant(Of Object) = dInt  
    ' Dim dLong As DInvariant(Of Long) = dInt  
    ' Dim dVaraintObject As DInvariant(Of Object) = dInt  
    ' Dim dVaraintLong As DInvariant(Of Long) = dInt  
End Sub  
```  
  
## <a name="relaxed-delegate-conversion-in-visual-basic"></a><span data-ttu-id="4de49-152">Gelockerte Delegatenkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4de49-152">Relaxed Delegate Conversion in Visual Basic</span></span>  
 <span data-ttu-id="4de49-153">Gelockerte delegatenkonvertierung ermöglicht mehr Flexibilität in Methodensignaturen und Delegattypen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="4de49-153">Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types.</span></span> <span data-ttu-id="4de49-154">Beispielsweise können Sie Parameterspezifikationen und Rückgabewerte verzichten, wenn Sie einem Delegaten eine Methode zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4de49-154">For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate.</span></span> <span data-ttu-id="4de49-155">Weitere Informationen finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="4de49-155">For more information, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de49-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4de49-156">See Also</span></span>  
 <span data-ttu-id="4de49-157">[Generika](https://msdn.microsoft.com/library/ms172192) </span><span class="sxs-lookup"><span data-stu-id="4de49-157">[Generics](https://msdn.microsoft.com/library/ms172192) </span></span>  
<span data-ttu-id="4de49-158"> [Verwenden von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="4de49-158"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
