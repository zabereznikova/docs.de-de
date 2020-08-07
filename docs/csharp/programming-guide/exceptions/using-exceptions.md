---
title: Verwenden von Ausnahmen – C#-Programmierhandbuch
description: Erfahren Sie, wie Sie Ausnahmen verwenden. Ausnahmen werden von Code ausgelöst, der auf einen Fehler stößt, und von Code abgefangen, der den Fehler behebt.
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], about exceptions
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
ms.openlocfilehash: fb45381f1c6cfa2f27d036ead8e662b7a0d8d924
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303373"
---
# <a name="use-exceptions-c-programming-guide"></a>Verwenden von Ausnahmen (C#-Programmierhandbuch)

In C# werden Fehler im Programm zur Laufzeit mithilfe von sogenannten Ausnahmen durch das Programm weitergegeben. Ausnahmen werden von Code ausgelöst, der auf einen Fehler stößt. Sie werden von Code abgefangen, der den Fehler beheben kann. Ausnahmen können durch die .NET-Runtime oder durch Code in einem Programm ausgelöst werden. Sobald eine Ausnahme ausgelöst wird, wird sie in der Aufrufliste nach oben weitergegeben, bis eine `catch`-Anweisung für die Ausnahme gefunden wird. Nicht abgefangene Ausnahmen werden von einem generischen Ausnahmehandler behandelt, der vom System bereitgestellt wird, das ein Dialogfeld anzeigt.  
  
 Ausnahmen werden von Klassen dargestellt, die von <xref:System.Exception> abgeleitet sind. Diese Klasse bestimmt den Typ der Ausnahme und enthält Eigenschaften, die über Details zur Ausnahme verfügen. Das Auslösen einer Ausnahme umfasst das Erstellen einer Instanz einer von einer Ausnahme abgeleiteten Klasse, das optionale Konfigurieren von Eigenschaften der Ausnahme und das Auslösen des Objekts mithilfe des Schlüsselworts `throw`. Zum Beispiel:  
  
 [!code-csharp[csProgGuideExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#1)]  
  
 Nachdem eine Ausnahme ausgelöst wird, überprüft die Runtime die aktuelle Anweisung, um festzustellen, ob sie sich in einem `try`-Block befindet. Falls dies der Fall ist, werden alle mit dem `try`-Block verknüpften `catch`-Blöcke überprüft, um festzustellen, ob sie die Ausnahme abfangen können. `Catch`-Blöcke geben normalerweise Ausnahmetypen an; wenn der Typ des `catch`-Blocks der gleiche Typ ist wie die Ausnahme oder die Basisklasse der Ausnahme, kann der `catch`-Block die Methode behandeln. Zum Beispiel:  
  
 [!code-csharp[csProgGuideExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#2)]  
  
 Wenn sich die Anweisung, die eine Ausnahme auslöst, nicht innerhalb eines `try`-Blocks befindet, oder der `try`-Block, der sie umfasst, über keinen übereinstimmenden `catch`-Block verfügt, überprüft die Runtime die aufrufende Methode auf eine `try`-Anweisung und `catch`-Blöcke. Die Runtime geht die Aufrufliste weiter nach oben durch und sucht nach einem kompatiblen `catch`-Block. Nachdem der `catch`-Block gefunden und ausgeführt wurde, wird die Steuerung an die nächste Anweisung nach diesem `catch`-Block weitergegeben.  
  
 Eine `try`-Anweisung kann mehr als einen `catch`-Block enthalten. Die erste `catch`-Anweisung, die die Ausnahme behandelt, wird ausgeführt; alle folgenden `catch`-Anweisungen werden ignoriert, selbst wenn sie kompatibel sind. Daher sollten catch-Blöcke immer vom spezifischsten Element (oder am meisten abgeleiteten) zum am wenigsten spezifischen sortiert werden. Zum Beispiel:  
  
 [!code-csharp[csProgGuideExceptions#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#3)]  
  
 Bevor der `catch`-Block ausgeführt wird prüft die Runtime auf `finally`-Blöcke. `Finally`-Blöcke ermöglichen dem Programmierer, mehrdeutige Zustände zu bereinigen, die möglicherweise von einem abgebrochenen `try`-Block übrig sind, oder externe Ressourcen freizugeben (z.B. Grafikhandles, Datenbankverbindungen oder Dateistreams), ohne auf Garbage Collector in der Runtime zum Finalisieren der Objekte zu warten. Zum Beispiel:  
  
 [!code-csharp[csProgGuideExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#4)]  
  
 Wenn `WriteByte()` eine Ausnahme auslöst, schlägt der Code im zweiten `try`-Block fehl, der versucht, die Datei erneut zu öffnen, wenn `file.Close()` nicht aufgerufen wird. Die Datei bleibt gesperrt. Da `finally`-Blocke ausgeführt werden, selbst wenn eine Ausnahme ausgelöst wird, ermöglicht es der `finally`-Block im vorherigen Beispiel, dass die Datei korrekt geschlossen wird und trägt so zur Fehlervermeidung bei.  
  
 Wenn in der Aufrufliste kein kompatibler `catch`-Block gefunden wird, nachdem eine Ausnahme ausgelöst wird, tritt eine der folgenden Situationen auf:  
  
- Wenn die Ausnahme sich in einem Finalizer befindet, wird der Finalizer abgebrochen und der Basisfinalizer (sofern vorhanden) aufgerufen.  
  
- Wenn die Aufrufliste einen statischen Konstruktor oder einen statischen Feldinitialisierer enthält, wird <xref:System.TypeInitializationException> ausgelöst und die ursprüngliche Ausnahme der <xref:System.Exception.InnerException%2A>-Eigenschaft der neuen Ausnahme zugewiesen.  
  
- Wenn der Anfang des Threads erreicht wird, wird der Thread beendet.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Ausnahmen und Ausnahmebehandlung](./index.md)
