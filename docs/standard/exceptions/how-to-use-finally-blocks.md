---
title: 'Vorgehensweise: Verwenden von finally-Blöcken'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
ms.openlocfilehash: 44fbb53437c4c8f19a424227a167e2e268b77057
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708831"
---
# <a name="how-to-use-finally-blocks"></a><span data-ttu-id="94957-102">Verwenden von finally-Blöcken</span><span class="sxs-lookup"><span data-stu-id="94957-102">How to use finally blocks</span></span>

<span data-ttu-id="94957-103">Wenn eine Ausnahme auftritt, wird die Ausführung beendet und die Steuerung an den entsprechenden Ausnahmehandler übergeben.</span><span class="sxs-lookup"><span data-stu-id="94957-103">When an exception occurs, execution stops and control is given to the appropriate exception handler.</span></span> <span data-ttu-id="94957-104">Dies bedeutet häufig, dass Codezeilen umgangen werden, die eigentlich ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="94957-104">This often means that lines of code you expect to be executed are bypassed.</span></span> <span data-ttu-id="94957-105">Daher muss auch nach Auslösen einer Ausnahme eine Ressourcenbereinigung durchgeführt werden, z.B. das Schließen einer Datei.</span><span class="sxs-lookup"><span data-stu-id="94957-105">Some resource cleanup, such as closing a file, needs to be done even if an exception is thrown.</span></span> <span data-ttu-id="94957-106">Zu diesem Zweck können Sie einen `finally`-Block verwenden.</span><span class="sxs-lookup"><span data-stu-id="94957-106">To do this, you can use a `finally` block.</span></span> <span data-ttu-id="94957-107">Ein `finally`-Block wird immer ausgeführt, unabhängig davon, ob eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="94957-107">A `finally` block always executes, regardless of whether an exception is thrown.</span></span>

<span data-ttu-id="94957-108">Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine <xref:System.ArgumentOutOfRangeException> abzufangen.</span><span class="sxs-lookup"><span data-stu-id="94957-108">The following code example uses a `try`/`catch` block to catch an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="94957-109">Die `Main`-Methode erstellt zwei Arrays und versucht, das eine Array in das andere zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="94957-109">The `Main` method creates two arrays and attempts to copy one to the other.</span></span> <span data-ttu-id="94957-110">Die Aktion generiert eine <xref:System.ArgumentOutOfRangeException>, und der Fehler wird an die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="94957-110">The action generates an <xref:System.ArgumentOutOfRangeException> and the error is written to the console.</span></span> <span data-ttu-id="94957-111">Der `finally`-Block wird unabhängig vom Ergebnis des Kopiervorgangs ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="94957-111">The `finally` block executes regardless of the outcome of the copy action.</span></span>

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="94957-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94957-112">See also</span></span>

- [<span data-ttu-id="94957-113">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="94957-113">Exceptions</span></span>](index.md)
