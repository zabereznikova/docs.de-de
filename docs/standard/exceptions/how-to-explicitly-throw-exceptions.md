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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a71cefc0a6483dbbe6513a64d8111a07a2e5af42
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696738"
---
# <a name="how-to-explicitly-throw-exceptions"></a>Explizites Auslösen von Ausnahmen

Sie können mithilfe der C#-Anweisung [`throw`](../../csharp/language-reference/keywords/throw.md) oder der Visual Basic-Anweisung [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) eine Ausnahme explizit auslösen. Mit der `throw`-Anweisung können Sie auch eine abgefangene Ausnahme erneut auslösen. Es ist sinnvoll, einer Ausnahme, die erneut ausgelöst wird, weitere Informationen hinzuzufügen, um das Debuggen zu vereinfachen.

Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine <xref:System.IO.FileNotFoundException> abzufangen. Auf den `try`-Block folgt ein `catch`-Block, der die <xref:System.IO.FileNotFoundException> abfängt und eine Meldung an die Konsole schreibt, wenn die Datendatei nicht gefunden wird. Die nächste Anweisung ist die `throw`-Anweisung, die eine neue <xref:System.IO.FileNotFoundException> auslöst und der Ausnahme Textinformationen hinzufügt.

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
