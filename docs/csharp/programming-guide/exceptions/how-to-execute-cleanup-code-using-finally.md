---
title: 'Gewusst wie: Ausführen von Bereinigungscode mit finally (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 948281af45d04714ed6fc308b60341e87abeb830
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="1af4c-102">Gewusst wie: Ausführen von Bereinigungscode mit finally (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="1af4c-102">How to: Execute Cleanup Code Using finally (C# Programming Guide)</span></span>
<span data-ttu-id="1af4c-103">`finally`-Anweisungen sollen sicherstellen, dass die notwendige Bereinigung von Objekten, die externe Ressourcen enthalten, sofort erfolgen, auch wenn eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1af4c-103">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="1af4c-104">Ein Beispiel für eine solche Bereinigung ist der Aufruf von <xref:System.IO.Stream.Close%2A> auf einem <xref:System.IO.FileStream> sofort nach der Verwendung, anstatt abzuwarten, bis das Objekt durch die Common Language Runtime wie folgt speicherbereinigt wird:</span><span class="sxs-lookup"><span data-stu-id="1af4c-104">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="1af4c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1af4c-105">Example</span></span>  
 <span data-ttu-id="1af4c-106">Um den vorherigen Code in eine `try-catch-finally`-Anweisung umzuwandeln, wird der Bereinigungscode wie folgt vom Arbeitscode getrennt.</span><span class="sxs-lookup"><span data-stu-id="1af4c-106">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]  
  
 <span data-ttu-id="1af4c-107">Da eine Ausnahme zu einem beliebigen Zeitpunkt innerhalb des `try`-Blocks vor dem `OpenWrite()`-Aufruf auftreten oder der `OpenWrite()`-Aufruf selbst fehlschlagen kann, ist nicht garantiert, dass die Datei geöffnet ist, wenn wir versuchen, sie zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1af4c-107">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="1af4c-108">Der `finally`-Block fügt eine Prüfung hinzu, um sicherzustellen, dass das <xref:System.IO.FileStream>-Objekt nicht `null` ist, bevor Sie die <xref:System.IO.Stream.Close%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1af4c-108">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="1af4c-109">Ohne die `null`-Prüfung kann der `finally`-Block kann eine eigene <xref:System.NullReferenceException>-Ausnahme auslösen. Das Auslösen von Ausnahmen in `finally`-Blöcken sollte allerdings, wenn möglich, vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="1af4c-109">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="1af4c-110">Auch Datenbankverbindungen können mit einem `finally`-Block geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1af4c-110">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="1af4c-111">Da die Anzahl der zulässigen Verbindungen mit einem Datenbankserver manchmal begrenzt ist, sollten Sie Datenbankverbindungen so schnell wie möglich schließen.</span><span class="sxs-lookup"><span data-stu-id="1af4c-111">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="1af4c-112">Wenn eine Ausnahme ausgelöst wird, bevor Sie die Verbindung schließen können, ist es besser, den `finally`-Block zu verwenden, als die Speicherbereinigung abzuwarten.</span><span class="sxs-lookup"><span data-stu-id="1af4c-112">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af4c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1af4c-113">See Also</span></span>  
 [<span data-ttu-id="1af4c-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1af4c-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1af4c-115">Ausnahmen und Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="1af4c-115">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)  
 [<span data-ttu-id="1af4c-116">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="1af4c-116">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)  
 [<span data-ttu-id="1af4c-117">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1af4c-117">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)  
 [<span data-ttu-id="1af4c-118">try-catch</span><span class="sxs-lookup"><span data-stu-id="1af4c-118">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="1af4c-119">try-finally</span><span class="sxs-lookup"><span data-stu-id="1af4c-119">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)  
 [<span data-ttu-id="1af4c-120">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="1af4c-120">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)
