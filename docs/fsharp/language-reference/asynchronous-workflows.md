---
title: Asynchrone Workflows
description: 'Erfahren Sie mehr über die Unterstützung in der Programmiersprache F # zum asynchronen Ausführen von Berechnungen, die ohne Blockierung der Ausführung anderer Aufgaben ausgeführt werden.'
ms.date: 05/16/2016
ms.openlocfilehash: 3bc24639b329401a8f944488e974f0739d4680df
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855464"
---
# <a name="asynchronous-workflows"></a>Asynchrone Workflows

In diesem Artikel wird die Unterstützung von F # zum asynchronen Ausführen von Berechnungen beschrieben, d. h. ohne die Ausführung anderer Aufgaben zu blockieren. So können z. b. asynchrone Berechnungen verwendet werden, um Anwendungen zu schreiben, die über Benutzeroberflächen verfügen, die für Benutzer reaktionsfähig bleiben, während die Anwendung andere Aufgaben ausführt.

> [!NOTE]
> Die docs.Microsoft.com-API-Referenz für F # ist nicht fertig. Wenn Sie auf unterbrochene Verknüpfungen stoßen, verweisen Sie stattdessen auf die [Dokumentation der F #-Kernbibliothek](https://fsharp.github.io/fsharp-core-docs/) .

## <a name="syntax"></a>Syntax

```fsharp
async { expression }
```

## <a name="remarks"></a>Bemerkungen

In der vorherigen Syntax wird die durch dargestellte Berechnung `expression` so eingerichtet, dass Sie asynchron ausgeführt wird, d. h., ohne den aktuellen Berechnungs Thread zu blockieren, wenn asynchrone standbyvorgänge, e/a-Vorgänge und andere asynchrone Vorgänge ausgeführt werden. Asynchrone Berechnungen werden häufig in einem Hintergrund Thread gestartet, während die Ausführung im aktuellen Thread fortgesetzt wird. Der Typ des Ausdrucks ist `Async<'T>` , wobei `'T` der Typ ist, der von dem Ausdruck zurückgegeben wird, wenn das `return` Schlüsselwort verwendet wird. Der Code in einem solchen Ausdruck wird als *asynchroner Block*oder *Async-Block*bezeichnet.

Es gibt eine Vielzahl von Methoden zur asynchronen Programmierung, und die- [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) Klasse stellt Methoden bereit, die verschiedene Szenarien unterstützen. Die allgemeine Vorgehensweise besteht darin, Objekte zu erstellen `Async` , die die Berechnung oder Berechnungen darstellen, die Sie asynchron ausführen möchten, und dann diese Berechnungen mithilfe einer der auslösenden Funktionen zu starten. Die verschiedenen auslösenden Funktionen bieten verschiedene Möglichkeiten, asynchrone Berechnungen auszuführen, und welche Sie verwenden, hängt davon ab, ob Sie den aktuellen Thread, einen Hintergrund Thread oder ein .NET Framework Aufgaben Objekt verwenden möchten und ob Fortsetzungs Funktionen vorhanden sind, die nach Abschluss der Berechnung ausgeführt werden sollen. Um z. b. eine asynchrone Berechnung für den aktuellen Thread zu starten, können Sie verwenden [`Async.StartImmediate`](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3) . Wenn Sie eine asynchrone Berechnung aus dem UI-Thread starten, blockieren Sie die Hauptereignis Schleife nicht, die Benutzeraktionen verarbeitet, wie z. b. Tastatureingaben und Maus Aktivitäten, sodass Ihre Anwendung reaktionsfähig bleibt.

## <a name="asynchronous-binding-by-using-let"></a>Asynchrone Bindung mithilfe von Let!

In einem asynchronen Workflow sind einige Ausdrücke und Vorgänge synchron, und einige sind längere Berechnungen, die so entworfen wurden, dass ein Ergebnis asynchron zurückgegeben wird. Wenn Sie eine Methode asynchron anstelle einer normalen Bindung aufzurufen `let` , verwenden Sie `let!` . Der Effekt von `let!` besteht darin, die Ausführung zu aktivieren, damit andere Berechnungen oder Threads fortgesetzt werden, während die Berechnung ausgeführt wird. Nachdem die Rechte Seite der `let!` Bindung zurückgegeben wurde, wird der Rest des asynchronen Workflows die Ausführung fortsetzen.

Der folgende Code zeigt den Unterschied zwischen `let` und `let!` . Die Codezeile, in der nur verwendet wird, `let` erstellt eine asynchrone Berechnung als Objekt, das Sie später mithilfe von ausführen können, `Async.StartImmediate` z [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) . b. oder. Die Codezeile, in der verwendet wird `let!` , startet die Berechnung, und der Thread wird angehalten, bis das Ergebnis verfügbar ist, bei dem die Ausführung fortgesetzt wird.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Zusätzlich zu `let!` können Sie verwenden, `use!` um asynchrone Bindungen auszuführen. Der Unterschied zwischen `let!` und `use!` ist mit dem Unterschied zwischen `let` und identisch `use` . Für `use!` wird das-Objekt am Ende des aktuellen Gültigkeits Bereichs verworfen. Beachten Sie, dass in der aktuellen Version der Sprache F # `use!` es nicht zulässt, dass ein Wert mit NULL initialisiert wird, auch wenn `use` dies nicht möglich ist.

## <a name="asynchronous-primitives"></a>Asynchrone primitive

Eine Methode, die eine einzelne asynchrone Aufgabe ausführt und das Ergebnis zurückgibt, wird als *asynchroner primitiv*bezeichnet und ist speziell für die Verwendung mit konzipiert `let!` . Mehrere asynchrone primitive sind in der F #-Kernbibliothek definiert. Zwei dieser Methoden für Webanwendungen werden im-Modul definiert [`Microsoft.FSharp.Control.WebExtensions`](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003) : [`WebRequest.AsyncGetResponse`](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) und [`WebClient.AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a) . Beide primitiven laden Daten von einer Webseite herunter, wenn eine URL angegeben ist. `AsyncGetResponse`erzeugt ein `System.Net.WebResponse` -Objekt und `AsyncDownloadString` erstellt eine Zeichenfolge, die den HTML-Code für eine Webseite darstellt.

Im Modul sind mehrere primitive für asynchrone e/a-Vorgänge enthalten [`Microsoft.FSharp.Control.CommonExtensions`](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) . Diese Erweiterungs Methoden der `System.IO.Stream` -Klasse sind [`Stream.AsyncRead`](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) und [`Stream.AsyncWrite`](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618) .

Sie können auch eigene asynchrone primitive schreiben, indem Sie eine Funktion definieren, deren kompletter Text in einen Async-Block eingeschlossen ist.

Um asynchrone Methoden in den .NET Framework zu verwenden, die für andere asynchrone Modelle mit dem asynchronen F #-Programmiermodell entwickelt wurden, erstellen Sie eine Funktion, die ein f #-Objekt zurückgibt `Async` . Die F #-Bibliothek verfügt über Funktionen, die dies erleichtern.

Ein Beispiel für die Verwendung von asynchronen Workflows finden Sie hier: in der Dokumentation finden Sie viele weitere Informationen zu den Methoden der [Async-Klasse](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

In diesem Beispiel wird gezeigt, wie asynchrone Workflows verwendet werden, um Berechnungen parallel auszuführen.

Im folgenden Codebeispiel ruft eine Funktion `fetchAsync` den HTML-Text ab, der von einer Webanforderung zurückgegeben wird. Die- `fetchAsync` Funktion enthält einen asynchronen Codeblock. Wenn eine Bindung an das Ergebnis eines asynchronen primitiven vorgenommen wird, können Sie in diesem Fall [`AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a) wird anstelle von Let verwendet.

Sie verwenden die [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) -Funktion, um einen asynchronen Vorgang auszuführen und auf das Ergebnis zu warten. Beispielsweise können Sie mehrere asynchrone Vorgänge parallel ausführen, indem Sie die- [`Async.Parallel`](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) Funktion zusammen mit der- `Async.RunSynchronously` Funktion verwenden. Die- `Async.Parallel` Funktion nimmt eine Liste der- `Async` Objekte an, richtet den Code für jedes `Async` Aufgaben Objekt so ein, dass Sie parallel ausgeführt wird, und gibt ein Objekt zurück, `Async` das die parallele Berechnung darstellt. Ebenso wie bei einem einzelnen Vorgang wird aufgerufen, `Async.RunSynchronously` um die Ausführung zu starten.

Die `runAll` -Funktion gestartet parallel drei asynchrone Workflows und wartet, bis alle abgeschlossen sind.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Berechnungsausdrücke](computation-expressions.md)
- [Control. Async-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
