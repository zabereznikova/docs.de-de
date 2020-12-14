---
title: Ausnahmen und Ausnahmebehandlung – C#-Programmierhandbuch
description: Hier erfahren Sie mehr über Ausnahmen und die Ausnahmebehandlung. Mithilfe dieser C#-Features können Sie unerwartete oder außergewöhnliche Situationen bei der Ausführung eines Programms bewältigen.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#]
- exceptions [C#]
- C# language, exceptions
ms.assetid: 0001887f-4fa2-47e2-8034-2819477e2344
ms.openlocfilehash: 679171e6d397741ef44cb37fb770f6feba039fd9
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110623"
---
# <a name="exceptions-and-exception-handling-c-programming-guide"></a>Ausnahmen und Ausnahmebehandlung (C#-Programmierhandbuch)

Die C#-Funktionen zur Ausnahmebehandlung helfen Ihnen dabei, unerwartete oder außergewöhnliche Situationen zu verarbeiten, die beim Ausführen von Programmen auftreten können. Die Ausnahmebehandlung verwendet die Schlüsselwörter `try`, `catch` und `finally`, um Aktionen zu testen, die möglicherweise nicht erfolgreich sind, um Fehler zu behandeln, wenn Sie entscheiden, dass dies vernünftig ist, und um später Ressourcen zu bereinigen. Ausnahmen können von der Common Language Runtime (CLR), von .NET bzw. anderen Drittanbieterbibliotheken oder vom Anwendungscode generiert werden. Ausnahmen werden mit dem Schlüsselwort `throw` erstellt.

In vielen Fällen wird eine Ausnahme nicht von einer Methode ausgelöst, die von Ihrem Code direkt aufgerufen wurde, sondern von einer anderen Methode weiter unten in der Aufrufliste. Wenn eine Ausnahme ausgelöst wird, entlädt die CLR die Liste, sucht nach einer Methode mit einem `catch`-Block für den spezifischen Ausnahmetyp und führt den ersten gefundenen `catch`-Block aus. Wenn kein geeigneter `catch`-Block in der Aufrufliste gefunden wird, beendet die CLR den Prozess und zeigt eine Meldung für den Benutzer an.

In diesem Beispiel testet eine Methode, ob eine Division durch Null möglich ist, und fängt den Fehler ab. Ohne Ausnahmebehandlung würde dieses Programm mit dem Fehler **DivideByZeroException wurde nicht behandelt** beendet.

:::code language="csharp" source="snippets/exceptions/ExceptionTest.cs" ID="ExceptionTest":::

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
- Zusätzlich zum strukturierten Win32-Mechanismus zur Ausnahmebehandlung wurden in .NET verwaltete Ausnahmen implementiert. Weitere Informationen finden Sie unter [Structured Exception Handling (C/C++)](/cpp/cpp/structured-exception-handling-c-cpp) (Strukturierte Ausnahmebehandlung [C/C++]) und [A Crash Course on the Depths of Win32 Structured Exception Handling](http://bytepointer.com/resources/pietrek_crash_course_depths_of_win32_seh.htm) (Schnellkurs zu den Details der strukturierten Win32-Ausnahmebehandlung).

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

Weitere Informationen erhalten Sie unter [Ausnahmen](~/_csharplang/spec/exceptions.md) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- <xref:System.SystemException>
- [C#-Schlüsselwörter](../../language-reference/keywords/index.md)
- [throw](../../language-reference/keywords/throw.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [Ausnahmen](../../../standard/exceptions/index.md)
