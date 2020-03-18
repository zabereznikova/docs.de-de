---
title: Ausnahmen und Ausnahmebehandlung – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#]
- exceptions [C#]
- C# language, exceptions
ms.assetid: 0001887f-4fa2-47e2-8034-2819477e2344
ms.openlocfilehash: b883012cf8f72247ff4e0b47a46eee1854e2d534
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "76735651"
---
# <a name="exceptions-and-exception-handling-c-programming-guide"></a>Ausnahmen und Ausnahmebehandlung (C#-Programmierhandbuch)

Die C#-Funktionen zur Ausnahmebehandlung helfen Ihnen dabei, unerwartete oder außergewöhnliche Situationen zu verarbeiten, die beim Ausführen von Programmen auftreten können. Die Ausnahmebehandlung verwendet die Schlüsselwörter `try`, `catch` und `finally`, um Aktionen zu testen, die möglicherweise nicht erfolgreich sind, um Fehler zu behandeln, wenn Sie entscheiden, dass dies vernünftig ist, und um später Ressourcen zu bereinigen. Ausnahmen können von der Common Language Runtime (CLR), vom .NET Framework bzw. anderen Drittanbieterbibliotheken oder vom Anwendungscode generiert werden. Ausnahmen werden mit dem Schlüsselwort `throw` erstellt.

In vielen Fällen wird eine Ausnahme nicht von einer Methode ausgelöst, die von Ihrem Code direkt aufgerufen wurde, sondern von einer anderen Methode weiter unten in der Aufrufliste. In diesem Fall entlädt die CLR die Liste, sucht nach einer Methode mit einem `catch`-Block für den spezifischen Ausnahmetyp und führt den ersten gefundenen `catch`-Block aus. Wenn kein geeigneter `catch`-Block in der Aufrufliste gefunden wird, beendet die CLR den Prozess und zeigt eine Meldung für den Benutzer an.

In diesem Beispiel testet eine Methode, ob eine Division durch Null möglich ist, und fängt den Fehler ab. Ohne Ausnahmebehandlung würde dieses Programm mit dem Fehler **DivideByZeroException wurde nicht behandelt** beendet.

[!code-csharp[csProgGuideExceptions#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#18)]

## <a name="exceptions-overview"></a>Übersicht über Ausnahmen

Ausnahmen weisen folgende Eigenschaften auf:

- Bei Ausnahmen handelt es sich um Typen, die alle letztlich von `System.Exception` abgeleitet werden.
- Verwenden Sie einen `try`-Block um die Anweisungen, die möglicherweise Ausnahmen auslösen.
- Sobald eine Ausnahme im `try`-Block auftritt, springt der Steuerungsfluss zum ersten zugeordneten Ausnahmehandler, der sich an einer beliebigen Stelle in der Aufrufliste befindet. In C# wird das Schlüsselwort `catch` zum Definieren eines Ausnahmehandlers verwendet.
- Wenn für eine bestimmte Ausnahme kein Ausnahmehandler vorhanden ist, beendet das Programm die Ausführung mit einer Fehlermeldung.
- Fangen Sie Ausnahmen nur dann ab, wenn Sie sie behandeln und die Anwendung in einem bekannten Zustand belassen können. Wenn Sie `System.Exception` abfangen, lösen Sie diese mithilfe des Schlüsselworts `throw` am Ende des `catch`-Blocks erneut aus.
- Wenn ein `catch`-Block eine Ausnahmevariable definiert, können Sie diese verwenden, um weitere Informationen zum Typ der aufgetretenen Ausnahme abzurufen.
- Ausnahmen können von einem Programm mithilfe des Schlüsselworts `throw` explizit generiert werden.
- Ausnahmeobjekte enthalten detaillierte Informationen über den Fehler, z.B. den Zustand der Aufrufliste und eine Textbeschreibung des Fehlers.
- Code in einem `finally`-Block wird auch dann ausgeführt, wenn eine Ausnahme ausgelöst wurde. Verwenden Sie einen `finally`-Block, um Ressourcen freizugeben, beispielsweise um Streams oder Dateien zu schließen, die im `try`-Block geöffnet wurden.
- Zusätzlich zum strukturierten Win32-Mechanismus zur Ausnahmebehandlung wurden im .NET Framework verwaltete Ausnahmen implementiert. Weitere Informationen finden Sie unter [Structured Exception Handling (C/C++)](/cpp/cpp/structured-exception-handling-c-cpp) (Strukturierte Ausnahmebehandlung [C/C++]) und [A Crash Course on the Depths of Win32 Structured Exception Handling](http://bytepointer.com/resources/pietrek_crash_course_depths_of_win32_seh.htm) (Schnellkurs zu den Details der strukturierten Win32-Ausnahmebehandlung).

## <a name="related-sections"></a>Verwandte Abschnitte

Weitere Informationen zu Ausnahmen und zur Ausnahmebehandlung finden Sie in den folgenden Artikeln:

- [Verwenden von Ausnahmen](using-exceptions.md)
- [Ausnahmebehandlung](exception-handling.md)
- [Erstellen und Auslösen von Ausnahmen](creating-and-throwing-exceptions.md)
- [Vom Compiler generierte Ausnahmen](compiler-generated-exceptions.md)
- [Behandeln einer Ausnahme mit „try/catch“ (C#-Programmierhandbuch)](how-to-handle-an-exception-using-try-catch.md)
- [Ausführen von Bereinigungscode mit „finally“](how-to-execute-cleanup-code-using-finally.md)
- [Abfangen einer Nicht-CLS-Ausnahme](how-to-catch-a-non-cls-exception.md)

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

Weitere Informationen erhalten Sie unter [Ausnahmen](~/_csharplang/spec/exceptions.md) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.SystemException>
- [C#-Programmierhandbuch](../index.md)
- [C#-Schlüsselwörter](../../language-reference/keywords/index.md)
- [throw](../../language-reference/keywords/throw.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [Ausnahmen](../../../standard/exceptions/index.md)
