---
title: 'Vorgehensweise: Verwenden des Try-Catch-Blocks zum Abfangen von Ausnahmen'
description: Schließen Sie Anweisungen in den try-Block ein, die möglicherweise eine Ausnahme auslösen. Verwenden Sie Anweisungen zum Verarbeiten von Ausnahmen in einem oder mehreren catch-Blöcken.
ms.date: 02/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: cfe5b2b304cdb9efe7f0d91059fe1c279b4fa2dd
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828009"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>Verwenden des try/catch-Blocks zum Abfangen von Ausnahmen

Platzieren Sie alle Codeanweisungen, die zu einer Ausnahme führen könnten in einen `try`-Block, und platzieren Sie Anweisungen, die für Ausnahmen verwendet werden oder die Ausnahmen selbst in einen oder mehrere `catch`-Blöcke unterhalb des `try`-Blocks. Jeder `catch`-Block beinhaltet den Ausnahmetyp und kann zusätzliche Anweisungen beinhalten, die für diesen Ausnahmetyp benötigt werden.

Im folgenden Beispiel öffnet ein <xref:System.IO.StreamReader> eine Datei namens *data.txt* und ruft eine Zeile daraus ab. Da der Code möglicherweise eine der drei Ausnahmen auslöst, wird er in einen `try`-Block platziert. Drei `catch`-Blöcke fangen die Ausnahmen ab und verarbeiten sie, indem sie die Ergebnisse in der Konsole anzeigen.

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

Die Common Language Runtime (CLR) fängt Ausnahmen ab, die nicht von den `catch`-Blöcken verarbeitet wurden. Wenn eine Ausnahme von einer CLR abgefangen wird, führt dies zu einem der folgenden möglichen Ergebnisse, je nachdem, wie die CLR konfiguriert wurde:

- Ein Dialogfeld **Debuggen** wird angezeigt.
- Das Programm beendet die Ausführung, und ein Dialogfeld mit Informationen über die Ausnahme wird angezeigt.
- Im [Standardausgabestream für Fehler](xref:System.Console.Error) wird ein Fehler ausgegeben.

> [!NOTE]
> Die meisten Codes können eine Ausnahme auslösen, und einige Ausnahmen, z.B. <xref:System.OutOfMemoryException>, können auch jederzeit von der CRL selbst ausgelöst werden. Während Anwendungen diese Ausnahmen nicht behandeln müssen, sollte diese Möglichkeit beim Schreiben von Bibliotheken, die von anderen Anwendungen verwendet werden sollen, allerdings berücksichtigen werden. Vorschläge dazu, wann Sie Code in einen`try` -Block platzieren sollten, finden Sie unter [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md).

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
- [Behandeln von E/A-Fehlern in .NET](../io/handling-io-errors.md)
