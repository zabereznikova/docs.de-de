---
title: 'Vorgehensweise: Explizites Auslösen von Ausnahmen'
description: Informationen zum expliziten Auslösen von Ausnahmen in .NET mithilfe der Throw-Anweisung in C# oder Visual Basic
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
ms.openlocfilehash: 2dd939f9edd58ba91ea74df5d6930087849f0560
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662783"
---
# <a name="how-to-explicitly-throw-exceptions"></a>Explizites Auslösen von Ausnahmen

Sie können mithilfe der C#-Anweisung [`throw`](../../csharp/language-reference/keywords/throw.md) oder der Visual Basic-Anweisung [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) eine Ausnahme explizit auslösen. Mit der `throw`-Anweisung können Sie auch eine abgefangene Ausnahme erneut auslösen. Es ist sinnvoll, einer Ausnahme, die erneut ausgelöst wird, weitere Informationen hinzuzufügen, um das Debuggen zu vereinfachen.

Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine <xref:System.IO.FileNotFoundException> abzufangen. Auf den `try`-Block folgt ein `catch`-Block, der die <xref:System.IO.FileNotFoundException> abfängt und eine Meldung an die Konsole schreibt, wenn die Datendatei nicht gefunden wird. Die nächste Anweisung ist die `throw`-Anweisung, die eine neue <xref:System.IO.FileNotFoundException> auslöst und der Ausnahme Textinformationen hinzufügt.

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
