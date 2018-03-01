---
title: Asynchrone Workflows (F#)
description: "Weitere Informationen Sie zur Unterstützung in der F#-Programmiersprache zum Ausführen von Berechnungen asynchron ausgeführt wird, die ausgeführt werden, ohne dass die Ausführung von anderen Arbeitsaufgaben."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ee2bb9bf-e04a-4fbe-bf58-46d07229e981
ms.openlocfilehash: e1cbdb452c8f77d97a0231a5ec75d752a98d2ed6
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="asynchronous-workflows"></a>Asynchrone Workflows

> [!NOTE]
Mit dem API-Referenz-Link gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Dieses Thema beschreibt die Unterstützung in f# zum Ausführen von Berechnungen asynchron ausgeführt wird, d. h. ohne andere arbeiten, die Ausführung blockiert. Beispielsweise können asynchrone Berechnungen verwendet werden, zum Schreiben von Anwendungen mit Benutzeroberflächen, die Benutzern reaktionsfähig bleiben, wie die Anwendung andere Arbeit ausführt.

## <a name="syntax"></a>Syntax

```fsharp
async { expression }
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax, die Berechnung dargestellte `expression` eingerichtet wurde, asynchron ausgeführt wird, d. h. ausführen, ohne den aktuellen Berechnungsthread blockieren, wenn asynchrone Standby-Vorgänge, e/a- und anderer asynchronen Operationen ausgeführt werden. Asynchrone Berechnungen werden häufig in einem Hintergrundthread gestartet, während der Ausführung wird fortgeführt, für den aktuellen Thread. Der Typ des Ausdrucks ist `Async<'T>`, wobei `'T` ist der vom Ausdruck zurückgegebenen Typ bei der `return` -Schlüsselwort wird verwendet. Der Code in ein solcher Ausdruck wird als bezeichnet ein *asynchroner Block*, oder *Async-Block*.

Es gibt verschiedene Arten der Programmierung von asynchron ausgeführt wird, und die [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) Klasse enthält Methoden, die mehrere Szenarien zu unterstützen. Die allgemeine Vorgehensweise besteht im erstellen `Async` Objekte repräsentieren die Berechnung oder Berechnungen, die asynchron ausgeführt werden soll, und klicken Sie dann diese Berechnungen mit einer der auslösenden Funktionen zu starten. Die verschiedenen auslösenden Funktionen bieten verschiedene Möglichkeiten zum Ausführen von asynchronen Berechnungen und welche Sie verwenden hängt von, ob Sie den aktuellen Thread, einen Hintergrundthread weitergeben oder eine .NET Framework-Task-Objekt verwenden möchten und ob Fortsetzung vorhanden sind Funktionen, die ausgeführt werden soll, wenn die Berechnung beendet wurde. Beispielsweise um eine asynchrone Berechnung für den aktuellen Thread zu starten, können Sie [ `Async.StartImmediate` ](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3). Wenn Sie eine asynchrone Berechnung vom UI-Thread starten, werden Sie nicht die Haupt-Ereignisschleife blockiert, die Benutzeraktionen wie Tastatureingaben und Mausaktivitäten, verarbeitet, damit die Anwendung reaktionsfähig bleibt.

## <a name="asynchronous-binding-by-using-let"></a>Asynchrone Bindung mithilfe von let!

In einem asynchronen Workflow einige Ausdrücke und die Vorgänge sind synchron, und einige längeren Berechnungen, die entwickelt wurden, ein Ergebnis asynchron zurückgegeben werden. Wenn Sie eine Methode asynchron aufrufen, anstatt mit einem normalen `let` binden, verwenden Sie `let!`. Die Auswirkung der `let!` besteht darin, aktivieren die Ausführung auf anderen Berechnungen oder Threads zu fortfahren, da es sich bei die Berechnung ausgeführt wird. Nach rechts neben der `let!` Bindung zurückgibt, wird der Rest des asynchronen Workflows die Ausführung fortgesetzt.

Der folgende Code zeigt den Unterschied zwischen `let` und `let!`. Die Codezeile, die verwendet `let` einfach erstellt eine asynchrone Berechnung als ein Objekt, mit dem Sie später verwenden, z. B. `Async.StartImmediate` oder [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b). Die Codezeile, die verwendet `let!` startet die Berechnung, und klicken Sie dann der Thread angehalten wird, bis das Ergebnis verfügbar ist, an die Punkt die Ausführung wird fortgesetzt.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Zusätzlich zu `let!`, können Sie `use!` zum Ausführen von asynchronen Bindungen. Der Unterschied zwischen `let!` und `use!` ist identisch mit den Unterschied zwischen `let` und `use`. Für `use!`, das Objekt wird zum Abschluss des aktuellen Gültigkeitsbereichs verworfen. Beachten Sie, dass in der aktuellen Version von der Programmiersprache f# `use!` lässt sich nicht auf einen Wert auf null initialisiert werden, obwohl `use` verfügt.

## <a name="asynchronous-primitives"></a>Asynchrone primitiven

Eine Methode, die eine einzelne asynchrone Aufgabe ausführt, und gibt das Ergebnis aufgerufen, ein *asynchrone Primitive*, und diese dienen insbesondere für die Verwendung mit `let!`. Mehrere asynchrone primitiven sind in der f#-Kernbibliothek definiert. Sind zwei solche Methoden für Webanwendungen im Modul definierten [ `Microsoft.FSharp.Control.WebExtensions` ](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003): [ `WebRequest.AsyncGetResponse` ](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) und [ `WebClient.AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a). Beide primitive Herunterladen von Daten von einer Webseite, eine URL angegeben. `AsyncGetResponse` erzeugt eine `System.Net.WebResponse` -Objekt, und `AsyncDownloadString` erzeugt eine Zeichenfolge, die HTML für eine Webseite darstellt.

Mehrere primitiven für asynchrone e/a-Vorgänge sind in enthalten die [ `Microsoft.FSharp.Control.CommonExtensions` ](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) Modul. Diese Erweiterungsmethoden für die `System.IO.Stream` -Klasse sind [ `Stream.AsyncRead` ](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) und [ `Stream.AsyncWrite` ](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618).

Zusätzliche asynchrone primitiven stehen in der [f# PowerTools](https://fsprojects.github.io/VisualFSharpPowerTools/). Sie können auch eine eigene asynchronen primitiven schreiben, durch die Definition einer Funktion, deren vollständiger Text in einer Async-Block eingeschlossen ist.

Asynchrone Methoden in .NET Framework, die entwickelt wurden für anderen asynchronen Modellen mit dem asynchronen F#-Programmiermodell verwenden möchten, erstellen Sie eine Funktion, ein F#-zurückgibt `Async` Objekt. F#-Bibliothek verfügt über Funktionen, die Dies erleichtert, vornehmen.

Hier ist ein Beispiel zur Verwendung des asynchronen Workflows enthalten. Es gibt noch viele andere in der Dokumentation für die Methoden der der [Async-Klasse](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

Dieses Beispiel zeigt, wie Sie asynchrone Workflows verwenden, um Berechnungen parallel auszuführen.

Im folgenden Codebeispiel wird eine Funktion `fetchAsync` ruft der HTML-Text aus einer webanforderung zurückgegeben. Die `fetchAsync` Funktion enthält einen asynchronen Codeblock. Wenn eine Bindung setzt auf das Ergebnis eines asynchronen primitiven in diesem Fall [ `AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a)ermöglichen! wird anstelle der Let verwendet.

Verwenden Sie die Funktion [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) ein asynchroner Vorgang ausgeführt und das Ergebnis gewartet. Beispielsweise können Sie mehrere asynchrone Vorgänge parallel ausgeführt, mit der [ `Async.Parallel` ](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) -Funktion zusammen mit der `Async.RunSynchronously` Funktion. Die `Async.Parallel` Funktion akzeptiert eine Liste von der `Async` Objekte, richtet den Code für die einzelnen `Async` Aufgabenobjekt auszuführende Parallel aus, und gibt ein `Async` Objekt, das die parallele Berechnung darstellt. So wie für einen einzelnen Vorgang, rufen Sie `Async.RunSynchronously` auf die Ausführung zu starten.

Die `runAll` -Funktion startet drei asynchrone Workflows parallel und wartet, bis alle abgeschlossen wurden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Siehe auch

[F#-Sprachreferenz](index.md)

[Berechnungsausdrücke](computation-expressions.md)

[Control.Async-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
