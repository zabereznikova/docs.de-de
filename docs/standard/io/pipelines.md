---
title: 'E/A-Pipelines: .NET'
description: Erfahren Sie, wie Sie E/A-Pipelines in .NET effizient verwenden und Probleme im Code vermeiden können.
ms.date: 08/27/2020
helpviewer_keywords:
- Pipelines
- Pipelines I/O
- I/O [.NET], Pipelines
author: rick-anderson
ms.author: riande
ms.openlocfilehash: 508ae0e2b854f81ee639a63063a8f6d73ae84863
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830635"
---
# <a name="systemiopipelines-in-net"></a>System.IO.Pipelines in .NET

<xref:System.IO.Pipelines> ist eine neue Bibliothek, die entwickelt wurde, um die Ausführung von Hochleistungs-E/A in .NET zu erleichtern. Dabei handelt es sich um eine Bibliothek für .NET Standard, die mit allen .NET-Implementierungen kompatibel ist.

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a>Von System.IO.Pipelines gelöste Probleme

<!-- corner case doesn't MT (machine translate)   -->
Apps, die Streamingdaten analysieren, bestehen aus Codebausteinen, die über viele spezialisierte und ungewöhnliche Codeflows verfügen. Die Codebausteine und der Sonderfallcode sind komplex und schwer zu verwalten.

`System.IO.Pipelines` soll Folgendes ermöglichen:

* Hochleistungsanalyse von Streamingdaten.
* Verringern der Komplexität von Code.

Der folgende Code ist typisch für einen TCP-Server, der durch Zeilen getrennte Nachrichten (getrennt durch `'\n'`) von einem Client empfängt:

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

Der vorstehende Code weist mehrere Probleme auf:

* Die gesamte Nachricht (Zeilenende) wird möglicherweise nicht in einem einzigen Aufruf von `ReadAsync` empfangen.
* Das Ergebnis von `stream.ReadAsync` wird ignoriert. `stream.ReadAsync` gibt zurück, wie viele Daten gelesen wurden.
* Der Fall, in dem mehrere Zeilen in einem einzigen Aufruf von `ReadAsync` gelesen werden, wird nicht verarbeitet.
* Es wird bei jedem Lesevorgang ein `byte`-Array zugeordnet.

Um die oben beschriebenen Probleme zu beheben, sind die folgenden Änderungen erforderlich:

* Puffern der eingehenden Daten, bis eine neue Zeile gefunden wird.
* Analysieren aller zurückgegebenen Zeilen im Puffer.
* Es ist möglich, dass die Zeile größer als 1 KB (1.024 Bytes) ist. Der Code muss die Größe des Eingabepuffers ändern, bis das Trennzeichen gefunden wird, damit die gesamte Zeile in den Puffer passt.

  * Wenn die Größe des Puffers geändert wird, werden mehr Pufferkopien erstellt, weil in der Eingabe längere Zeilen vorhanden sind.
  * Um unnötigen Speicherplatz zu sparen, komprimieren Sie den Puffer, der zum Lesen von Zeilen verwendet wird.

* Verwenden Sie ggf. Pufferpools, um zu vermeiden, dass wiederholt Speicher zugeteilt wird.
* Der folgende Code behandelt einige dieser Probleme:

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs" id="snippet":::

Der oben gezeigte Code ist komplex und behandelt nicht alle identifizierten Probleme. Hochleistungsnetzwerke bedeuten in der Regel das Schreiben von sehr komplexem Code, um die Leistung zu maximieren. `System.IO.Pipelines` wurde entworfen, um das Schreiben dieser Art von Code zu vereinfachen.

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a>Pipe

Die <xref:System.IO.Pipelines.Pipe>-Klasse kann verwendet werden, um ein `PipeWriter/PipeReader`-Paar zu erstellen. Alle Daten, die in `PipeWriter` geschrieben werden, sind in `PipeReader` verfügbar:

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet2":::

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a>Grundlegende Verwendung von Pipe

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet":::

Es gibt zwei Schleifen:

* `FillPipeAsync` liest aus `Socket` und schreibt in `PipeWriter`.
* `ReadPipeAsync` liest aus `PipeReader` und analysiert eingehende Zeilen.

Es sind keine expliziten Puffer zugeordnet. Die gesamte Pufferverwaltung wird an die `PipeReader`- und `PipeWriter`-Implementierungen delegiert. Durch die Delegierung der Pufferverwaltung ist es für Daten verarbeitenden Code einfacher, sich ausschließlich auf die Geschäftslogik zu konzentrieren.

In der ersten Schleife geschieht Folgendes:

* <xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> wird aufgerufen, um Speicher vom zugrunde liegenden Writer abzurufen.
* <xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> wird aufgerufen, um `PipeWriter` mitzuteilen, wie viele Daten in den Puffer geschrieben wurden.
* <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> wird aufgerufen, um die Daten für `PipeReader` verfügbar zu machen.

In der zweiten Schleife verarbeitet `PipeReader` die von `PipeWriter` geschriebenen Puffer. Die Puffer stammen aus dem Socket. Für den Aufruf von `PipeReader.ReadAsync` gilt Folgendes:

* Er gibt ein <xref:System.IO.Pipelines.ReadResult> zurück, das zwei wichtige Informationen enthält:

  * Die gelesenen Daten in Form von `ReadOnlySequence<byte>`.
  * Einen boolescher Wert `IsCompleted`, der angibt, ob das Ende der Daten (EOF) erreicht wurde.

Nachdem das Zeilenende-Trennzeichen (EOL) gefunden und die Zeile analysiert wurde, geschieht Folgendes:

* Die Logik verarbeitet den Puffer, um die Daten zu überspringen, die bereits verarbeitet wurden.
* `PipeReader.AdvanceTo` wird aufgerufen, um `PipeReader` mitzuteilen, wie viele Daten verarbeitet und untersucht wurden.

Die Reader- und Writerschleifen werden durch den Aufruf von `Complete` beendet. `Complete` ermöglicht der zugrunde liegenden Pipe, den zugeordneten Arbeitsspeicher freizugeben.

### <a name="backpressure-and-flow-control"></a>Rückstau und Flusssteuerung

Im Idealfall arbeiten die Lese- und Analysevorgänge zusammen:

* Der schreibende Thread nutzt Daten aus dem Netzwerk und speichert sie in Puffern.
* Der analysierende Thread ist für das Erstellen der entsprechenden Datenstrukturen verantwortlich.

In der Regel nimmt die Analyse mehr Zeit als das Kopieren von Datenblöcken aus dem Netzwerk in Anspruch:

* Der lesende Thread überholt den analysierenden Thread.
* Der lesende Thread muss entweder langsamer werden oder mehr Speicher zuteilen, um die Daten für den analysierenden Thread zu speichern.

Für optimale Leistung ist ein Gleichgewicht zwischen häufigen Pausen und der Zuteilung von mehr Speicherplatz vorhanden.

Zum Beheben des oben beschriebenen Problems hat `Pipe` zwei Einstellungen, um den Datenfluss zu steuern:

* <xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Bestimmt, wie viele Daten gepuffert werden sollen, bevor für Aufrufe von <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> eine Pause eingelegt wird.
* <xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Bestimmt, wie viele Daten der Reader untersuchen muss, bevor die Aufrufe von `PipeWriter.FlushAsync` fortgesetzt werden.

![Abbildung mit ResumeWriterThreshold und PauseWriterThreshold](media/pipelines/resume-pause.png)

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:

* Gibt ein unvollständiges `ValueTask<FlushResult>` zurück, wenn die Datenmenge in `Pipe``PauseWriterThreshold` erreicht.
* Schließt `ValueTask<FlushResult>` ab, wenn der Wert kleiner als `ResumeWriterThreshold` wird.

Es werden zwei Werte verwendet, um einen schnellen Zyklus zu verhindern, der bei Verwendung nur eines Werts auftreten kann.

### <a name="examples"></a>Beispiele

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a>PipeScheduler

In der Regel wird der asynchrone Code bei Verwendung von `async` und `await` entweder für eine <xref:System.Threading.Tasks.TaskScheduler>-Klasse oder die aktuelle <xref:System.Threading.SynchronizationContext>-Klasse fortgesetzt.

Wenn E/A-Vorgänge durchgeführt werden, ist es wichtig, genau zu steuern, wo die E/A-Vorgänge durchgeführt werden. Diese Steuerung ermöglicht die effektive Nutzung von CPU-Caches. Effiziente Zwischenspeicherung ist für Hochleistungs-Apps wie Webserver von entscheidender Bedeutung. <xref:System.IO.Pipelines.PipeScheduler> bietet die Kontrolle darüber, wo asynchrone Rückrufe ausgeführt werden. Standardmäßig:

* Der aktuelle <xref:System.Threading.SynchronizationContext> wird verwendet.
* Wenn kein `SynchronizationContext` vorhanden ist, wird der Threadpool verwendet, um Rückrufe auszuführen.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Program.cs" id="snippet":::

[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) ist die <xref:System.IO.Pipelines.PipeScheduler>-Implementierung, die Rückrufe des Threadpools der Warteschlange hinzufügt. `PipeScheduler.ThreadPool` ist die Standardeinstellung und in der Regel die beste Wahl. [Pipescheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) kann unbeabsichtigte Folgen verursachen, z.B. Deadlocks.

### <a name="pipe-reset"></a>Pipezurücksetzung

Es ist häufig effizient, das `Pipe`-Objekt wiederzuverwenden. Zum Zurücksetzen der Pipe rufen Sie <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> auf, wenn `PipeReader` sowie `PipeWriter` abgeschlossen ist.

## <a name="pipereader"></a>PipeReader

<xref:System.IO.Pipelines.PipeReader> verwaltet den Arbeitsspeicher im Auftrag des Aufrufers. Rufen Sie **immer**<xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> auf, nachdem <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType> aufgerufen wurde. Dadurch kann `PipeReader` erkennen, wenn der Aufrufer Vorgänge im Arbeitsspeicher abgeschlossen hat, damit sie nachverfolgt werden können. Das von `PipeReader.ReadAsync` zurückgegebene `ReadOnlySequence<byte>`-Element ist nur bis zum Aufruf von `PipeReader.AdvanceTo` gültig. Es ist unzulässig, `ReadOnlySequence<byte>` nach dem Aufruf von `PipeReader.AdvanceTo` zu verwenden.

`PipeReader.AdvanceTo` nimmt zwei <xref:System.SequencePosition>-Argumente an.

* Das erste Argument bestimmt, wie viel Arbeitsspeicher verbraucht wurde.
* Das zweite Argument bestimmt, in welchem Umfang der Puffer untersucht wurde.

Das Markieren von Daten als verarbeitet bedeutet, dass die Pipe den Arbeitsspeicher an den zugrunde liegenden Pufferpool zurückgeben kann. Durch das Markieren von Daten als untersucht wird gesteuert, welche Aktion der nächste Aufruf von `PipeReader.ReadAsync` ausführt. Wenn alle Daten als untersucht markiert sind, bedeutet dies, dass der nächste Aufruf von `PipeReader.ReadAsync` erst dann eine Rückgabe liefert, wenn weitere Daten in die Pipe geschrieben werden. Jeder andere Wert führt dazu, dass der nächste Aufruf von `PipeReader.ReadAsync` sofort die untersuchten *und* die nicht untersuchten Daten zurückgibt. Es handelt sich jedoch nicht um bereits verarbeitete Daten.

### <a name="read-streaming-data-scenarios"></a>Szenarien für das Lesen von Streamingdaten

Beim Versuch, Streamingdaten zu lesen, gibt es einige typische Muster:

* Analysieren einer einzelnen Nachricht in einem angegebenen Datenstrom.
* Analysieren aller Nachrichten in einem angegebenen Datenstrom.

In den folgenden Beispielen wird die `TryParseMessage`-Methode zum Analysieren von Nachrichten aus `ReadOnlySequence<byte>` verwendet. `TryParseMessage` analysiert eine einzelne Nachricht und aktualisiert den Eingabepuffer, um die analysierte Nachricht aus dem Puffer zu kürzen. `TryParseMessage` ist nicht Bestandteil von .NET, sondern eine vom Benutzer erstellte Methode, die in den folgenden Abschnitten verwendet wird.

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a>Lesen einer einzelnen Nachricht

Der folgende Code liest eine einzelne Nachricht aus `PipeReader` und gibt sie an den Aufrufer zurück.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs" id="snippet":::

Der vorangehende Code:

* Analysiert eine einzelne Nachricht.
* Aktualisiert die verarbeitete `SequencePosition` und die untersuchte `SequencePosition`, um auf den Anfang des gekürzten Eingabepuffers zu verweisen.

Die beiden `SequencePosition`-Argumente werden aktualisiert, weil `TryParseMessage` die analysierte Nachricht aus dem Eingabepuffer entfernt. Wenn eine einzelne Nachricht aus dem Puffer analysiert wird, sollte die untersuchte Position im Allgemeinen eine der folgenden Positionen sein:

* Das Ende der Nachricht.
* Das Ende des empfangenen Puffers, wenn keine Nachricht gefunden wurde.

Das Szenario mit einer einzelnen Nachricht weist das größte Fehlerpotenzial auf. Wenn Sie die falschen Werte an *examined* (untersucht) übergeben, kann dies zu einer Ausnahme des Typs „Nicht genügend Arbeitsspeicher“ oder einer Endlosschleife führen. Weitere Informationen finden Sie im Abschnitt [Allgemeine PipeReader-Probleme](#gotchas) in diesem Artikel.

### <a name="reading-multiple-messages"></a>Lesen mehrerer Nachrichten

Der folgende Code liest alle Nachrichten aus einem `PipeReader` und ruft für jede Nachricht `ProcessMessageAsync` auf.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection1.cs" id="snippet":::

### <a name="cancellation"></a>Abbruch

`PipeReader.ReadAsync`:

* Unterstützt das Übergeben eines <xref:System.Threading.CancellationToken>-Elements.
* Löst eine <xref:System.OperationCanceledException> aus, wenn `CancellationToken` abgebrochen wird, während ein Lesevorgang aussteht.
* Unterstützt die Möglichkeit, den aktuellen Lesevorgang über <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType> abzubrechen, wodurch das Auslösen einer Ausnahme vermieden wird. Das Aufrufen von `PipeReader.CancelPendingRead` bewirkt, dass der aktuelle oder nächste Aufruf von `PipeReader.ReadAsync` ein <xref:System.IO.Pipelines.ReadResult> zurückgibt, wobei `IsCanceled` auf `true` festgelegt ist. Dies kann nützlich sein, um die vorhandene Leseschleife auf nicht destruktive Weise und ohne Auslösen einer Ausnahme anzuhalten.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection.cs" id="snippet":::

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a>Allgemeine PipeReader-Probleme

* Wenn die falschen Werte an `consumed` oder `examined` übergeben werden, können bereits gelesene Daten erneut gelesen werden.
* Wenn Sie `buffer.End` als untersucht übergeben, kann dies zu folgenden Ergebnissen führen:

  * Angehaltene Daten.
  * Möglicherweise wird eine Ausnahme aufgrund von nicht genügend Arbeitsspeicher (Out of Memory, OOM) ausgelöst, wenn keine Daten verarbeitet werden. Beispielsweise `PipeReader.AdvanceTo(position, buffer.End)`, wenn jeweils eine einzelne Nachricht aus dem Puffer verarbeitet wird.

* Wenn die falschen Werte an `consumed` oder `examined` übergeben werden, kann dies zu einer Endlosschleife führen. `PipeReader.AdvanceTo(buffer.Start)`, wenn sich `buffer.Start` nicht geändert hat, bewirkt beispielsweise, dass der nächste Aufruf von `PipeReader.ReadAsync` sofort vor dem Eintreffen neuer Daten zurückgegeben wird.
* Wenn die falschen Werte an `consumed` oder `examined` übergeben werden, kann dies zu einer Endlospufferung führen (möglicherweise OOM).
* Wenn Sie `ReadOnlySequence<byte>` nach dem Aufruf von `PipeReader.AdvanceTo` verwenden, kann dies zu einer Beschädigung des Arbeitsspeichers führen (Verwendung nach dem Freigeben).
* Wenn `PipeReader.Complete/CompleteAsync` nicht aufgerufen wird, kann dies zu einem Arbeitsspeicherverlust führen.
* Das Überprüfen von <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> und das Beenden der Leselogik vor dem Verarbeiten der Pufferergebnisse führt zu Datenverlusten. Die Beendigungsbedingung der Schleife sollte auf `ReadResult.Buffer.IsEmpty` und `ReadResult.IsCompleted` basieren. Wenn dieser Vorgang nicht ordnungsgemäß erfolgt, kann dies zu einer Endlosschleife führen.

#### <a name="problematic-code"></a>Problematischer Code

❌ **Datenverlust**

`ReadResult` kann das finale Datensegment zurückgeben, wenn `IsCompleted` auf `true` festgelegt ist. Das Nichtlesen dieser Daten vor dem Beenden der Leseschleife führt zu Datenverlusten.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Endlosschleife**

Die folgende Logik kann zu einer Endlosschleife führen, wenn `Result.IsCompleted``true` ist, im Puffer aber niemals eine vollständige Nachricht vorhanden ist.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet2":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

Im Folgenden finden Sie einen weiteren Codeausschnitt mit dem gleichen Problem. Der Code überprüft, ob ein nicht leerer Puffer vorhanden ist, bevor `ReadResult.IsCompleted` überprüft wird. Da dies in einer `else if`-Anweisung stattfindet, ist das Ergebnis eine Endlosschleife, wenn im Puffer niemals eine vollständige Nachricht vorhanden ist.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet3":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **App reagiert unerwarteterweise nicht mehr**

Der Aufruf von `PipeReader.AdvanceTo` mit `buffer.End` an der `examined`-Position ohne Bedingungen kann beim Analysieren einer einzelnen Nachricht dazu führen, dass die App nicht mehr reagiert. Der nächste Aufruf von `PipeReader.AdvanceTo` liefert erst eine Rückgabe, wenn:

* Weitere Daten in die Pipe geschrieben werden.
* Und die neuen Daten zuvor nicht untersucht wurden.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet4":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Nicht genügend Arbeitsspeicher (Out of Memory, OOM)**

Mit den folgenden Bedingungen behält der folgende Code die Pufferung bei, bis eine <xref:System.OutOfMemoryException> auftritt:

* Es gibt keine maximale Nachrichtengröße.
* Die von `PipeReader` zurückgegebenen Daten bilden keine vollständige Nachricht. Beispielsweise ergibt sich keine vollständige Nachricht, weil die andere Seite eine große Nachricht schreibt (z.B. eine Nachricht mit 4 GB).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet5":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Speicherbeschädigung**

Beim Schreiben von Hilfsprogrammen, die den Puffer lesen, sollte jede zurückgegebene Nutzlast kopiert werden, bevor `Advance` aufgerufen wird. Im folgenden Beispiel wird der Arbeitsspeicher zurückgegeben, der von `Pipe` verworfen wurde. Er kann für den nächsten Vorgang (Lese-/Schreibzugriff) wiederverwendet werden.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippetMessage":::

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet6":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a>PipeWriter

<xref:System.IO.Pipelines.PipeWriter> verwaltet Puffer zum Schreiben im Auftrag des Aufrufers. `PipeWriter` implementiert [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601). `IBufferWriter<byte>` ermöglicht es, Zugriff auf Puffer zu erhalten, um Schreibvorgänge ohne zusätzliche Pufferkopien auszuführen.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet":::

Der vorherige Code:

* Fordert einen Puffer mit mindestens 5 Bytes von `PipeWriter` unter Verwendung von <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> an.
* Schreibt Bytes für die ASCII-Zeichenfolge `"Hello"` in das zurückgegebene `Memory<byte>`-Element.
* Ruft <xref:System.IO.Pipelines.PipeWriter.Advance%2A> auf, um anzugeben, wie viele Bytes in den Puffer geschrieben wurden.
* Leert das `PipeWriter`-Element, das die Bytes an das zugrunde liegende Gerät sendet.

Die vorherige Methode zum Schreiben verwendet die Puffer, die von `PipeWriter` bereitgestellt werden. Alternativ geht <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType> folgendermaßen vor:

* Kopiert den vorhandenen Puffer in `PipeWriter`.
* Ruft `GetSpan`, `Advance` nach Bedarf auf und ruft dann <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> auf.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet2":::

### <a name="cancellation"></a>Abbruch

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> unterstützt das Übergeben eines <xref:System.Threading.CancellationToken>-Elements. Das Übergeben eines `CancellationToken` führt zu einer `OperationCanceledException`, wenn das Token abgebrochen wird, während ein Leerungsvorgang aussteht. `PipeWriter.FlushAsync` unterstützt die Möglichkeit, den aktuellen Leerungsvorgang über <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> abzubrechen, ohne eine Ausnahme auszulösen. Der Aufruf von `PipeWriter.CancelPendingFlush` bewirkt, dass der aktuelle oder nächste Aufruf von `PipeWriter.FlushAsync` oder `PipeWriter.WriteAsync` ein <xref:System.IO.Pipelines.FlushResult> zurückgibt, wobei `IsCanceled` auf `true` festgelegt ist. Dies kann nützlich sein, um die sich ergebende Leerung auf nicht destruktive Weise und ohne Auslösen einer Ausnahme anzuhalten.

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a>Allgemeine PipeWriter-Probleme

* <xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> und <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> geben einen Puffer mit mindestens der angeforderten Menge an Arbeitsspeicher zurück. Gehen Sie **nicht** von genauen Puffergrößen aus.
* Es gibt keine Garantie, dass aufeinanderfolgende Aufrufe denselben Puffer oder dieselbe Puffergröße zurückgeben.
* Nach dem Aufrufen von <xref:System.IO.Pipelines.PipeWriter.Advance%2A> muss ein neuer Puffer angefordert werden, um das Schreiben weiterer Daten fortzusetzen. In den zuvor abgerufenen Puffer kann nicht geschrieben werden.
* Das Aufrufen von `GetMemory` oder `GetSpan` ist während eines unvollständiger Aufrufs von `FlushAsync` nicht sicher.
* Wenn Sie `Complete` oder `CompleteAsync` aufrufen, während nicht geleerte Daten vorhanden sind, kann dies zu einer Speicherbeschädigung führen.

## <a name="iduplexpipe"></a>IDuplexPipe

<xref:System.IO.Pipelines.IDuplexPipe> ist ein Vertrag für Typen, die sowohl Lese- als auch Schreibvorgänge unterstützen. Eine Netzwerkverbindung würde z.B. durch eine `IDuplexPipe` dargestellt werden.

 Im Gegensatz zum `Pipe`-Element, das eine `PipeReader`- und eine `PipeWriter`-Klasse enthält, stellt `IDuplexPipe` nur eine Seite einer vollständigen Duplexverbindung dar. Dies bedeutet, dass die in `PipeWriter` geschriebenen Informationen von `PipeReader` gelesen werden.

## <a name="streams"></a>Streams

Beim Lesen oder Schreiben von Streamdaten lesen Sie Daten in der Regel mithilfe eines Deserialisierers und schreiben Daten mit einem Serialisierer. Die meisten dieser APIs zum Lesen und Schreiben eines Datenstrom verfügen über einen `Stream`-Parameter. Um die Integration mit diesen vorhandenen APIs zu vereinfachen, machen `PipeReader` und `PipeWriter` eine <xref:System.IO.Pipelines.PipeReader.AsStream%2A>-Methode verfügbar. <xref:System.IO.Pipelines.PipeWriter.AsStream%2A> gibt eine `Stream`-Implementierung um `PipeReader` oder `PipeWriter` zurück.

### <a name="stream-example"></a>Streambeispiel

`PipeReader`- und `PipeWriter`-Instanzen können mithilfe der statischen Methode `Create` erstellt werden, sofern ein <xref:System.IO.Stream>-Objekt und optional entsprechende Erstellungsoptionen vorhanden sind.

Mit <xref:System.IO.Pipelines.StreamPipeReaderOptions> kann die Erstellung einer `PipeReader`-Instanz gesteuert werden, indem folgende Parameter verwendet werden:

- <xref:System.IO.Pipelines.StreamPipeReaderOptions.BufferSize?displayProperty=nameWithType> ist die minimale Puffergröße in Byte, die beim Leihen von Arbeitsspeicher aus dem Pool verwendet wird. Der Standardwert ist `4096`.
- Mit dem <xref:System.IO.Pipelines.StreamPipeReaderOptions.LeaveOpen?displayProperty=nameWithType>-Flag wird festgelegt, ob der zugrunde liegende Stream nach Abschluss von `PipeReader` geöffnet bleibt. Der Standardwert ist `false`.
- <xref:System.IO.Pipelines.StreamPipeReaderOptions.MinimumReadSize?displayProperty=nameWithType> stellt den Schwellenwert der im Puffer verbleibenden Bytes dar, bevor ein neuer Puffer zugeordnet wird. Der Standardwert ist `1024`.
- <xref:System.IO.Pipelines.StreamPipeReaderOptions.Pool?displayProperty=nameWithType> entspricht der beim Belegen von Arbeitsspeicher verwendeten `MemoryPool<byte>`-Klasse. Der Standardwert ist `null`.

Mit <xref:System.IO.Pipelines.StreamPipeWriterOptions> kann die Erstellung einer `PipeWriter`-Instanz gesteuert werden, indem folgende Parameter verwendet werden:

- Mit dem <xref:System.IO.Pipelines.StreamPipeWriterOptions.LeaveOpen?displayProperty=nameWithType>-Flag wird festgelegt, ob der zugrunde liegende Stream nach Abschluss von `PipeWriter` geöffnet bleibt. Der Standardwert ist `false`.
- <xref:System.IO.Pipelines.StreamPipeWriterOptions.MinimumBufferSize?displayProperty=nameWithType> ist die minimale Puffergröße in Byte, die beim Leihen von Arbeitsspeicher von `4096` verwendet werden soll. Der Standardwert ist <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool>.
- <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool?displayProperty=nameWithType> entspricht der beim Belegen von Arbeitsspeicher verwendeten `MemoryPool<byte>`-Klasse. Der Standardwert ist `null`.

> [!IMPORTANT]
> Wenn Sie `PipeReader`- und `PipeWriter`-Instanzen mithilfe von `Create`-Methoden erstellen, müssen Sie die Lebensdauer des `Stream`-Objekts berücksichtigen. Wenn Sie Zugriff auf den Stream benötigen, nachdem der Reader oder Writer beendet wurde, müssen Sie das Flag in den Erstellungsoptionen `LeaveOpen` auf `true` festlegen. Andernfalls wird der Stream geschlossen.

Im folgenden Code wird die Erstellung von `PipeReader`- und `PipeWriter`-Instanzen mithilfe der `Create`-Methoden über einen Stream veranschaulicht.

:::code language="csharp" source="snippets/pipelines/Program.cs":::

Die Anwendung verwendet <xref:System.IO.StreamReader>, um die Datei *lorem-ipsum.txt* als Stream zu lesen. <xref:System.IO.FileStream> wird an die <xref:System.IO.Pipelines.PipeReader.Create%2A?displayProperty=nameWithType>-Methode übergeben, die ein `PipeReader`-Objekt instanziiert. Die Konsolenanwendung übergibt dann ihren Standardausgabestream mithilfe von <xref:System.Console.OpenStandardOutput?displayProperty=nameWithType> an <xref:System.IO.Pipelines.PipeWriter.Create%2A?displayProperty=nameWithType>. In diesem Beispiel wird ein [Abbruch](#cancellation) unterstützt.
