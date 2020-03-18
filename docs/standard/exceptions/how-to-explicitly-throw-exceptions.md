---
title: 'Gewusst wie: Explizites Auslösen von Ausnahmen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
ms.openlocfilehash: 750da20b8c1c40901cc363ac0eff8af888821ce9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708861"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="52b4a-102">Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="52b4a-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="52b4a-103">Sie können mithilfe der C#-Anweisung [`throw`](../../csharp/language-reference/keywords/throw.md) oder der Visual Basic-Anweisung [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) eine Ausnahme explizit auslösen.</span><span class="sxs-lookup"><span data-stu-id="52b4a-103">You can explicitly throw an exception using the C# [`throw`](../../csharp/language-reference/keywords/throw.md) or the Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) statement.</span></span> <span data-ttu-id="52b4a-104">Mit der `throw`-Anweisung können Sie auch eine abgefangene Ausnahme erneut auslösen.</span><span class="sxs-lookup"><span data-stu-id="52b4a-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="52b4a-105">Es ist sinnvoll, einer Ausnahme, die erneut ausgelöst wird, weitere Informationen hinzuzufügen, um das Debuggen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="52b4a-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="52b4a-106">Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine <xref:System.IO.FileNotFoundException> abzufangen.</span><span class="sxs-lookup"><span data-stu-id="52b4a-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="52b4a-107">Auf den `try`-Block folgt ein `catch`-Block, der die <xref:System.IO.FileNotFoundException> abfängt und eine Meldung an die Konsole schreibt, wenn die Datendatei nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="52b4a-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="52b4a-108">Die nächste Anweisung ist die `throw`-Anweisung, die eine neue <xref:System.IO.FileNotFoundException> auslöst und der Ausnahme Textinformationen hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="52b4a-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="52b4a-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52b4a-109">See also</span></span>

- [<span data-ttu-id="52b4a-110">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="52b4a-110">Exceptions</span></span>](index.md)
