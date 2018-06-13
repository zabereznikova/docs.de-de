---
title: 'Gewusst wie: Verwenden des Try-Catch-Blocks zum Abfangen von Ausnahmen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b169353752f6e6483a056cdc9dd8c3227b9ebeb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571449"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="dbf9d-102">Verwenden des try/catch-Blocks zum Abfangen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="dbf9d-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="dbf9d-103">Platzieren Sie die Codeabschnitte, die möglicherweise Ausnahmen auslösen, in einem `try`-Block, und platzieren Sie den Code, der die Ausnahmen behandelt, in einem `catch`-Block.</span><span class="sxs-lookup"><span data-stu-id="dbf9d-103">Place the sections of code that might throw exceptions in a `try` block and place code that handles exceptions in a `catch` block.</span></span> <span data-ttu-id="dbf9d-104">Der `catch`-Block ist eine Reihe von Anweisungen, der mit dem Schlüsselwort `catch` beginnt, gefolgt von einem Ausnahmetyp und einer auszuführenden Aktion.</span><span class="sxs-lookup"><span data-stu-id="dbf9d-104">The `catch` block is a series of statements beginning with the keyword `catch`, followed by an exception type and an action to be taken.</span></span>

<span data-ttu-id="dbf9d-105">Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine mögliche Ausnahme abzufangen.</span><span class="sxs-lookup"><span data-stu-id="dbf9d-105">The following code example uses a `try`/`catch` block to catch a possible exception.</span></span> <span data-ttu-id="dbf9d-106">Die `Main`-Methode enthält einen `try`-Block mit einer <xref:System.IO.StreamReader>-Anweisung, die eine Datei namens `data.txt` öffnet und eine Zeichenfolge aus der Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="dbf9d-106">The `Main` method contains a `try` block with a <xref:System.IO.StreamReader> statement that opens a data file called `data.txt` and writes a string from the file.</span></span> <span data-ttu-id="dbf9d-107">Dem `try`-Block folgt ein `catch`-Block, der alle Ausnahmen abfängt, die aus dem `try`-Block resultieren.</span><span class="sxs-lookup"><span data-stu-id="dbf9d-107">Following the `try` block is a `catch` block that catches any exception that results from the `try` block.</span></span>

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

<span data-ttu-id="dbf9d-108">Die Common Language Runtime fängt Ausnahmen ab, die nicht von einem catch-Block abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="dbf9d-108">The common language runtime catches exceptions that are not caught by a catch block.</span></span> <span data-ttu-id="dbf9d-109">Je nach Konfiguration der Runtime wird ein Dialogfeld zum Debuggen angezeigt, oder das Programm beendet die Ausführung und zeigt ein Dialogfeld mit Informationen zur Ausnahme an, oder es wird ein Fehler an STDERR ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="dbf9d-109">Depending on how the runtime is configured, a debug dialog box appears, or the program stops executing and a dialog box with exception information appears, or an error is printed out to STDERR.</span></span>

> [!NOTE] 
> <span data-ttu-id="dbf9d-110">Nahezu jede Codezeile kann eine Ausnahme verursachen, insbesondere Ausnahmen, die von der Common Language Runtime selbst ausgelöst werden, wie z.B. eine <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="dbf9d-110">Almost any line of code can cause an exception, particularly exceptions that are thrown by the common language runtime itself, such as <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="dbf9d-111">Die meisten Anwendungen müssen diese Ausnahmen nicht behandeln, beim Schreiben von Bibliotheken, die von anderen Anwendungen verwendet werden sollen, sollte diese Möglichkeit allerdings berücksichtigen werden.</span><span class="sxs-lookup"><span data-stu-id="dbf9d-111">Most applications don't have to deal with these exceptions, but you should be aware of this possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="dbf9d-112">Vorschläge dazu, wann Sie Code in einen try-Block platzieren sollten, finden Sie unter [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="dbf9d-112">For suggestions on when to set code in a Try block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dbf9d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbf9d-113">See Also</span></span>  
[<span data-ttu-id="dbf9d-114">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="dbf9d-114">Exceptions</span></span>](index.md)
