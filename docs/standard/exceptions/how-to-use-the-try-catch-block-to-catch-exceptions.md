---
title: 'Gewusst wie: Verwenden des Try-Catch-Blocks zum Abfangen von Ausnahmen'
ms.date: 02/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: 5a9218d394b76e897f4263708a10f1bc895ad4e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708465"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="b5bf1-102">Verwenden des try/catch-Blocks zum Abfangen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b5bf1-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="b5bf1-103">Platzieren Sie alle Codeanweisungen, die zu einer Ausnahme führen könnten in einen `try`-Block, und platzieren Sie Anweisungen, die für Ausnahmen verwendet werden oder die Ausnahmen selbst in einen oder mehrere `catch`-Blöcke unterhalb des `try`-Blocks.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-103">Place any code statements that might raise or throw an exception in a `try` block, and place statements used to handle the exception or exceptions in one or more `catch` blocks below the `try` block.</span></span> <span data-ttu-id="b5bf1-104">Jeder `catch`-Block beinhaltet den Ausnahmetyp und kann zusätzliche Anweisungen beinhalten, die für diesen Ausnahmetyp benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-104">Each `catch` block includes the exception type and can contain additional statements needed to handle that exception type.</span></span>

<span data-ttu-id="b5bf1-105">Im folgenden Beispiel öffnet ein <xref:System.IO.StreamReader> eine Datei namens *data.txt* und ruft eine Zeile daraus ab.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-105">In the following example, a <xref:System.IO.StreamReader> opens a file called *data.txt* and retrieves a line from the file.</span></span> <span data-ttu-id="b5bf1-106">Da der Code möglicherweise eine der drei Ausnahmen auslöst, wird er in einen `try`-Block platziert.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-106">Since the code might throw any of three exceptions, it's placed in a `try` block.</span></span> <span data-ttu-id="b5bf1-107">Drei `catch`-Blöcke fangen die Ausnahmen ab und verarbeiten sie, indem sie die Ergebnisse in der Konsole anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-107">Three `catch` blocks catch the exceptions and handle them by displaying the results to the console.</span></span>

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

<span data-ttu-id="b5bf1-108">Die Common Language Runtime (CLR) fängt Ausnahmen ab, die nicht von den `catch`-Blöcken verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-108">The Common Language Runtime (CLR) catches exceptions not handled by `catch` blocks.</span></span> <span data-ttu-id="b5bf1-109">Wenn eine Ausnahme von einer CLR abgefangen wird, führt dies zu einem der folgenden möglichen Ergebnisse, je nachdem, wie die CLR konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="b5bf1-109">If an exception is caught by the CLR, one of the following results may occur depending on your CLR configuration:</span></span>

- <span data-ttu-id="b5bf1-110">Ein Dialogfeld **Debuggen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-110">A **Debug** dialog box appears.</span></span>
- <span data-ttu-id="b5bf1-111">Das Programm beendet die Ausführung, und ein Dialogfeld mit Informationen über die Ausnahme wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-111">The program stops execution and a dialog box with exception information appears.</span></span>
- <span data-ttu-id="b5bf1-112">Im [Standardausgabestream für Fehler](xref:System.Console.Error) wird ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-112">An error prints out to the [standard error output stream](xref:System.Console.Error).</span></span>

> [!NOTE]
> <span data-ttu-id="b5bf1-113">Die meisten Codes können eine Ausnahme auslösen, und einige Ausnahmen, z.B. <xref:System.OutOfMemoryException>, können auch jederzeit von der CRL selbst ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-113">Most code can throw an exception, and some exceptions, like <xref:System.OutOfMemoryException>, can be thrown by the CLR itself at any time.</span></span> <span data-ttu-id="b5bf1-114">Während Anwendungen diese Ausnahmen nicht behandeln müssen, sollte diese Möglichkeit beim Schreiben von Bibliotheken, die von anderen Anwendungen verwendet werden sollen, allerdings berücksichtigen werden.</span><span class="sxs-lookup"><span data-stu-id="b5bf1-114">While applications aren't required to deal with these exceptions, be aware of the possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="b5bf1-115">Vorschläge dazu, wann Sie Code in einen`try` -Block platzieren sollten, finden Sie unter [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="b5bf1-115">For suggestions on when to set code in a `try` block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5bf1-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5bf1-116">See also</span></span>

- [<span data-ttu-id="b5bf1-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b5bf1-117">Exceptions</span></span>](index.md)
- [<span data-ttu-id="b5bf1-118">Behandeln von E/A-Fehlern in .NET</span><span class="sxs-lookup"><span data-stu-id="b5bf1-118">Handling I/O errors in .NET</span></span>](../io/handling-io-errors.md)
