---
title: Behandeln und Auslösen von Ausnahmen in .NET
description: Erfahren Sie, wie Sie Ausnahmen in .NET behandeln und auslösen. Mit Ausnahmen geben .NET-Vorgänge Fehler in Anwendungen an.
ms.date: 06/19/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET], exceptions
- exceptions [.NET], throwing
- exceptions [.NET]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
ms.openlocfilehash: 89d88e3128917125d1a09466ed4e230604d6978c
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662770"
---
# <a name="handling-and-throwing-exceptions-in-net"></a>Behandeln und Auslösen von Ausnahmen in .NET

Anwendungen müssen in der Lage sein, Fehler zu behandeln, die während der Ausführung konsistent auftreten. .NET bietet ein Modell, um Anwendungen auf einheitliche Weise über Fehler zu benachrichtigen: .NET-Vorgänge geben Fehler durch Auslösen von Ausnahmen an.

## <a name="exceptions"></a>Ausnahmen

Bei einer Ausnahme handelt es sich um einen Fehlerzustand oder unerwartetes Verhalten beim Ausführen eines Programms. Ausnahmen können durch Fehler in Ihrem oder in aufgerufenem Code (z.B. bei freigegebenen Bibliotheken), nicht verfügbare Betriebssystemressourcen, unerwartete, von der Runtime festgestellte Fehlerzustände (z.B. durch nicht überprüfbaren Code) und andere Ereignisse ausgelöst werden. Anwendungen können in einigen, aber nicht allen Fällen wiederhergestellt werden. Obwohl bei den meisten Anwendungsausnahmen eine Wiederherstellung möglich ist, ist dies beim Großteil der Laufzeitausnahmen nicht der Fall.

In .NET ist eine Ausnahme ein Objekt, das von der <xref:System.Exception?displayProperty=nameWithType>-Klasse erbt. Eine Ausnahme wird in einem Codebereich ausgelöst, in dem ein Fehler aufgetreten ist. Die Ausnahme bleibt solange im Stapel, bis sie durch die Anwendung behandelt oder das Programm beendet wird.

## <a name="exceptions-vs-traditional-error-handling-methods"></a>Ausnahmen vs. herkömmliche Fehlerbehandlungsmethoden

Herkömmliche Modelle der Fehlerbehandlung in Sprachen beruhten bisher entweder auf eigenen sprachenabhängigen Methoden der Fehlererkennung und -behandlung oder auf dem Fehlerbehandlungsmechanismus des Betriebssystems. Die Art und Weise, in der die Ausnahmebehandlung in .NET implementiert ist, bietet folgende Vorteile:

- Das Auslösen und Behandeln von Ausnahmen funktioniert für alle .NET-Programmiersprachen gleich.

- Eine besondere Sprachsyntax ist für die Ausnahmebehandlung nicht erforderlich, trotzdem kann jede Sprache ihre eigene Syntax definieren.

- Ausnahmen können prozess- und sogar computerübergreifend ausgelöst werden.

- Einer Anwendung kann Ausnahmebehandlungscode hinzugefügt werden, um die Programmzuverlässigkeit zu erhöhen.

Ausnahmen bieten verschiedene Vorteile gegenüber anderen Methoden zur Fehlerbenachrichtigung, z.B. Rückgabecodes. Fehler bleiben nicht unerkannt, da die Runtime Ihre Anwendung beendet, wenn eine Ausnahme ausgelöst wurde und nicht behandelt wird. Ungültige Werte werden nicht weiter im System weitergegeben – was passieren kann, wenn im Code nicht geprüft wird, ob ein Fehlerrückgabecode vorhanden ist.

## <a name="common-exceptions"></a>Allgemeine Ausnahmen

In der folgenden Tabelle sind einige allgemeine Ausnahmen sowie Beispiele aufgeführt, die die Ausnahmen verursachen können.

| Ausnahmetyp | Beschreibung | Beispiel |
| -------------- | ----------- | ------- |
| <xref:System.Exception> | Die Basisklasse für alle Ausnahmen. | Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme). |
| <xref:System.IndexOutOfRangeException> | Wird von der Runtime nur dann ausgelöst, wenn ein Array falsch indiziert ist. | Indizieren eines Arrays außerhalb seines gültigen Vereichs: <br /> `arr[arr.Length+1]` |
| <xref:System.NullReferenceException> | Wird von der Runtime nur dann ausgelöst, wenn auf ein NULL-Objekt verwiesen wird. | `object o = null;` <br /> `o.ToString();` |
| <xref:System.InvalidOperationException> | Wird von Methoden ausgelöst, wenn ein ungültiger Status vorliegt. | Aufrufen von `Enumerator.MoveNext()` nach Entfernen eines Elements aus der zugrunde liegenden Auflistung. |
| <xref:System.ArgumentException> | Die Basisklasse für alle Argumentausnahmen. | Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme). |
| <xref:System.ArgumentNullException> | Wird von Methoden ausgelöst, bei denen ein Argument nicht gleich NULL sein darf. | `String s = null;` <br /> `"Calculate".IndexOf(s);`|
| <xref:System.ArgumentOutOfRangeException> | Wird von Methoden ausgelöst, die überprüfen, ob Argumente in einem angegebenen Bereich liegen. | `String s = "string";` <br /> `s.Substring(s.Length+1);` |

## <a name="see-also"></a>Siehe auch

- [Exception-Klasse und Exception-Eigenschaften](exception-class-and-properties.md)
- [How to: Verwenden des Try-Catch-Blocks zum Abfangen von Ausnahmen](how-to-use-the-try-catch-block-to-catch-exceptions.md)
- [How to: Verwenden spezifischer Ausnahmen in einem Catch-Block](how-to-use-specific-exceptions-in-a-catch-block.md)
- [How to: Explizites Auslösen von Ausnahmen](how-to-explicitly-throw-exceptions.md)
- [How to: Erstellen benutzerdefinierter Ausnahmen](how-to-create-user-defined-exceptions.md)
- [Verwenden benutzergefilterter Ausnahmehandler](using-user-filtered-exception-handlers.md)
- [How to: Verwenden von Finally-Blöcken](how-to-use-finally-blocks.md)
- [Behandeln von COM-Interop-Ausnahmen](handling-com-interop-exceptions.md)
- [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md)
- [What Every Dev needs to Know About Exceptions in the Runtime (Was jeder Entwickler über Ausnahmen in der Runtime wissen sollte)](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/exceptions.md)
