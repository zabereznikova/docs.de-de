---
title: 'Vorgehensweise: Behandeln von Ausnahmen in parallelen Schleifen'
description: Erfahren Sie, wie Sie Ausnahmen in parallelen Schleifen in .NET verarbeiten. In diesem Artikel wird ein Beispiel dafür gezeigt, wie Sie alle Ausnahmen aus der Schleife in System.AggregateException umschließen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
ms.openlocfilehash: 61c22d6e82282f8aeb54818c813d4489e3bc9641
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768975"
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="459c2-104">Vorgehensweise: Behandeln von Ausnahmen in parallelen Schleifen</span><span class="sxs-lookup"><span data-stu-id="459c2-104">How to: Handle Exceptions in Parallel Loops</span></span>
<span data-ttu-id="459c2-105">Die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>- und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Überladungen verfügen über keinen speziellen Mechanismus zur Behandlung von Ausnahmen, die möglicherweise ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="459c2-105">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="459c2-106">In dieser Hinsicht ähneln sie herkömmlichen `for`- und `foreach`-Schleifen (`For` und `For Each` in Visual Basic). Eine nicht behandelte Ausnahme bewirkt, dass die Schleife sofort beendet wird, sobald alle momentan laufenden Iterationen abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="459c2-106">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate as soon as all currently running iterations finish.</span></span>
  
 <span data-ttu-id="459c2-107">Wenn Sie Parallelschleifen eigene Logik zur Ausnahmebehandlung hinzufügen, behandeln Sie den Fall, in dem ähnliche Ausnahmen in mehreren Threads gleichzeitig ausgelöst werden können, sowie den Fall, in dem eine in einem Thread ausgelöste Ausnahme bewirkt, dass eine andere Ausnahme in einem anderen Thread ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="459c2-107">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="459c2-108">Sie können beide Fälle behandeln, indem Sie alle Ausnahmen der Schleife in einer <xref:System.AggregateException?displayProperty=nameWithType> umschließen.</span><span class="sxs-lookup"><span data-stu-id="459c2-108">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="459c2-109">Im folgenden Beispiel wird ein möglicher Ansatz gezeigt.</span><span class="sxs-lookup"><span data-stu-id="459c2-109">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="459c2-110">Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="459c2-110">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="459c2-111">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="459c2-111">This error is benign.</span></span> <span data-ttu-id="459c2-112">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das im nachstehenden Beispiel veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="459c2-112">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="459c2-113">Um zu verhindern, dass Visual Studio beim ersten Fehler abbricht, deaktivieren Sie einfach unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.</span><span class="sxs-lookup"><span data-stu-id="459c2-113">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="459c2-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="459c2-114">Example</span></span>  
 <span data-ttu-id="459c2-115">In diesem Beispiel werden alle Ausnahmen abgefangen und dann in einer <xref:System.AggregateException?displayProperty=nameWithType> umschlossen, die ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="459c2-115">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="459c2-116">Der Aufrufer kann entscheiden, welche Ausnahmen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="459c2-116">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="459c2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="459c2-117">See also</span></span>

- [<span data-ttu-id="459c2-118">Datenparallelität</span><span class="sxs-lookup"><span data-stu-id="459c2-118">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="459c2-119">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="459c2-119">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
