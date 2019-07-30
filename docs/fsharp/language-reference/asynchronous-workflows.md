---
title: Asynchrone Workflows
description: Erfahren Sie mehr über die F# Unterstützung in der Programmiersprache zum asynchronen Ausführen von Berechnungen, die ohne Blockierung der Ausführung anderer Aufgaben ausgeführt werden.
ms.date: 05/16/2016
ms.openlocfilehash: 2d967f6bfe46b4f3916648b3063210d1ba1c210f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630000"
---
# <a name="asynchronous-workflows"></a>Asynchrone Workflows

> [!NOTE]
> Mit dem API-Referenz-Link gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Dieses Thema beschreibt die Unterstützung in F# zum Ausführen von Berechnungen asynchron, d. h. ohne Ausführung weiterer Aufgaben zu blockieren. So können z. b. asynchrone Berechnungen verwendet werden, um Anwendungen zu schreiben, die über Benutzeroberflächen verfügen, die für Benutzer reaktionsfähig bleiben, während die Anwendung andere Aufgaben ausführt.

## <a name="syntax"></a>Syntax

```fsharp
async { expression }
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax wird die durch `expression` dargestellte Berechnung so eingerichtet, dass Sie asynchron ausgeführt wird, d. h., ohne den aktuellen Berechnungs Thread zu blockieren, wenn asynchrone standbyvorgänge, e/a-Vorgänge und andere asynchrone Vorgänge ausgeführt werden. Asynchrone Berechnungen werden häufig in einem Hintergrund Thread gestartet, während die Ausführung im aktuellen Thread fortgesetzt wird. Der Typ des Ausdrucks ist `Async<'T>`, wobei `'T` der Typ ist, der von dem Ausdruck zurückgegeben `return` wird, wenn das Schlüsselwort verwendet wird. Der Code in einem solchen Ausdruck wird als *asynchroner Block*oder *Async-Block*bezeichnet.

Es gibt eine Vielzahl von Methoden zur asynchronen Programmierung, und die [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) -Klasse stellt Methoden bereit, die verschiedene Szenarien unterstützen. Die allgemeine Vorgehensweise besteht darin `Async` , Objekte zu erstellen, die die Berechnung oder Berechnungen darstellen, die Sie asynchron ausführen möchten, und dann diese Berechnungen mithilfe einer der auslösenden Funktionen zu starten. Die verschiedenen auslösenden Funktionen bieten verschiedene Möglichkeiten, asynchrone Berechnungen auszuführen, und welche, welche Sie verwenden, hängt davon ab, ob Sie den aktuellen Thread, einen Hintergrund Thread oder ein .NET Framework Aufgaben Objekt verwenden möchten und ob eine Fortsetzung vorhanden ist. Funktionen, die ausgeführt werden sollen, wenn die Berechnung abgeschlossen ist. Um z. b. eine asynchrone Berechnung für den aktuellen Thread zu starten, können [`Async.StartImmediate`](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3)Sie verwenden. Wenn Sie eine asynchrone Berechnung aus dem UI-Thread starten, blockieren Sie die Hauptereignis Schleife nicht, die Benutzeraktionen verarbeitet, wie z. b. Tastatureingaben und Maus Aktivitäten, sodass Ihre Anwendung reaktionsfähig bleibt.

## <a name="asynchronous-binding-by-using-let"></a>Asynchrone Bindung mithilfe von Let!

In einem asynchronen Workflow sind einige Ausdrücke und Vorgänge synchron, und einige sind längere Berechnungen, die so entworfen wurden, dass ein Ergebnis asynchron zurückgegeben wird. Wenn Sie eine Methode asynchron anstelle einer normalen `let` Bindung aufzurufen, verwenden `let!`Sie. Der Effekt von `let!` besteht darin, die Ausführung zu aktivieren, damit andere Berechnungen oder Threads fortgesetzt werden, während die Berechnung ausgeführt wird. Nachdem die Rechte Seite `let!` der Bindung zurückgegeben wurde, wird der Rest des asynchronen Workflows die Ausführung fortsetzen.

Der folgende Code zeigt den Unterschied `let` zwischen `let!`und. Die Codezeile, in der `let` nur verwendet wird, erstellt eine asynchrone Berechnung als Objekt, das Sie später mithilfe von ausführen können, `Async.StartImmediate` z [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b). b. oder. Die Codezeile, in der `let!` verwendet wird, startet die Berechnung, und der Thread wird angehalten, bis das Ergebnis verfügbar ist, bei dem die Ausführung fortgesetzt wird.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Zusätzlich zu `let!`können Sie verwenden `use!` , um asynchrone Bindungen auszuführen. Der Unterschied `let!` zwischen `use!` und ist mit dem Unterschied zwischen `let` und `use`identisch. Für `use!`wird das-Objekt am Ende des aktuellen Gültigkeits Bereichs verworfen. Beachten Sie, dass in der aktuellen Version F# der Sprache `use!` nicht zulässt, dass ein Wert mit NULL initialisiert wird, auch wenn `use` dies nicht möglich ist.

## <a name="asynchronous-primitives"></a>Asynchrone primitive

Eine Methode, die eine einzelne asynchrone Aufgabe ausführt und das Ergebnis zurückgibt, wird als *asynchroner primitiv*bezeichnet und ist speziell für die `let!`Verwendung mit konzipiert. Mehrere asynchrone primitive sind in der F# Kernbibliothek definiert. Zwei dieser Methoden für Webanwendungen werden im-Modul [`Microsoft.FSharp.Control.WebExtensions`](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003)definiert [`WebRequest.AsyncGetResponse`](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) : [`WebClient.AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a)und. Beide primitiven laden Daten von einer Webseite herunter, wenn eine URL angegeben ist. `AsyncGetResponse`erzeugt ein `System.Net.WebResponse` -Objekt und `AsyncDownloadString` erstellt eine Zeichenfolge, die den HTML-Code für eine Webseite darstellt.

Im [`Microsoft.FSharp.Control.CommonExtensions`](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) Modul sind mehrere primitive für asynchrone e/a-Vorgänge enthalten. Diese Erweiterungs Methoden der `System.IO.Stream` -Klasse sind [`Stream.AsyncRead`](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) und. [`Stream.AsyncWrite`](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618)

Sie können auch eigene asynchrone primitive schreiben, indem Sie eine Funktion definieren, deren kompletter Text in einen Async-Block eingeschlossen ist.

Um verwenden asynchrone Methoden in .NET Framework, die entwickelt wurden, für andere asynchrone Modelle mit dem asynchronen F#-Programmiermodell, erstellen Sie eine Funktion, einen F#-zurückgibt `Async` Objekt. Die F# -Bibliothek verfügt über Funktionen, die dies erleichtern.

Ein Beispiel für die Verwendung von asynchronen Workflows finden Sie hier: in der Dokumentation finden Sie viele weitere Informationen zu den Methoden der [Async-Klasse](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

In diesem Beispiel wird gezeigt, wie asynchrone Workflows verwendet werden, um Berechnungen parallel auszuführen.

Im folgenden Codebeispiel ruft eine Funktion `fetchAsync` den HTML-Text ab, der von einer Webanforderung zurückgegeben wird. Die `fetchAsync` -Funktion enthält einen asynchronen Codeblock. Wenn eine Bindung an das Ergebnis eines asynchronen primitiven vorgenommen wird, können Sie in diesem [`AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a)Fall wird anstelle von Let verwendet.

Sie verwenden die- [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) Funktion, um einen asynchronen Vorgang auszuführen und auf das Ergebnis zu warten. Beispielsweise können Sie mehrere asynchrone Vorgänge parallel ausführen, indem Sie die [`Async.Parallel`](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) -Funktion zusammen mit der `Async.RunSynchronously` -Funktion verwenden. Die `Async.Parallel` -Funktion nimmt eine Liste `Async` der-Objekte an, richtet den Code für `Async` jedes Aufgaben Objekt so ein, dass Sie parallel ausgeführt `Async` wird, und gibt ein Objekt zurück, das die parallele Berechnung darstellt. Ebenso wie bei einem einzelnen Vorgang wird aufgerufen `Async.RunSynchronously` , um die Ausführung zu starten.

Die `runAll` -Funktion gestartet parallel drei asynchrone Workflows und wartet, bis alle abgeschlossen sind.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Berechnungsausdrücke](computation-expressions.md)
- [Control. Async-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
