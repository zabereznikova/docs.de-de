---
title: "Gewusst wie: Ausführen von Bereinigungscode mit finally (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
caps.latest.revision: 21
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
ms.openlocfilehash: b1f7bccacf20a9322f4de75740cdc34b4a97fa4c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="56703-102">Gewusst wie: Ausführen von Bereinigungscode mit finally (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="56703-102">How to: Execute Cleanup Code Using finally (C# Programming Guide)</span></span>
<span data-ttu-id="56703-103">`finally`-Anweisungen sollen sicherstellen, dass die notwendige Bereinigung von Objekten, die externe Ressourcen enthalten, sofort erfolgen, auch wenn eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="56703-103">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="56703-104">Ein Beispiel für eine solche Bereinigung ist der Aufruf von <xref:System.IO.Stream.Close%2A> auf einem <xref:System.IO.FileStream> sofort nach der Verwendung, anstatt abzuwarten, bis das Objekt durch die Common Language Runtime wie folgt speicherbereinigt wird:</span><span class="sxs-lookup"><span data-stu-id="56703-104">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 <span data-ttu-id="56703-105">[!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="56703-105">[!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="56703-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56703-106">Example</span></span>  
 <span data-ttu-id="56703-107">Um den vorherigen Code in eine `try-catch-finally`-Anweisung umzuwandeln, wird der Bereinigungscode wie folgt vom Arbeitscode getrennt.</span><span class="sxs-lookup"><span data-stu-id="56703-107">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 <span data-ttu-id="56703-108">[!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="56703-108">[!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]</span></span>  
  
 <span data-ttu-id="56703-109">Da eine Ausnahme zu einem beliebigen Zeitpunkt innerhalb des `try`-Blocks vor dem `OpenWrite()`-Aufruf auftreten oder der `OpenWrite()`-Aufruf selbst fehlschlagen kann, ist nicht garantiert, dass die Datei geöffnet ist, wenn wir versuchen, sie zu schließen.</span><span class="sxs-lookup"><span data-stu-id="56703-109">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="56703-110">Der `finally`-Block fügt eine Prüfung hinzu, um sicherzustellen, dass das <xref:System.IO.FileStream>-Objekt nicht `null` ist, bevor Sie die <xref:System.IO.Stream.Close%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="56703-110">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="56703-111">Ohne die `null`-Prüfung kann der `finally`-Block kann eine eigene <xref:System.NullReferenceException>-Ausnahme auslösen. Das Auslösen von Ausnahmen in `finally`-Blöcken sollte allerdings, wenn möglich, vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="56703-111">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="56703-112">Auch Datenbankverbindungen können mit einem `finally`-Block geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="56703-112">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="56703-113">Da die Anzahl der zulässigen Verbindungen mit einem Datenbankserver manchmal begrenzt ist, sollten Sie Datenbankverbindungen so schnell wie möglich schließen.</span><span class="sxs-lookup"><span data-stu-id="56703-113">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="56703-114">Wenn eine Ausnahme ausgelöst wird, bevor Sie die Verbindung schließen können, ist es besser, den `finally`-Block zu verwenden, als die Speicherbereinigung abzuwarten.</span><span class="sxs-lookup"><span data-stu-id="56703-114">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56703-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56703-115">See Also</span></span>  
 <span data-ttu-id="56703-116">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="56703-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="56703-117">[Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="56703-117">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="56703-118">[Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md) </span><span class="sxs-lookup"><span data-stu-id="56703-118">[Exception Handling](../../../csharp/programming-guide/exceptions/exception-handling.md) </span></span>  
 <span data-ttu-id="56703-119">[using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="56703-119">[using Statement](../../../csharp/language-reference/keywords/using-statement.md) </span></span>  
 <span data-ttu-id="56703-120">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="56703-120">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="56703-121">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="56703-121">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 [<span data-ttu-id="56703-122">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="56703-122">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)

