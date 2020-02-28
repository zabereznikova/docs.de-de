---
title: 'Vorgehensweise: Behandeln von Ausnahmen in parallelen Schleifen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
ms.openlocfilehash: 5d108937e6ab2483cd1633d4b398c1e250f5c098
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453012"
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="17333-102">Vorgehensweise: Behandeln von Ausnahmen in parallelen Schleifen</span><span class="sxs-lookup"><span data-stu-id="17333-102">How to: Handle Exceptions in Parallel Loops</span></span>
<span data-ttu-id="17333-103">Die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>- und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Überladungen verfügen über keinen speziellen Mechanismus zur Behandlung von Ausnahmen, die möglicherweise ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="17333-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="17333-104">In dieser Hinsicht ähneln sie herkömmlichen `for`- und `foreach`-Schleifen (`For` und `For Each` in Visual Basic). Eine nicht behandelte Ausnahme bewirkt, dass die Schleife sofort beendet wird, sobald alle momentan laufenden Iterationen abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="17333-104">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate as soon as all currently running iterations finish.</span></span>
  
 <span data-ttu-id="17333-105">Wenn Sie Parallelschleifen eigene Logik zur Ausnahmebehandlung hinzufügen, behandeln Sie den Fall, in dem ähnliche Ausnahmen in mehreren Threads gleichzeitig ausgelöst werden können, sowie den Fall, in dem eine in einem Thread ausgelöste Ausnahme bewirkt, dass eine andere Ausnahme in einem anderen Thread ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="17333-105">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="17333-106">Sie können beide Fälle behandeln, indem Sie alle Ausnahmen der Schleife in einer <xref:System.AggregateException?displayProperty=nameWithType> umschließen.</span><span class="sxs-lookup"><span data-stu-id="17333-106">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="17333-107">Im folgenden Beispiel wird ein möglicher Ansatz gezeigt.</span><span class="sxs-lookup"><span data-stu-id="17333-107">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17333-108">Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="17333-108">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="17333-109">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="17333-109">This error is benign.</span></span> <span data-ttu-id="17333-110">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das im nachstehenden Beispiel veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="17333-110">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="17333-111">Um zu verhindern, dass Visual Studio beim ersten Fehler abbricht, deaktivieren Sie einfach unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.</span><span class="sxs-lookup"><span data-stu-id="17333-111">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17333-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17333-112">Example</span></span>  
 <span data-ttu-id="17333-113">In diesem Beispiel werden alle Ausnahmen abgefangen und dann in einer <xref:System.AggregateException?displayProperty=nameWithType> umschlossen, die ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="17333-113">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="17333-114">Der Aufrufer kann entscheiden, welche Ausnahmen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="17333-114">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="17333-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17333-115">See also</span></span>

- [<span data-ttu-id="17333-116">Datenparallelität</span><span class="sxs-lookup"><span data-stu-id="17333-116">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="17333-117">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="17333-117">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
