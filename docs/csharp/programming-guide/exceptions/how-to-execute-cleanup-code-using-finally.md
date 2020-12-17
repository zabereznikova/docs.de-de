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
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a>Vorgehensweise: Ausführen von Bereinigungscode mit finally (C#-Programmierleitfaden)

`finally`-Anweisungen sollen sicherstellen, dass die notwendige Bereinigung von Objekten, die externe Ressourcen enthalten, sofort erfolgen, auch wenn eine Ausnahme ausgelöst wird. Ein Beispiel für eine solche Bereinigung ist der Aufruf von <xref:System.IO.Stream.Close%2A> auf einem <xref:System.IO.FileStream> sofort nach der Verwendung, anstatt abzuwarten, bis das Objekt durch die Common Language Runtime wie folgt speicherbereinigt wird:

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="NoCleanup":::

## <a name="example"></a>Beispiel

Um den vorherigen Code in eine `try-catch-finally`-Anweisung umzuwandeln, wird der Bereinigungscode wie folgt vom Arbeitscode getrennt.

:::code language="csharp" source="snippets/exceptions/Program.cs" ID="WithCleanup":::

Da eine Ausnahme zu einem beliebigen Zeitpunkt innerhalb des `try`-Blocks vor dem `OpenWrite()`-Aufruf auftreten oder der `OpenWrite()`-Aufruf selbst fehlschlagen kann, ist nicht garantiert, dass die Datei geöffnet ist, wenn wir versuchen, sie zu schließen. Der `finally`-Block fügt eine Überprüfung hinzu, um sicherzustellen, dass das <xref:System.IO.FileStream>-Objekt nicht `null` ist, bevor Sie die <xref:System.IO.Stream.Close%2A>-Methode aufrufen. Ohne die `null`-Überprüfung kann der `finally`-Block eine eigene <xref:System.NullReferenceException>-Ausnahme auslösen. Das Auslösen von Ausnahmen in `finally`-Blöcken sollte allerdings nach Möglichkeit vermieden werden.

Auch Datenbankverbindungen können mit einem `finally`-Block geschlossen werden. Da die Anzahl der zulässigen Verbindungen mit einem Datenbankserver manchmal begrenzt ist, sollten Sie Datenbankverbindungen so schnell wie möglich schließen. Wenn eine Ausnahme ausgelöst wird, bevor Sie die Verbindung beenden können, ist es besser, den `finally`-Block zu verwenden, anstatt auf due automatische Speicherbereinigung zu warten.

## <a name="see-also"></a>Weitere Informationen

- [Using-Anweisung](../../language-reference/keywords/using-statement.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
