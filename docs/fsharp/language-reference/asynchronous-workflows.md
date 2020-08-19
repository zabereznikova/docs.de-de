---
title: Asynchrone Workflows
description: 'Erfahren Sie mehr über die Unterstützung in der Programmiersprache F # zum asynchronen Ausführen von Berechnungen, die ohne Blockierung der Ausführung anderer Aufgaben ausgeführt werden.'
ms.date: 08/15/2020
ms.openlocfilehash: ac727fc630f13db01da964131ab39dc242a12cd1
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557710"
---
# <a name="asynchronous-workflows"></a>Asynchrone Workflows

In diesem Artikel wird die Unterstützung von F # zum asynchronen Ausführen von Berechnungen beschrieben, d. h. ohne die Ausführung anderer Aufgaben zu blockieren. So können z. b. asynchrone Berechnungen verwendet werden, um Anwendungen zu schreiben, die über Benutzeroberflächen verfügen, die für Benutzer reaktionsfähig bleiben, während die Anwendung andere Aufgaben ausführt.

## <a name="syntax"></a>Syntax

```fsharp
async { expression }
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax wird die durch dargestellte Berechnung `expression` so eingerichtet, dass Sie asynchron ausgeführt wird, d. h., ohne den aktuellen Berechnungs Thread zu blockieren, wenn asynchrone standbyvorgänge, e/a-Vorgänge und andere asynchrone Vorgänge ausgeführt werden. Asynchrone Berechnungen werden häufig in einem Hintergrund Thread gestartet, während die Ausführung im aktuellen Thread fortgesetzt wird. Der Typ des Ausdrucks ist `Async<'T>` , wobei `'T` der Typ ist, der von dem Ausdruck zurückgegeben wird, wenn das `return` Schlüsselwort verwendet wird. Der Code in einem solchen Ausdruck wird als *asynchroner Block*oder *Async-Block*bezeichnet.

Es gibt eine Vielzahl von Methoden zur asynchronen Programmierung, und die- [`Async`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html) Klasse stellt Methoden bereit, die verschiedene Szenarien unterstützen. Die allgemeine Vorgehensweise besteht darin, Objekte zu erstellen `Async` , die die Berechnung oder Berechnungen darstellen, die Sie asynchron ausführen möchten, und dann diese Berechnungen mithilfe einer der auslösenden Funktionen zu starten. Die verschiedenen auslösenden Funktionen bieten verschiedene Möglichkeiten, asynchrone Berechnungen auszuführen, und welche Sie verwenden, hängt davon ab, ob Sie den aktuellen Thread, einen Hintergrund Thread oder ein .NET Framework Aufgaben Objekt verwenden möchten und ob Fortsetzungs Funktionen vorhanden sind, die nach Abschluss der Berechnung ausgeführt werden sollen. Um z. b. eine asynchrone Berechnung für den aktuellen Thread zu starten, können Sie verwenden [`Async.StartImmediate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#StartImmediate) . Wenn Sie eine asynchrone Berechnung aus dem UI-Thread starten, blockieren Sie die Hauptereignis Schleife nicht, die Benutzeraktionen verarbeitet, wie z. b. Tastatureingaben und Maus Aktivitäten, sodass Ihre Anwendung reaktionsfähig bleibt.

## <a name="asynchronous-binding-by-using-let"></a>Asynchrone Bindung mithilfe von Let!

In einem asynchronen Workflow sind einige Ausdrücke und Vorgänge synchron, und einige sind längere Berechnungen, die so entworfen wurden, dass ein Ergebnis asynchron zurückgegeben wird. Wenn Sie eine Methode asynchron anstelle einer normalen Bindung aufzurufen `let` , verwenden Sie `let!` . Der Effekt von `let!` besteht darin, die Ausführung zu aktivieren, damit andere Berechnungen oder Threads fortgesetzt werden, während die Berechnung ausgeführt wird. Nachdem die Rechte Seite der `let!` Bindung zurückgegeben wurde, wird der Rest des asynchronen Workflows die Ausführung fortsetzen.

Der folgende Code zeigt den Unterschied zwischen `let` und `let!` . Die Codezeile, in der nur verwendet wird, `let` erstellt eine asynchrone Berechnung als Objekt, das Sie später mithilfe von ausführen können, `Async.StartImmediate` z [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) . b. oder. Die Codezeile, in der verwendet wird `let!` , startet die Berechnung, und der Thread wird angehalten, bis das Ergebnis verfügbar ist, bei dem die Ausführung fortgesetzt wird.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Zusätzlich zu `let!` können Sie verwenden, `use!` um asynchrone Bindungen auszuführen. Der Unterschied zwischen `let!` und `use!` ist mit dem Unterschied zwischen `let` und identisch `use` . Für `use!` wird das-Objekt am Ende des aktuellen Gültigkeits Bereichs verworfen. Beachten Sie, dass in der aktuellen Version der Sprache F # `use!` es nicht zulässt, dass ein Wert mit NULL initialisiert wird, auch wenn `use` dies nicht möglich ist.

## <a name="asynchronous-primitives"></a>Asynchrone primitive

Eine Methode, die eine einzelne asynchrone Aufgabe ausführt und das Ergebnis zurückgibt, wird als *asynchroner primitiv*bezeichnet und ist speziell für die Verwendung mit konzipiert `let!` . Mehrere asynchrone primitive sind in der F #-Kernbibliothek definiert. Zwei dieser Methoden für Webanwendungen werden im-Modul definiert [`FSharp.Control.WebExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html) : [`WebRequest.AsyncGetResponse`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncGetResponse) und [`WebClient.AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) . Beide primitiven laden Daten von einer Webseite herunter, wenn eine URL angegeben ist. `AsyncGetResponse` erzeugt ein `System.Net.WebResponse` -Objekt und `AsyncDownloadString` erstellt eine Zeichenfolge, die den HTML-Code für eine Webseite darstellt.

Im Modul sind mehrere primitive für asynchrone e/a-Vorgänge enthalten [`FSharp.Control.CommonExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html) . Diese Erweiterungs Methoden der `System.IO.Stream` -Klasse sind [`Stream.AsyncRead`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncRead) und [`Stream.AsyncWrite`](hhttps://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncWrite) .

Sie können auch eigene asynchrone primitive schreiben, indem Sie eine Funktion definieren, deren kompletter Text in einen Async-Block eingeschlossen ist.

Um asynchrone Methoden in den .NET Framework zu verwenden, die für andere asynchrone Modelle mit dem asynchronen F #-Programmiermodell entwickelt wurden, erstellen Sie eine Funktion, die ein f #-Objekt zurückgibt `Async` . Die F #-Bibliothek verfügt über Funktionen, die dies erleichtern.

Ein Beispiel für die Verwendung von asynchronen Workflows finden Sie hier: in der Dokumentation finden Sie viele weitere Informationen zu den Methoden der [Async-Klasse](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html).

In diesem Beispiel wird gezeigt, wie asynchrone Workflows verwendet werden, um Berechnungen parallel auszuführen.

Im folgenden Codebeispiel ruft eine Funktion `fetchAsync` den HTML-Text ab, der von einer Webanforderung zurückgegeben wird. Die- `fetchAsync` Funktion enthält einen asynchronen Codeblock. Wenn eine Bindung an das Ergebnis eines asynchronen primitiven erfolgt, wird in diesem Fall [`AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) `let!` anstelle von verwendet `let` .

Sie verwenden die [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) -Funktion, um einen asynchronen Vorgang auszuführen und auf das Ergebnis zu warten. Beispielsweise können Sie mehrere asynchrone Vorgänge parallel ausführen, indem Sie die- [`Async.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#Parallel) Funktion zusammen mit der- `Async.RunSynchronously` Funktion verwenden. Die- `Async.Parallel` Funktion nimmt eine Liste der- `Async` Objekte an, richtet den Code für jedes `Async` Aufgaben Objekt so ein, dass Sie parallel ausgeführt wird, und gibt ein Objekt zurück, `Async` das die parallele Berechnung darstellt. Ebenso wie bei einem einzelnen Vorgang wird aufgerufen, `Async.RunSynchronously` um die Ausführung zu starten.

Die `runAll` -Funktion gestartet parallel drei asynchrone Workflows und wartet, bis alle abgeschlossen sind.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Berechnungsausdrücke](computation-expressions.md)
- [Control. Async-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
