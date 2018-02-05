---
title: "Gewusst wie: Explizites Auslösen von Ausnahmen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 02576db4b9920a367ac3111f2c2c49989ea45149
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="3b7c7-102">Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="3b7c7-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="3b7c7-103">Sie können mithilfe der `throw`-Anweisung eine Ausnahme explizit auslösen.</span><span class="sxs-lookup"><span data-stu-id="3b7c7-103">You can explicitly throw an exception using the `throw` statement.</span></span> <span data-ttu-id="3b7c7-104">Mit der `throw`-Anweisung können Sie auch eine abgefangene Ausnahme erneut auslösen.</span><span class="sxs-lookup"><span data-stu-id="3b7c7-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="3b7c7-105">Es ist sinnvoll, einer Ausnahme, die erneut ausgelöst wird, weitere Informationen hinzuzufügen, um das Debuggen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="3b7c7-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="3b7c7-106">Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine <xref:System.IO.FileNotFoundException> abzufangen.</span><span class="sxs-lookup"><span data-stu-id="3b7c7-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="3b7c7-107">Auf den `try`-Block folgt ein `catch`-Block, der die <xref:System.IO.FileNotFoundException> abfängt und eine Meldung an die Konsole schreibt, wenn die Datendatei nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3b7c7-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="3b7c7-108">Die nächste Anweisung ist die `throw`-Anweisung, die eine neue <xref:System.IO.FileNotFoundException> auslöst und der Ausnahme Textinformationen hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="3b7c7-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="3b7c7-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b7c7-109">See Also</span></span>  
[<span data-ttu-id="3b7c7-110">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="3b7c7-110">Exceptions</span></span>](index.md)
