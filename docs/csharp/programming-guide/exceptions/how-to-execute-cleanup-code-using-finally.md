---
title: 'Vorgehensweise: Ausführen von Bereinigungscode mit finally (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Bereinigungscode mit einer finally-Anweisung ausführen. Mit finally-Anweisungen wird sichergestellt, dass alle notwendigen Bereinigungsvorgänge für Objekte sofort ausgeführt werden.
ms.date: 12/09/2020
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: e9b5d3086488d3f7e3c0709317d6fafd15c439e8
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110181"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="c9f61-104">Vorgehensweise: Ausführen von Bereinigungscode mit finally (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="c9f61-104">How to execute cleanup code using finally (C# Programming Guide)</span></span>

<span data-ttu-id="c9f61-105">`finally`-Anweisungen sollen sicherstellen, dass die notwendige Bereinigung von Objekten, die externe Ressourcen enthalten, sofort erfolgen, auch wenn eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c9f61-105">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="c9f61-106">Ein Beispiel für eine solche Bereinigung ist der Aufruf von <xref:System.IO.Stream.Close%2A> auf einem <xref:System.IO.FileStream> sofort nach der Verwendung, anstatt abzuwarten, bis das Objekt durch die Common Language Runtime wie folgt speicherbereinigt wird:</span><span class="sxs-lookup"><span data-stu-id="c9f61-106">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="NoCleanup":::

## <a name="example"></a><span data-ttu-id="c9f61-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9f61-107">Example</span></span>

<span data-ttu-id="c9f61-108">Um den vorherigen Code in eine `try-catch-finally`-Anweisung umzuwandeln, wird der Bereinigungscode wie folgt vom Arbeitscode getrennt.</span><span class="sxs-lookup"><span data-stu-id="c9f61-108">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="WithCleanup":::

<span data-ttu-id="c9f61-109">Da eine Ausnahme zu einem beliebigen Zeitpunkt innerhalb des `try`-Blocks vor dem `OpenWrite()`-Aufruf auftreten oder der `OpenWrite()`-Aufruf selbst fehlschlagen kann, ist nicht garantiert, dass die Datei geöffnet ist, wenn wir versuchen, sie zu schließen.</span><span class="sxs-lookup"><span data-stu-id="c9f61-109">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we aren't guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="c9f61-110">Der `finally`-Block fügt eine Überprüfung hinzu, um sicherzustellen, dass das <xref:System.IO.FileStream>-Objekt nicht `null` ist, bevor Sie die <xref:System.IO.Stream.Close%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c9f61-110">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object isn't `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="c9f61-111">Ohne die `null`-Überprüfung kann der `finally`-Block eine eigene <xref:System.NullReferenceException>-Ausnahme auslösen. Das Auslösen von Ausnahmen in `finally`-Blöcken sollte allerdings nach Möglichkeit vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="c9f61-111">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it's possible.</span></span>

<span data-ttu-id="c9f61-112">Auch Datenbankverbindungen können mit einem `finally`-Block geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c9f61-112">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="c9f61-113">Da die Anzahl der zulässigen Verbindungen mit einem Datenbankserver manchmal begrenzt ist, sollten Sie Datenbankverbindungen so schnell wie möglich schließen.</span><span class="sxs-lookup"><span data-stu-id="c9f61-113">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="c9f61-114">Wenn eine Ausnahme ausgelöst wird, bevor Sie die Verbindung beenden können, ist es besser, den `finally`-Block zu verwenden, anstatt auf due automatische Speicherbereinigung zu warten.</span><span class="sxs-lookup"><span data-stu-id="c9f61-114">If an exception is thrown before you can close your connection, using the `finally` block is better than waiting for garbage collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9f61-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9f61-115">See also</span></span>

- [<span data-ttu-id="c9f61-116">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c9f61-116">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
- [<span data-ttu-id="c9f61-117">try-catch</span><span class="sxs-lookup"><span data-stu-id="c9f61-117">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="c9f61-118">try-finally</span><span class="sxs-lookup"><span data-stu-id="c9f61-118">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="c9f61-119">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="c9f61-119">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
