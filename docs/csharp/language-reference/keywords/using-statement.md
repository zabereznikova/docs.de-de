---
title: using-Anweisung (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1fdf37e1bfc57bf850b332f167e57d3e05d23e78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="9d89f-102">using-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9d89f-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="9d89f-103">Bietet eine praktische Syntax, die den ordnungsgemäßen Einsatz von <xref:System.IDisposable>-Objekten sicherstellt</span><span class="sxs-lookup"><span data-stu-id="9d89f-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d89f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d89f-104">Example</span></span>  
 <span data-ttu-id="9d89f-105">Im folgenden Beispiel wird die Verwendung der using-Anweisung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9d89f-105">The following example shows how to use the using statement.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="9d89f-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d89f-106">Remarks</span></span>  
 <span data-ttu-id="9d89f-107"><xref:System.IO.File> und <xref:System.Drawing.Font> sind Beispiele für verwaltete Typen, die auf nicht verwaltete Ressourcen zugreifen (in diesem Fall Dateihandles und Gerätekontexte).</span><span class="sxs-lookup"><span data-stu-id="9d89f-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="9d89f-108">Es gibt viele andere Arten von nicht verwalteten Ressourcen und Klassenbibliothekstypen, die sie einschließen.</span><span class="sxs-lookup"><span data-stu-id="9d89f-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="9d89f-109">Alle Typen dieser Art müssen die <xref:System.IDisposable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="9d89f-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
<span data-ttu-id="9d89f-110">Wenn die Lebensdauer des ein `IDisposable` Objekt auf eine einzelne Methode beschränkt ist, sollten Sie deklarieren und instanziieren Sie ihn in eine `using` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9d89f-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in a `using` statement.</span></span> <span data-ttu-id="9d89f-111">Die `using`-Anweisung ruft die Methode <xref:System.IDisposable.Dispose%2A> ordnungsgemäß für das Objekt auf. Wenn Sie sie, wie vorher gezeigt, verwenden, führt dies auch dazu, dass das Objekt den gültigen Bereich verlässt, sobald <xref:System.IDisposable.Dispose%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9d89f-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="9d89f-112">Innerhalb des `using`-Blocks ist das Objekt schreibgeschützt und kann nicht geändert oder neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9d89f-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="9d89f-113">Die `using`-Anweisung stellt sicher, dass <xref:System.IDisposable.Dispose%2A> aufgerufen wird, auch wenn eine Ausnahme ausgelöst wird, während Sie die Methode für das Objekt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9d89f-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs while you are calling methods on the object.</span></span> <span data-ttu-id="9d89f-114">Sie können das gleiche Ergebnis erzielen, indem Sie das Objekt in einen Try-Block einfügen und dann `using` in einem Finally-Block aufrufen; so wird die <xref:System.IDisposable.Dispose%2A>-Anweisung vom Compiler übersetzt.</span><span class="sxs-lookup"><span data-stu-id="9d89f-114">You can achieve the same result by putting the object inside a try block and then calling <xref:System.IDisposable.Dispose%2A> in a finally block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="9d89f-115">Das vorherige Codebeispiel wird zur Kompilierzeit auf den folgenden Code erweitert (beachten Sie die zusätzlichen geschweiften Klammern zum Erstellen des eingeschränkten Gültigkeitsbereichs für das Objekt):</span><span class="sxs-lookup"><span data-stu-id="9d89f-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 <span data-ttu-id="9d89f-116">Wie im folgenden Beispiel gezeigt, können mehrere Instanzen eines Typs in einer `using`-Anweisung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="9d89f-116">Multiple instances of a type can be declared in a `using` statement, as shown in the following example.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 <span data-ttu-id="9d89f-117">Sie können das Ressourcenobjekt instanziieren und die Variable an die `using`-Anweisung übergeben; dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9d89f-117">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="9d89f-118">In diesem Fall verbleibt das Objekt im Gültigkeitsbereich, nachdem das `using`-Steuerelement den Block verlassen hat, obwohl es wahrscheinlich keinen Zugriff auf dessen nicht verwaltete Ressourcen mehr hat.</span><span class="sxs-lookup"><span data-stu-id="9d89f-118">In this case, the object remains in scope after control leaves the `using` block even though it will probably no longer have access to its unmanaged resources.</span></span> <span data-ttu-id="9d89f-119">Das heißt, es wird nicht mehr vollständig initialisiert.</span><span class="sxs-lookup"><span data-stu-id="9d89f-119">In other words, it will no longer be fully initialized.</span></span> <span data-ttu-id="9d89f-120">Wenn Sie versuchen, das Objekt außerhalb des `using`-Blocks zu verwenden, riskieren Sie, dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9d89f-120">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="9d89f-121">Aus diesem Grund ist es im Allgemeinen besser, das Objekt in der `using`-Anweisung zu instanziieren und dessen Bereich auf den `using`-Block zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="9d89f-121">For this reason, it is generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
<span data-ttu-id="9d89f-122">Weitere Informationen zum Freigeben von `IDisposable` anzuzeigen, [mit Objekten, die IDisposable implementieren](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="9d89f-122">For more information on disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9d89f-123">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="9d89f-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9d89f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d89f-124">See Also</span></span>  
 [<span data-ttu-id="9d89f-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9d89f-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9d89f-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9d89f-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9d89f-127">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9d89f-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9d89f-128">using-Direktive</span><span class="sxs-lookup"><span data-stu-id="9d89f-128">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="9d89f-129">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="9d89f-129">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
 [<span data-ttu-id="9d89f-130">Verwenden von Objekten, die IDisposable implementieren</span><span class="sxs-lookup"><span data-stu-id="9d89f-130">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)  
 [<span data-ttu-id="9d89f-131">IDisposable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d89f-131">IDisposable interface</span></span>](xref:System.IDisposable)
