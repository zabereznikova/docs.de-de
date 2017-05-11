---
title: "Behandeln und Auslösen von Ausnahmen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c8c5962db342dba6ff22c409d145af5e628eed3d
ms.contentlocale: de-de
ms.lasthandoff: 05/04/2017

---
# <a name="handling-and-throwing-exceptions-in-net"></a>Behandeln und Auslösen von Ausnahmen in .NET

Anwendungen müssen in der Lage sein, Fehler zu behandeln, die während der Ausführung konsistent auftreten.  .NET bietet ein Modell, um Anwendungen auf einheitliche Weise über Fehler zu benachrichtigen: .NET-Vorgänge geben Fehler durch Auslösen von Ausnahmen an.

## <a name="exceptions"></a>Ausnahmen

Bei einer Ausnahme handelt es sich um einen Fehlerzustand oder unerwartetes Verhalten beim Ausführen eines Programms. Ausnahmen können durch Fehler in Ihrem oder in aufgerufenem Code (z.B. bei freigegebenen Bibliotheken), nicht verfügbare Betriebssystemressourcen, unerwartete, von der Runtime festgestellte Fehlerzustände (z.B. durch nicht überprüfbaren Code) und andere Ereignisse ausgelöst werden. Anwendungen können in einigen, aber nicht allen Fällen wiederhergestellt werden. Obwohl bei den meisten Anwendungsausnahmen eine Wiederherstellung möglich ist, ist dies beim Großteil der Laufzeitausnahmen nicht der Fall.

In .NET stellt eine Ausnahme ein Objekt dar, das von der [System.Exception](xref:System.Exception)-Klasse erbt. Eine Ausnahme wird in einem Codebereich ausgelöst, in dem ein Fehler aufgetreten ist. Die Ausnahme bleibt solange im Stapel, bis sie durch die Anwendung behandelt oder das Programm beendet wird.

## <a name="exceptions-vs-traditional-error-handling-methods"></a>Ausnahmen vs. herkömmliche Fehlerbehandlungsmethoden

Herkömmliche Modelle der Fehlerbehandlung in Sprachen beruhten bisher entweder auf eigenen sprachenabhängigen Methoden der Fehlererkennung und -behandlung oder auf dem Fehlerbehandlungsmechanismus des Betriebssystems. Die Art und Weise, in der die Ausnahmebehandlung in .NET implementiert ist, bietet folgende Vorteile:

- Das Auslösen und Behandeln von Ausnahmen funktioniert für alle .NET-Programmiersprachen gleich.

- Eine besondere Sprachsyntax ist für die Ausnahmebehandlung nicht erforderlich, trotzdem kann jede Sprache ihre eigene Syntax definieren.

- Ausnahmen können prozess- und sogar computerübergreifend ausgelöst werden.

- Einer Anwendung kann Ausnahmebehandlungscode hinzugefügt werden, um die Programmzuverlässigkeit zu erhöhen.

Ausnahmen bieten verschiedene Vorteile gegenüber anderen Methoden zur Fehlerbenachrichtigung, z.B. Rückgabecodes. Fehler bleiben nicht unerkannt, da die Runtime Ihre Anwendung beendet, wenn eine Ausnahme ausgelöst wurde und diese nicht behandelt wird. Ungültige Werte werden nicht weiter im System weitergegeben – was passieren kann, wenn im Code nicht geprüft wird, ob ein Fehlerrückgabecode vorhanden ist. 

## <a name="common-exceptions"></a>Allgemeine Ausnahmen

In der folgenden Tabelle sind einige allgemeine Ausnahmen sowie Beispiele aufgeführt, die die Ausnahmen verursachen können.

| Ausnahmetyp | Basistyp | Beschreibung | Beispiel |
| -------------- | --------- | ----------- | ------- |
| @System.Exception | @System.Object | Die Basisklasse für alle Ausnahmen. | Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme). |
| @System.IndexOutOfRangeException | @System.Exception | Wird von der Runtime nur dann ausgelöst, wenn ein Array falsch indiziert ist. | Indizieren eines Arrays außerhalb seines gültigen Bereichs: `arr[arr.Length+1]` |
| @System.NullReferenceException | @System.Exception | Wird von der Runtime nur dann ausgelöst, wenn auf ein NULL-Objekt verwiesen wird. | `object o = null; o.ToString();` |
| @System.InvalidOperationException | @System.Exception | Wird von Methoden ausgelöst, wenn ein ungültiger Status vorliegt. | Aufrufen von `Enumerator.GetNext()` nach Entfernen eines Elements aus der zugrunde liegenden Auflistung. |
| @System.ArgumentException | @System.Exception | Die Basisklasse für alle Argumentausnahmen. | Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme). |
| @System.ArgumentNullException | @System.Exception | Wird von Methoden ausgelöst, bei denen ein Argument nicht gleich NULL sein darf. | `String s = null; "Calculate".IndexOf (s);` |
| @System.ArgumentOutOfRangeException | @System.Exception | Wird von Methoden ausgelöst, die überprüfen, ob Argumente in einem angegebenen Bereich liegen. | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="see-also"></a>Siehe auch

* [Exception-Klasse und Exception-Eigenschaften](exception-class-and-properties.md)
* [Gewusst wie: Verwenden des Try-Catch-Blocks zum Abfangen von Ausnahmen](how-to-use-the-try-catch-block-to-catch-exceptions.md)
* [Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch-Block](how-to-use-specific-exceptions-in-a-catch-block.md)
* [Vorgehensweise: Explizites Auslösen von Ausnahmen](how-to-explicitly-throw-exceptions.md)
* [Gewusst wie: Erstellen benutzerdefinierter Ausnahmen](how-to-create-user-defined-exceptions.md)
* [Verwenden benutzergefilterter Ausnahmehandler](using-user-filtered-exception-handlers.md)
* [Gewusst wie: Verwenden von Finally-Blöcken](how-to-use-finally-blocks.md)
* [Behandeln von COM-Interop-Ausnahmen](handling-com-interop-exceptions.md)
* [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md)

Weitere Informationen zur Funktionsweise von Ausnahmen in .NET finden Sie in [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md) (Was jeder Entwickler über Ausnahmen in der Runtime wissen muss).

