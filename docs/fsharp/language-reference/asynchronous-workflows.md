---
title: Asynchrone Workflows (F#)
description: Erfahren Sie mehr über die Unterstützung in den F# Programmiersprache zum Ausführen von Berechnungen asynchron, die ausgeführt werden, ohne die Ausführung weiterer Aufgaben zu blockieren.
ms.date: 05/16/2016
ms.openlocfilehash: 720996106d2b90392eacc75eb99147691ee83334
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127744"
---
# <a name="asynchronous-workflows"></a>Asynchrone Workflows

> [!NOTE]
> Mit dem API-Referenz-Link gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Dieses Thema beschreibt die Unterstützung in F# zum Ausführen von Berechnungen asynchron, d. h. ohne Ausführung weiterer Aufgaben zu blockieren. Beispielsweise können asynchrone Berechnungen verwendet werden, zum Schreiben von Anwendungen mit Benutzeroberflächen, die für Benutzer reaktionsfähig bleiben, wie die Anwendung andere Aufgaben ausführt.

## <a name="syntax"></a>Syntax

```fsharp
async { expression }
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax, die Berechnung durch dargestellt `expression` wird eingerichtet, asynchron, d. h. auszuführen, ohne blockiert den aktuellen Berechnungsthread aus, wenn asynchrone Standby-Vorgänge, e/a- und andere asynchrone Vorgänge durchgeführt werden. Asynchrone Berechnungen werden häufig in einem Hintergrundthread gestartet, während der Ausführung wird fortgeführt, für den aktuellen Thread. Der Typ des Ausdrucks ist `Async<'T>`, wobei `'T` ist der vom Ausdruck zurückgegebenen Typ bei der `return` -Schlüsselwort wird verwendet. Der Code in ein solcher Ausdruck wird als bezeichnet ein *asynchronen Block*, oder *asynchronen Block*.

Es gibt eine Vielzahl von Methoden zum asynchronen Programmieren und die [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) -Klasse bietet Methoden, die verschiedene Szenarien zu unterstützen. Der allgemeine Ansatz ist die Erstellung `Async` Objekte, die darstellen, der Berechnung oder Berechnungen, die asynchron ausgeführt werden soll, und klicken Sie dann diese Berechnungen mithilfe einer der auslösenden Funktionen zu starten. Die verschiedenen auslösenden Funktionen bieten verschiedene Möglichkeiten zum Ausführen von asynchronen Berechnungen und welche Sie verwenden hängt davon, ob Sie den aktuellen Thread, einem Hintergrundthread oder ein Task-Objekt von .NET Framework verwenden möchten und ob Fortsetzung vorhanden sind Funktionen, die ausgeführt werden soll, wenn die Berechnung beendet wurde. Z. B. um eine asynchrone Berechnung auf dem aktuellen Thread zu starten, können Sie [ `Async.StartImmediate` ](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3). Wenn Sie eine asynchrone Berechnung vom UI-Thread starten, blockieren Sie nicht die main-Ereignisschleife, die Benutzeraktionen, wie z. B. Tastenanschläge und Mausaktivitäten, verarbeitet, damit Ihre Anwendung reaktionsfähig bleibt.

## <a name="asynchronous-binding-by-using-let"></a>Asynchrone Datenbindung mithilfe von let!

In einem asynchronen Workflow einige Ausdrücke und die Vorgänge sind synchron, und einige sind länger Berechnungen, die entwickelt wurden, um ein Ergebnis asynchron zurück. Wenn Sie eine Methode asynchron aufrufen, anstatt eine gewöhnliche `let` Bindung, die Sie verwenden `let!`. Die Auswirkungen der `let!` besteht darin, aktivieren die Ausführung auf anderen Berechnungen oder Threads fortgesetzt wird, wie die Berechnung ausgeführt wird. Nach rechts neben der `let!` Bindung zurückgibt, der Rest des asynchronen Workflows fortgesetzt.

Der folgende Code zeigt den Unterschied zwischen `let` und `let!`. Die Codezeile, die verwendet `let` nur erstellt eine asynchrone Berechnung als ein Objekt, das Sie später verwenden, z. B. ausführen können `Async.StartImmediate` oder [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b). Die Codezeile, die verwendet `let!` die Berechnung beginnt, und klicken Sie dann der Thread wird angehalten, bis das Ergebnis verfügbar ist, an die Punkt die Ausführung wird fortgesetzt.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Zusätzlich zu `let!`, können Sie `use!` zum Ausführen von asynchroner Bindungen. Der Unterschied zwischen `let!` und `use!` ist identisch mit den Unterschied zwischen `let` und `use`. Für `use!`, das Objekt am Ende des aktuellen Bereichs verworfen wird. Beachten Sie, dass der in der aktuellen Version der F# Sprache `use!` lässt sich nicht auf einen Wert auf null initialisiert werden, obwohl `use` ist.

## <a name="asynchronous-primitives"></a>Asynchrone primitiven

Eine Methode, die einen einzelnen asynchronen Vorgang ausführt, und gibt das Ergebnis wird aufgerufen, eine *asynchrone Primitive*, und diese sind darauf ausgelegt, insbesondere für die Verwendung mit `let!`. Mehrere asynchrone primitiven werden definiert, der F# -Kernbibliothek. Werden zwei Methoden für Webanwendungen im Modul definierten [ `Microsoft.FSharp.Control.WebExtensions` ](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003): [ `WebRequest.AsyncGetResponse` ](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) und [ `WebClient.AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a). Beide primitive herunterladen Daten von einer Webseite, wenn eine URL. `AsyncGetResponse` erzeugt eine `System.Net.WebResponse` Objekt und `AsyncDownloadString` erzeugt eine Zeichenfolge, die den HTML-Code für eine Webseite darstellt.

Mehrere primitiven für asynchrone e/a-Vorgänge sind enthalten die [ `Microsoft.FSharp.Control.CommonExtensions` ](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) Modul. Diese Erweiterungsmethoden die `System.IO.Stream` -Klasse sind [ `Stream.AsyncRead` ](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) und [ `Stream.AsyncWrite` ](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618).

Sie können auch eigene asynchrone Primitive Typen schreiben, durch die Definition einer Funktion, deren vollständiger Text in einen asynchronen Block eingeschlossen ist.

Um verwenden asynchrone Methoden in .NET Framework, die entwickelt wurden, für andere asynchrone Modelle mit dem asynchronen F#-Programmiermodell, erstellen Sie eine Funktion, einen F#-zurückgibt `Async` Objekt. Die F# Bibliothek verfügt über Funktionen, die dies leicht zu bewerkstelligen ist.

Ein Beispiel für die Verwendung von asynchronen Workflows ist hier enthalten. Es gibt viele andere in der Dokumentation für die Methoden der [Async-Klasse](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

Dieses Beispiel zeigt, wie Sie asynchrone Workflows, um Berechnungen parallel auszuführen.

Das folgende Codebeispiel zeigt, einer Funktion `fetchAsync` ruft der HTML-Text von einer webanforderung zurückgegeben. Die `fetchAsync` -Funktion enthält einen asynchronen Codeblock. Wenn eine Bindung wird, auf das Ergebnis eines asynchronen primitiven, in diesem Fall [ `AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a), Let! wird anstelle von können verwendet werden.

Verwenden Sie die Funktion [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) ein asynchroner Vorgang ausgeführt, und warten, bis das Ergebnis. Beispielsweise können Sie mehrere asynchrone Vorgänge parallel ausgeführt, mit der [ `Async.Parallel` ](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) -Funktion zusammen mit den `Async.RunSynchronously` Funktion. Die `Async.Parallel` Funktion akzeptiert eine Liste mit der `Async` Objekte, richtet der Code für die einzelnen `Async` Task-Objekt zum Ausführen in parallelen und gibt eine `Async` Objekt, das die parallele Berechnung darstellt. Rufen Sie genau wie bei einem einzelnen Vorgang `Async.RunSynchronously` auf die Ausführung zu starten.

Die `runAll` Funktion startet drei asynchrone Workflows parallel und wartet, bis alle abgeschlossen wurden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Berechnungsausdrücke](computation-expressions.md)
- [Control.Async-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
