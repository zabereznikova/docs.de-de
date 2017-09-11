---
title: Varianz in generischen Schnittstellen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
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
ms.openlocfilehash: c53c27bdb085213046553fc4b08f11336880a7c2
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-visual-basic"></a><span data-ttu-id="ac5aa-102">Varianz in generischen Schnittstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac5aa-102">Variance in Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="ac5aa-103">Varianz-Unterstützung für mehrere vorhandene generische Schnittstellen wurde in .NET Framework 4 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="ac5aa-104">Varianz-Unterstützung ermöglicht die implizite Konvertierung von Klassen, die diese Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="ac5aa-105">Die folgenden Schnittstellen sind jetzt Variant:</span><span class="sxs-lookup"><span data-stu-id="ac5aa-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="ac5aa-106"><xref:System.Collections.Generic.IEnumerable%601>(T ist kovariant)</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="ac5aa-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="ac5aa-107"><xref:System.Collections.Generic.IEnumerator%601>(T ist kovariant)</xref:System.Collections.Generic.IEnumerator%601></span><span class="sxs-lookup"><span data-stu-id="ac5aa-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="ac5aa-108"><xref:System.Linq.IQueryable%601>(T ist kovariant)</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="ac5aa-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="ac5aa-109"><xref:System.Linq.IGrouping%602>(`TKey` und `TElement` sind kovariant)</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="ac5aa-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="ac5aa-110"><xref:System.Collections.Generic.IComparer%601>(T ist kontravariant)</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="ac5aa-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="ac5aa-111"><xref:System.Collections.Generic.IEqualityComparer%601>(T ist kontravariant)</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="ac5aa-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="ac5aa-112"><xref:System.IComparable%601>(T ist kontravariant)</xref:System.IComparable%601></span><span class="sxs-lookup"><span data-stu-id="ac5aa-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="ac5aa-113">Kovarianz unterstützt eine Methode mit einem stärker abgeleiteten Rückgabetyp, als durch den generischen Typparameter der Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="ac5aa-114">Die Kovarianzfunktion betrachten Sie zur Veranschaulichung folgenden generischen Schnittstellen: `IEnumerable(Of Object)` und `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable(Of Object)` and `IEnumerable(Of String)`.</span></span> <span data-ttu-id="ac5aa-115">Die `IEnumerable(Of String)` Schnittstelle erbt nicht die `IEnumerable(Of Object)` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-115">The `IEnumerable(Of String)` interface does not inherit the `IEnumerable(Of Object)` interface.</span></span> <span data-ttu-id="ac5aa-116">Allerdings die `String` Typ erbt die `Object` Typ, und in einigen Fällen Sie möglicherweise Objekte dieser Schnittstellen einander zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="ac5aa-117">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-117">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="ac5aa-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="ac5aa-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="ac5aa-119">In früheren Versionen von .NET Framework, dieser Code verursacht einen Kompilierungsfehler in Visual Basic mit `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-119">In earlier versions of the .NET Framework, this code causes a compilation error in Visual Basic with `Option Strict On`.</span></span> <span data-ttu-id="ac5aa-120">Aber jetzt können Sie `strings` anstelle von `objects`, wie im vorherigen Beispiel dargestellt, da die <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle ist kovariant.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="ac5aa-120">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="ac5aa-121">Kontravarianz unterstützt eine Methode von Argumenttypen, die weniger stark abgeleitet sind, als durch den generischen Parameter der Schnittstelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-121">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="ac5aa-122">Zur Veranschaulichung der Kontravarianz wird angenommen, Sie erstellt haben eine `BaseComparer` zum Vergleichen von Instanzen der Klasse die `BaseClass` Klasse.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-122">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="ac5aa-123">Die `BaseComparer`-Klasse implementiert die `IEqualityComparer(Of BaseClass)`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-123">The `BaseComparer` class implements the `IEqualityComparer(Of BaseClass)` interface.</span></span> <span data-ttu-id="ac5aa-124">Da die <xref:System.Collections.Generic.IEqualityComparer%601>-Schnittstelle kontravariant ist, können Sie `BaseComparer` Instanzen von Klassen vergleichen, die erben die `BaseClass` Klasse</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="ac5aa-124">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="ac5aa-125">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-125">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="ac5aa-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="ac5aa-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="ac5aa-127">Weitere Beispiele finden Sie unter [Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="ac5aa-127">For more examples, see [Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="ac5aa-128">Varianz in generischen Schnittstellen ist nur für Verweistypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-128">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="ac5aa-129">Werttypen unterstützen keine Varianz.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-129">Value types do not support variance.</span></span> <span data-ttu-id="ac5aa-130">Beispielsweise `IEnumerable(Of Integer)` kann implizit in konvertiert `IEnumerable(Of Object)`, da ganze Zahlen durch einen Werttyp dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-130">For example, `IEnumerable(Of Integer)` cannot be implicitly converted to `IEnumerable(Of Object)`, because integers are represented by a value type.</span></span>  
  
<span data-ttu-id="ac5aa-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="ac5aa-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="ac5aa-132">Es ist auch wichtig zu beachten, dass Klassen, die Variante Schnittstellen implementieren, immer noch invariant sind.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="ac5aa-133">Z. B. zwar <xref:System.Collections.Generic.List%601>implementiert die Schnittstelle kovariante <xref:System.Collections.Generic.IEnumerable%601>, können nicht implizit konvertiert `List(Of Object)` , `List(Of String)`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="ac5aa-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List(Of Object)` to `List(Of String)`.</span></span> <span data-ttu-id="ac5aa-134">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac5aa-134">This is illustrated in the following code example.</span></span>  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac5aa-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac5aa-135">See Also</span></span>  
 <span data-ttu-id="ac5aa-136">[Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span><span class="sxs-lookup"><span data-stu-id="ac5aa-136">[Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span></span>  
<span data-ttu-id="ac5aa-137"> [Erstellen von Varianten generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="ac5aa-137"> [Creating Variant Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span></span>  
<span data-ttu-id="ac5aa-138"> [Generische Schnittstellen](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span><span class="sxs-lookup"><span data-stu-id="ac5aa-138"> [Generic Interfaces](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span></span>  
<span data-ttu-id="ac5aa-139"> [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="ac5aa-139"> [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span></span>
