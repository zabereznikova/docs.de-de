---
title: using-Anweisung (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: ec4849dda0f28ad1f0e0ebb2c493a33005107db4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500971"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="bb08c-102">using-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bb08c-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="bb08c-103">Bietet eine praktische Syntax, die den ordnungsgemäßen Einsatz von <xref:System.IDisposable>-Objekten sicherstellt</span><span class="sxs-lookup"><span data-stu-id="bb08c-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb08c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb08c-104">Example</span></span>  
 <span data-ttu-id="bb08c-105">Im folgenden Beispiel wird veranschaulicht, wie Sie die Anweisung `using` verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb08c-105">The following example shows how to use the `using` statement.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="bb08c-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb08c-106">Remarks</span></span>  
 <span data-ttu-id="bb08c-107"><xref:System.IO.File> und <xref:System.Drawing.Font> sind Beispiele für verwaltete Typen, die auf nicht verwaltete Ressourcen zugreifen (in diesem Fall Dateihandles und Gerätekontexte).</span><span class="sxs-lookup"><span data-stu-id="bb08c-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="bb08c-108">Es gibt viele andere Arten von nicht verwalteten Ressourcen und Klassenbibliothekstypen, die sie einschließen.</span><span class="sxs-lookup"><span data-stu-id="bb08c-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="bb08c-109">Alle Typen dieser Art müssen die <xref:System.IDisposable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="bb08c-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
<span data-ttu-id="bb08c-110">Wenn die Lebensdauer eines `IDisposable`-Objekts auf eine einzige Methode beschränkt ist, sollten Sie es in der `using`-Anweisung deklarieren und instanziieren.</span><span class="sxs-lookup"><span data-stu-id="bb08c-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="bb08c-111">Die `using`-Anweisung ruft die Methode <xref:System.IDisposable.Dispose%2A> ordnungsgemäß für das Objekt auf. Wenn Sie sie, wie vorher gezeigt, verwenden, führt dies auch dazu, dass das Objekt den gültigen Bereich verlässt, sobald <xref:System.IDisposable.Dispose%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bb08c-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="bb08c-112">Innerhalb des `using`-Blocks ist das Objekt schreibgeschützt und kann nicht geändert oder neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="bb08c-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="bb08c-113">Mit der Anweisung `using` wird sichergestellt, dass <xref:System.IDisposable.Dispose%2A> aufgerufen wird, selbst wenn eine Ausnahme im `using`-Block auftritt.</span><span class="sxs-lookup"><span data-stu-id="bb08c-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="bb08c-114">Sie können das gleiche Ergebnis erzielen, indem Sie das Objekt in einen `try`-Block einfügen und dann <xref:System.IDisposable.Dispose%2A> in einem `finally`-Block aufrufen. So übersetzt der Compiler die Anweisung `using`.</span><span class="sxs-lookup"><span data-stu-id="bb08c-114">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="bb08c-115">Das vorherige Codebeispiel wird zur Kompilierzeit auf den folgenden Code erweitert (beachten Sie die zusätzlichen geschweiften Klammern zum Erstellen des eingeschränkten Gültigkeitsbereichs für das Objekt):</span><span class="sxs-lookup"><span data-stu-id="bb08c-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
 
 <span data-ttu-id="bb08c-116">Weitere Informationen über die Anweisung `try`-`finally` finden Sie im Artikel zu [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="bb08c-116">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>
  
 <span data-ttu-id="bb08c-117">Wie im folgenden Beispiel gezeigt, können mehrere Instanzen eines Typs in einer `using`-Anweisung deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="bb08c-117">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 <span data-ttu-id="bb08c-118">Sie können das Ressourcenobjekt instanziieren und die Variable an die `using`-Anweisung übergeben; dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="bb08c-118">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="bb08c-119">In diesem Fall verbleibt das Objekt im Gültigkeitsbereich, nachdem das Steuerelement den `using`-Block verlassen hat, obwohl es wahrscheinlich keinen Zugriff auf dessen nicht verwaltete Ressourcen hat.</span><span class="sxs-lookup"><span data-stu-id="bb08c-119">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="bb08c-120">Das heißt, dass es nicht mehr vollständig initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="bb08c-120">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="bb08c-121">Wenn Sie versuchen, das Objekt außerhalb des `using`-Blocks zu verwenden, riskieren Sie, dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="bb08c-121">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="bb08c-122">Aus diesem Grund ist es im Allgemeinen besser, das Objekt in der `using`-Anweisung zu instanziieren und dessen Bereich auf den `using`-Block zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="bb08c-122">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
<span data-ttu-id="bb08c-123">Weitere Informationen zum Verwerfen von `IDisposable`-Objekten finden Sie unter [Verwenden von Objekten, die IDisposable implementieren](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="bb08c-123">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bb08c-124">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="bb08c-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bb08c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb08c-125">See Also</span></span>

- [<span data-ttu-id="bb08c-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bb08c-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="bb08c-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bb08c-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bb08c-128">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bb08c-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="bb08c-129">using-Direktive</span><span class="sxs-lookup"><span data-stu-id="bb08c-129">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
- [<span data-ttu-id="bb08c-130">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="bb08c-130">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
- [<span data-ttu-id="bb08c-131">Verwenden von Objekten, die IDisposable implementieren</span><span class="sxs-lookup"><span data-stu-id="bb08c-131">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)  
- [<span data-ttu-id="bb08c-132">IDisposable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb08c-132">IDisposable interface</span></span>](xref:System.IDisposable)
