---
title: 'Gewusst wie: Verwenden des Try-Catch-Blocks zum Abfangen von Ausnahmen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 852df5cb3eeea2ee5fa44ddce2f97e9c4f8d8b5a
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842384"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>Verwenden des try/catch-Blocks zum Abfangen von Ausnahmen

Platzieren Sie die Codeabschnitte, die möglicherweise Ausnahmen auslösen, in einem `try`-Block, und platzieren Sie den Code, der die Ausnahmen behandelt, in einem `catch`-Block. Der `catch`-Block ist eine Reihe von Anweisungen, der mit dem Schlüsselwort `catch` beginnt, gefolgt von einem Ausnahmetyp und einer auszuführenden Aktion.

Das folgende Codebeispiel verwendet einen `try`/`catch`-Block, um eine mögliche Ausnahme abzufangen. Die `Main`-Methode enthält einen `try`-Block mit einer <xref:System.IO.StreamReader>-Anweisung, die eine Datei namens `data.txt` öffnet und eine Zeichenfolge aus der Datei schreibt. Dem `try`-Block folgt ein `catch`-Block, der alle Ausnahmen abfängt, die aus dem `try`-Block resultieren.

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

Die Common Language Runtime fängt Ausnahmen ab, die nicht von einem catch-Block abgefangen werden. Je nach Konfiguration der Runtime wird ein Dialogfeld zum Debuggen angezeigt, oder das Programm beendet die Ausführung und zeigt ein Dialogfeld mit Informationen zur Ausnahme an, oder es wird ein Fehler an STDERR ausgegeben.

> [!NOTE] 
> Nahezu jede Codezeile kann eine Ausnahme verursachen, insbesondere Ausnahmen, die von der Common Language Runtime selbst ausgelöst werden, wie z.B. eine <xref:System.OutOfMemoryException>. Die meisten Anwendungen müssen diese Ausnahmen nicht behandeln, beim Schreiben von Bibliotheken, die von anderen Anwendungen verwendet werden sollen, sollte diese Möglichkeit allerdings berücksichtigen werden. Vorschläge dazu, wann Sie Code in einen try-Block platzieren sollten, finden Sie unter [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md).

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
