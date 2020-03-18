---
title: Verwenden von Objekten, die IDisposable implementieren
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: c5232aa89064c514e71f3a18bc754159e9c9b15b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160279"
---
# <a name="using-objects-that-implement-idisposable"></a><span data-ttu-id="8de8c-102">Verwenden von Objekten, die IDisposable implementieren</span><span class="sxs-lookup"><span data-stu-id="8de8c-102">Using objects that implement IDisposable</span></span>

<span data-ttu-id="8de8c-103">Der Garbage Collector der Common Language Runtime gibt den Speicher frei, der von verwalteten Objekten verwendet wird. Typen jedoch, die nicht verwaltete Ressourcen verwenden, implementieren die <xref:System.IDisposable>-Schnittstelle, damit der Speicher, der diesen nicht verwalteten Ressourcen zugeordnet ist, freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="8de8c-103">The common language runtime's garbage collector reclaims the memory used by managed objects, but types that use unmanaged resources implement the <xref:System.IDisposable> interface to allow the memory allocated to these unmanaged resources to be reclaimed.</span></span> <span data-ttu-id="8de8c-104">Wenn Sie ein Objekt, das <xref:System.IDisposable> implementiert, nicht mehr verwenden, sollten Sie die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung des Objekts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8de8c-104">When you finish using an object that implements <xref:System.IDisposable>, you should call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="8de8c-105">Dazu haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="8de8c-105">You can do this in one of two ways:</span></span>  
  
- <span data-ttu-id="8de8c-106">Verwenden der `using`-Anweisung in C# oder der `Using`-Anweisung in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8de8c-106">With the C# `using` statement or the Visual Basic `Using` statement.</span></span>  
  
- <span data-ttu-id="8de8c-107">Implementieren eines `try/finally`-Blocks.</span><span class="sxs-lookup"><span data-stu-id="8de8c-107">By implementing a `try/finally` block.</span></span>  

## <a name="the-using-statement"></a><span data-ttu-id="8de8c-108">Die using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8de8c-108">The using statement</span></span>

<span data-ttu-id="8de8c-109">Die `using`-Anweisung in C# und die `Using`-Anweisung in Visual Basic vereinfachen den Code, den Sie schreiben müssen, um ein Objekt zu erstellen und zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="8de8c-109">The `using` statement in C# and the `Using` statement in Visual Basic simplify the code that you must write to create and clean up an object.</span></span> <span data-ttu-id="8de8c-110">Die `using`-Anweisung ruft eine oder mehrere Ressourcen ab, führt die von Ihnen angegebenen Anweisungen aus und verwirft dann das Objekt automatisch.</span><span class="sxs-lookup"><span data-stu-id="8de8c-110">The `using` statement obtains one or more resources, executes the statements that you specify, and automatically disposes of the object.</span></span> <span data-ttu-id="8de8c-111">Die `using`-Anweisung ist jedoch nur hilfreich bei Objekten, die im Bereich der Methode verwendet werden, in der sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8de8c-111">However, the `using` statement is useful only for objects that are used within the scope of the method in which they are constructed.</span></span>  
  
<span data-ttu-id="8de8c-112">Im folgenden Beispiel wird die `using`-Anweisung verwendet, um ein <xref:System.IO.StreamReader?displayProperty=nameWithType>-Objekt zu erstellen und freizugeben.</span><span class="sxs-lookup"><span data-stu-id="8de8c-112">The following example uses the `using` statement to create and release a <xref:System.IO.StreamReader?displayProperty=nameWithType> object.</span></span>  
  
[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
<span data-ttu-id="8de8c-113">Beachten Sie Folgendes: Obwohl die <xref:System.IO.StreamReader>-Klasse die <xref:System.IDisposable>-Schnittstelle implementiert, die angibt, dass sie eine nicht verwaltete Ressource verwendet, wird in dem Beispiel nicht explizit die <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8de8c-113">Note that although the <xref:System.IO.StreamReader> class implements the <xref:System.IDisposable> interface, which indicates that it uses an unmanaged resource, the example doesn't explicitly call the <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="8de8c-114">Wenn der C#- oder Visual Basic-Compiler die `using`-Anweisung findet, gibt er Zwischensprache (Intermediate Language, IL) aus, die dem folgenden Code entspricht, der explizit einen `try/finally`-Block enthält.</span><span class="sxs-lookup"><span data-stu-id="8de8c-114">When the C# or Visual Basic compiler encounters the `using` statement, it emits intermediate language (IL) that is equivalent to the following code that explicitly contains a `try/finally` block.</span></span>  
  
[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
<span data-ttu-id="8de8c-115">Mit der `using`-Anweisung in C# können Sie auch mehrere Ressourcen in einer einzigen Anweisung abrufen. Intern entspricht dies geschachtelten `using`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="8de8c-115">The C# `using` statement also allows you to acquire multiple resources in a single statement, which is internally equivalent to nested `using` statements.</span></span> <span data-ttu-id="8de8c-116">Im folgenden Beispiel werden zwei <xref:System.IO.StreamReader>-Objekte instanziiert, um den Inhalt von zwei verschiedenen Dateien zu lesen.</span><span class="sxs-lookup"><span data-stu-id="8de8c-116">The following example instantiates two <xref:System.IO.StreamReader> objects to read the contents of two different files.</span></span>  
  
[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a><span data-ttu-id="8de8c-117">Try-/Finally-Block</span><span class="sxs-lookup"><span data-stu-id="8de8c-117">Try/finally block</span></span>

<span data-ttu-id="8de8c-118">Anstatt einen `try/finally`-Block in einer `using`-Anweisung zu umschließen, haben Sie die Möglichkeit, den `try/finally`-Block direkt zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="8de8c-118">Instead of wrapping a `try/finally` block in a `using` statement, you may choose to implement the `try/finally` block directly.</span></span> <span data-ttu-id="8de8c-119">Dies kann Ihr persönlicher Codierungsstil sein, oder Sie möchten dies eventuell aus einem der folgenden Gründe durchführen:</span><span class="sxs-lookup"><span data-stu-id="8de8c-119">This may be your personal coding style, or you might want to do this for one of the following reasons:</span></span>  
  
- <span data-ttu-id="8de8c-120">Um einen `catch`-Block einzufügen, um im `try`-Block ausgelöste Ausnahmen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="8de8c-120">To include a `catch` block to handle any exceptions thrown in the `try` block.</span></span> <span data-ttu-id="8de8c-121">Andernfalls bleiben alle Ausnahmen, die von der `using`-Anweisung ausgelöst werden, unbehandelt, so wie Ausnahmen, die innerhalb des `using`-Blocks ausgelöst werden, wenn kein `try/catch`-Block vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8de8c-121">Otherwise, any exceptions thrown by the `using` statement are unhandled, as are any exceptions thrown within the `using` block if a `try/catch` block isn't present.</span></span>  
  
- <span data-ttu-id="8de8c-122">Um ein Objekt zu instanziieren, das <xref:System.IDisposable> implementiert, dessen Bereich für den Block, in dem es deklariert ist, nicht lokal ist.</span><span class="sxs-lookup"><span data-stu-id="8de8c-122">To instantiate an object that implements <xref:System.IDisposable> whose scope is not local to the block within which it is declared.</span></span>  
  
<span data-ttu-id="8de8c-123">Das folgende Beispiel ähnelt dem vorhergehenden, es wird jedoch ein `try/catch/finally`-Block verwendet, um ein <xref:System.IO.StreamReader>-Objekt zu instanziieren, zu verwenden und zu verwerfen, und um alle Ausnahmen zu behandeln, die von dem <xref:System.IO.StreamReader>-Konstruktor und dessen <xref:System.IO.StreamReader.ReadToEnd%2A>-Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="8de8c-123">The following example is similar to the previous example, except that it uses a `try/catch/finally` block to instantiate, use, and dispose of a <xref:System.IO.StreamReader> object, and to handle any exceptions thrown by the <xref:System.IO.StreamReader> constructor and its <xref:System.IO.StreamReader.ReadToEnd%2A> method.</span></span> <span data-ttu-id="8de8c-124">Beachten Sie, dass der Code im `finally`-Block überprüft, ob das Objekt, das <xref:System.IDisposable> implementiert, nicht `null` ist, bevor die <xref:System.IDisposable.Dispose%2A>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8de8c-124">Note that the code in the `finally` block checks that the object that implements <xref:System.IDisposable> isn't `null` before it calls the <xref:System.IDisposable.Dispose%2A> method.</span></span> <span data-ttu-id="8de8c-125">Wird dies nicht ausgeführt, kann es zu einer <xref:System.NullReferenceException>-Ausnahme zur Laufzeit kommen.</span><span class="sxs-lookup"><span data-stu-id="8de8c-125">Failure to do this can result in a <xref:System.NullReferenceException> exception at run time.</span></span>  
  
[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
<span data-ttu-id="8de8c-126">Sie können dieses grundlegende Muster beibehalten, wenn Sie einen `try/finally`-Block implementieren möchten oder müssen, da Ihre Programmiersprache eine `using`-Anweisung nicht unterstützt, jedoch direkte Aufrufe der <xref:System.IDisposable.Dispose%2A>-Methode erlaubt.</span><span class="sxs-lookup"><span data-stu-id="8de8c-126">You can follow this basic pattern if you choose to implement or must implement a `try/finally` block, because your programming language doesn't support a `using` statement but does allow direct calls to the <xref:System.IDisposable.Dispose%2A> method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8de8c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8de8c-127">See also</span></span>

- [<span data-ttu-id="8de8c-128">Bereinigen von nicht verwalteten Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8de8c-128">Cleaning Up Unmanaged Resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
- [<span data-ttu-id="8de8c-129">using-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8de8c-129">using Statement (C# Reference)</span></span>](../../csharp/language-reference/keywords/using-statement.md)
- [<span data-ttu-id="8de8c-130">Using-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8de8c-130">Using Statement (Visual Basic)</span></span>](../../visual-basic/language-reference/statements/using-statement.md)
