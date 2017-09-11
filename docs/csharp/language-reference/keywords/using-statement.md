---
title: using-Anweisung (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 201dde951b4f92d92b7d78b3d71a3f3cfb559507
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="using-statement-c-reference"></a><span data-ttu-id="70605-102">using-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="70605-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="70605-103">Bietet eine praktische Syntax, die den ordnungsgemäßen Einsatz von <xref:System.IDisposable>-Objekten sicherstellt</span><span class="sxs-lookup"><span data-stu-id="70605-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70605-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70605-104">Example</span></span>  
 <span data-ttu-id="70605-105">Im folgenden Beispiel wird die Verwendung der using-Anweisung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="70605-105">The following example shows how to use the using statement.</span></span>  
  
 <span data-ttu-id="70605-106">[!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="70605-106">[!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70605-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70605-107">Remarks</span></span>  
 <span data-ttu-id="70605-108"><xref:System.IO.File> und <xref:System.Drawing.Font> sind Beispiele für verwaltete Typen, die auf nicht verwaltete Ressourcen zugreifen (in diesem Fall Dateihandles und Gerätekontexte).</span><span class="sxs-lookup"><span data-stu-id="70605-108"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="70605-109">Es gibt viele andere Arten von nicht verwalteten Ressourcen und Klassenbibliothekstypen, die sie einschließen.</span><span class="sxs-lookup"><span data-stu-id="70605-109">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="70605-110">Alle Typen dieser Art müssen die <xref:System.IDisposable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="70605-110">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
 <span data-ttu-id="70605-111">In der Regel sollten Sie bei der Verwendung eines `IDisposable`-Objekts das Objekt in einer `using`-Anweisung deklarieren und instanziieren.</span><span class="sxs-lookup"><span data-stu-id="70605-111">As a rule, when you use an `IDisposable` object, you should declare and instantiate it in a `using` statement.</span></span> <span data-ttu-id="70605-112">Die `using`-Anweisung ruft die Methode <xref:System.IDisposable.Dispose%2A> ordnungsgemäß für das Objekt auf. Wenn Sie sie, wie vorher gezeigt, verwenden, führt dies auch dazu, dass das Objekt den gültigen Bereich verlässt, sobald <xref:System.IDisposable.Dispose%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="70605-112">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="70605-113">Innerhalb des `using`-Blocks ist das Objekt schreibgeschützt und kann nicht geändert oder neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="70605-113">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="70605-114">Die `using`-Anweisung stellt sicher, dass <xref:System.IDisposable.Dispose%2A> aufgerufen wird, auch wenn eine Ausnahme ausgelöst wird, während Sie die Methode für das Objekt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="70605-114">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs while you are calling methods on the object.</span></span> <span data-ttu-id="70605-115">Sie können das gleiche Ergebnis erzielen, indem Sie das Objekt in einen Try-Block einfügen und dann `using` in einem Finally-Block aufrufen; so wird die <xref:System.IDisposable.Dispose%2A>-Anweisung vom Compiler übersetzt.</span><span class="sxs-lookup"><span data-stu-id="70605-115">You can achieve the same result by putting the object inside a try block and then calling <xref:System.IDisposable.Dispose%2A> in a finally block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="70605-116">Das vorherige Codebeispiel wird zur Kompilierzeit auf den folgenden Code erweitert (beachten Sie die zusätzlichen geschweiften Klammern zum Erstellen des eingeschränkten Gültigkeitsbereichs für das Objekt):</span><span class="sxs-lookup"><span data-stu-id="70605-116">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 <span data-ttu-id="70605-117">[!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="70605-117">[!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]</span></span>  
  
 <span data-ttu-id="70605-118">Wie im folgenden Beispiel gezeigt, können mehrere Instanzen eines Typs in einer `using`-Anweisung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="70605-118">Multiple instances of a type can be declared in a `using` statement, as shown in the following example.</span></span>  
  
 <span data-ttu-id="70605-119">[!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="70605-119">[!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]</span></span>  
  
 <span data-ttu-id="70605-120">Sie können das Ressourcenobjekt instanziieren und die Variable an die `using`-Anweisung übergeben; dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="70605-120">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="70605-121">In diesem Fall verbleibt das Objekt im Gültigkeitsbereich, nachdem das `using`-Steuerelement den Block verlassen hat, obwohl es wahrscheinlich keinen Zugriff auf dessen nicht verwaltete Ressourcen mehr hat.</span><span class="sxs-lookup"><span data-stu-id="70605-121">In this case, the object remains in scope after control leaves the `using` block even though it will probably no longer have access to its unmanaged resources.</span></span> <span data-ttu-id="70605-122">Das heißt, es wird nicht mehr vollständig initialisiert.</span><span class="sxs-lookup"><span data-stu-id="70605-122">In other words, it will no longer be fully initialized.</span></span> <span data-ttu-id="70605-123">Wenn Sie versuchen, das Objekt außerhalb des `using`-Blocks zu verwenden, riskieren Sie, dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="70605-123">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="70605-124">Aus diesem Grund ist es im Allgemeinen besser, das Objekt in der `using`-Anweisung zu instanziieren und dessen Bereich auf den `using`-Block zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="70605-124">For this reason, it is generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 <span data-ttu-id="70605-125">[!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="70605-125">[!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="70605-126">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="70605-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="70605-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70605-127">See Also</span></span>  
 <span data-ttu-id="70605-128">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="70605-128">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="70605-129">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="70605-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="70605-130">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="70605-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="70605-131">[using-Direktive](../../../csharp/language-reference/keywords/using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="70605-131">[using Directive](../../../csharp/language-reference/keywords/using-directive.md) </span></span>  
 <span data-ttu-id="70605-132">[Garbage Collection](../../../standard/garbage-collection/index.md) </span><span class="sxs-lookup"><span data-stu-id="70605-132">[Garbage Collection](../../../standard/garbage-collection/index.md) </span></span>  
 [<span data-ttu-id="70605-133">Implementieren einer Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="70605-133">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)

