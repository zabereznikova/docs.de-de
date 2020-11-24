---
title: 'Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch-Block'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
ms.openlocfilehash: bf4813e950b034cb807abebfe016c1e34487d594
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828022"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a><span data-ttu-id="daf2e-102">Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch-Block</span><span class="sxs-lookup"><span data-stu-id="daf2e-102">How to use specific exceptions in a catch block</span></span>

<span data-ttu-id="daf2e-103">Im Allgemeinen empfiehlt es sich beim Programmieren, einen bestimmten Ausnahmetyp abzufangen, anstatt eine grundlegende `catch`-Anweisung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="daf2e-103">In general, it's good programming practice to catch a specific type of exception rather than use a basic `catch` statement.</span></span>

<span data-ttu-id="daf2e-104">Wenn eine Ausnahme auftritt, wird sie von unten nach oben durch den Stapel übergeben, und jeder Block erhält die Möglichkeit, sie zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="daf2e-104">When an exception occurs, it is passed up the stack and each catch block is given the opportunity to handle it.</span></span> <span data-ttu-id="daf2e-105">Die Reihenfolge der catch-Anweisungen ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="daf2e-105">The order of catch statements is important.</span></span> <span data-ttu-id="daf2e-106">Platzieren Sie catch-Blöcke für bestimmte Ausnahmen vor einen allgemeinen Block zum Abfangen von Ausnahmen. Andernfalls gibt der Compiler möglicherweise einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="daf2e-106">Put catch blocks targeted to specific exceptions before a general exception catch block or the compiler might issue an error.</span></span> <span data-ttu-id="daf2e-107">Der richtige catch-Block wird ermitteln, indem der Typ der Ausnahme mit dem Namen der im catch-Block angegebenen Ausnahme abgeglichen wird.</span><span class="sxs-lookup"><span data-stu-id="daf2e-107">The proper catch block is determined by matching the type of the exception to the name of the exception specified in the catch block.</span></span> <span data-ttu-id="daf2e-108">Wenn kein bestimmter catch-Block vorhanden ist, wird die Ausnahme durch einen allgemeinen catch-Block abgefangen, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="daf2e-108">If there is no specific catch block, the exception is caught by a general catch block, if one exists.</span></span>

<span data-ttu-id="daf2e-109">Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine <xref:System.InvalidCastException> abzufangen.</span><span class="sxs-lookup"><span data-stu-id="daf2e-109">The following code example uses a `try`/`catch` block to catch an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="daf2e-110">Das Beispiel erstellt eine Klasse namens `Employee` mit einer einzigen Eigenschaft für die Mitarbeiterstufe („employee level“, `Emlevel`).</span><span class="sxs-lookup"><span data-stu-id="daf2e-110">The sample creates a class called `Employee` with a single property, employee level (`Emlevel`).</span></span> <span data-ttu-id="daf2e-111">Eine Methode, `PromoteEmployee`, übernimmt ein Objekt und erhöht die Mitarbeiterstufe.</span><span class="sxs-lookup"><span data-stu-id="daf2e-111">A method, `PromoteEmployee`, takes an object and increments the employee level.</span></span> <span data-ttu-id="daf2e-112">Eine <xref:System.InvalidCastException> tritt auf, wenn eine <xref:System.DateTime>-Instanz an die `PromoteEmployee`-Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="daf2e-112">An <xref:System.InvalidCastException> occurs when a <xref:System.DateTime> instance is passed to the `PromoteEmployee` method.</span></span>

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="daf2e-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="daf2e-113">See also</span></span>

- [<span data-ttu-id="daf2e-114">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="daf2e-114">Exceptions</span></span>](index.md)
