---
title: 'Vorgehensweise: Ausführen von Bereinigungscode mit finally (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Bereinigungscode mit einer finally-Anweisung ausführen. Mit finally-Anweisungen wird sichergestellt, dass alle notwendigen Bereinigungsvorgänge für Objekte sofort ausgeführt werden.
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 283c36ab9b976a92e339000a982340148c2480a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178644"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="ca4af-104">Vorgehensweise: Ausführen von Bereinigungscode mit finally (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="ca4af-104">How to execute cleanup code using finally (C# Programming Guide)</span></span>

<span data-ttu-id="ca4af-105">`finally`-Anweisungen sollen sicherstellen, dass die notwendige Bereinigung von Objekten, die externe Ressourcen enthalten, sofort erfolgen, auch wenn eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="ca4af-105">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="ca4af-106">Ein Beispiel für eine solche Bereinigung ist der Aufruf von <xref:System.IO.Stream.Close%2A> auf einem <xref:System.IO.FileStream> sofort nach der Verwendung, anstatt abzuwarten, bis das Objekt durch die Common Language Runtime wie folgt speicherbereinigt wird:</span><span class="sxs-lookup"><span data-stu-id="ca4af-106">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#16)]  
  
## <a name="example"></a><span data-ttu-id="ca4af-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca4af-107">Example</span></span>  

 <span data-ttu-id="ca4af-108">Um den vorherigen Code in eine `try-catch-finally`-Anweisung umzuwandeln, wird der Bereinigungscode wie folgt vom Arbeitscode getrennt.</span><span class="sxs-lookup"><span data-stu-id="ca4af-108">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#17)]  
  
 <span data-ttu-id="ca4af-109">Da eine Ausnahme zu einem beliebigen Zeitpunkt innerhalb des `try`-Blocks vor dem `OpenWrite()`-Aufruf auftreten oder der `OpenWrite()`-Aufruf selbst fehlschlagen kann, ist nicht garantiert, dass die Datei geöffnet ist, wenn wir versuchen, sie zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ca4af-109">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="ca4af-110">Der `finally`-Block fügt eine Prüfung hinzu, um sicherzustellen, dass das <xref:System.IO.FileStream>-Objekt nicht `null` ist, bevor Sie die <xref:System.IO.Stream.Close%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ca4af-110">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="ca4af-111">Ohne die `null`-Prüfung kann der `finally`-Block kann eine eigene <xref:System.NullReferenceException>-Ausnahme auslösen. Das Auslösen von Ausnahmen in `finally`-Blöcken sollte allerdings, wenn möglich, vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="ca4af-111">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="ca4af-112">Auch Datenbankverbindungen können mit einem `finally`-Block geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="ca4af-112">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="ca4af-113">Da die Anzahl der zulässigen Verbindungen mit einem Datenbankserver manchmal begrenzt ist, sollten Sie Datenbankverbindungen so schnell wie möglich schließen.</span><span class="sxs-lookup"><span data-stu-id="ca4af-113">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="ca4af-114">Wenn eine Ausnahme ausgelöst wird, bevor Sie die Verbindung schließen können, ist es besser, den `finally`-Block zu verwenden, als die Speicherbereinigung abzuwarten.</span><span class="sxs-lookup"><span data-stu-id="ca4af-114">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca4af-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca4af-115">See also</span></span>

- [<span data-ttu-id="ca4af-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ca4af-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ca4af-117">Ausnahmen und Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="ca4af-117">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="ca4af-118">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="ca4af-118">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="ca4af-119">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ca4af-119">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
- [<span data-ttu-id="ca4af-120">try-catch</span><span class="sxs-lookup"><span data-stu-id="ca4af-120">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="ca4af-121">try-finally</span><span class="sxs-lookup"><span data-stu-id="ca4af-121">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="ca4af-122">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="ca4af-122">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
