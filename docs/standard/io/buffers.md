---
title: System.Buffers – .NET
ms.date: 12/05/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- buffers [.NET]
- I/O [.NET], buffers
author: rick-anderson
ms.author: riande
ms.openlocfilehash: e42f165bfedec3b1fa54615ee7e2a2028f40aadb
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960474"
---
# <a name="work-with-buffers-in-net"></a>Arbeiten mit Puffern in .NET

Dieser Artikel bietet eine Übersicht über die Typen, die das Lesen von Daten unterstützen, die über mehrere Puffer hinweg ausgeführt werden. Sie werden hauptsächlich zur Unterstützung von <xref:System.IO.Pipelines.PipeReader>-Objekten verwendet.

## <a name="ibufferwritert"></a>IBufferWriter\<T\>

<xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> ist ein Vertrag für synchrone gepufferte Schreibvorgänge. Auf niedrigster Ebene gilt Folgendes für die Schnittstelle:

- Sie ist einfach zu verwenden.
- Sie bietet Zugriff auf <xref:System.Memory%601>- oder <xref:System.Span%601>-Elemente. `Memory<T>` und `Span<T>` erlauben Schreibvorgänge, und Sie können ermitteln, wie viele `T`-Elemente geschrieben wurden.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

Für die oben genannte Methode gilt:

- Fordert einen Puffer mit mindestens 5 Bytes von `IBufferWriter<byte>` unter Verwendung von `GetSpan(5)` an.
- Sie schreibt Bytes für die ASCII-Zeichenfolge „Hello“ in das zurückgegebene `Span<byte>`-Element.
- Sie ruft <xref:System.Buffers.IBufferWriter%601> auf, um anzugeben, wie viele Bytes in den Puffer geschrieben wurden.

Diese Methode zum Schreiben verwendet die Puffer `Memory<T>`/`Span<T>`, die von `IBufferWriter<T>` bereitgestellt werden. Alternativ dazu kann die Erweiterungsmethode <xref:System.Buffers.BuffersExtensions.Write%2A> verwendet werden, um einen vorhandenen Puffer in das `IBufferWriter<T>`-Element zu kopieren. `Write` ruft `GetSpan`/`Advance` je nach Bedarf auf, daher muss nach dem Schreiben `Advance` nicht aufgerufen werden:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<xref:System.Buffers.ArrayBufferWriter%601> ist eine Implementierung des `IBufferWriter<T>`-Elements, dessen Sicherungsspeicher ein einzelnes zusammenhängendes Array ist.

### <a name="ibufferwriter-common-problems"></a>Häufige IBufferWriter-Probleme

- `GetSpan` und `GetMemory` geben einen Puffer mit mindestens der angeforderten Menge an Arbeitsspeicher zurück. Gehen Sie nicht von genauen Puffergrößen aus.
- Es gibt keine Garantie, dass aufeinanderfolgende Aufrufe denselben Puffer oder dieselbe Puffergröße zurückgeben.
- Nach dem Aufrufen von `Advance` muss ein neuer Puffer angefordert werden, um das Schreiben weiterer Daten fortzusetzen. In einen zuvor abgerufenen Puffer kann erst nach dem Aufruf von `Advance` geschrieben werden.

## <a name="readonlysequencet"></a>ReadOnlySequence\<T\>

![ReadOnlySequence mit Arbeitsspeicher in der Pipe, darunter die Sequenzposition des schreibgeschützten Arbeitsspeichers](media/buffers/ro-sequence.png)

<xref:System.Buffers.ReadOnlySequence%601> ist eine Struktur, die eine zusammenhängende oder eine nicht zusammenhängende Sequenz von `T` darstellen kann. Sie kann aus Folgendem erstellt werden:

1. Eine `T[]`
1. Eine `ReadOnlyMemory<T>`
1. Ein Paar aus einem verknüpften Listenknoten <xref:System.Buffers.ReadOnlySequenceSegment%601> und einem Index zum Darstellen der Start- und Endposition der Sequenz.

Die dritte Darstellung ist die interessanteste, da sie sich auf die Leistung verschiedener Vorgänge in `ReadOnlySequence<T>` auswirkt:

|Darstellung|Vorgang|Komplexität|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

Aufgrund dieser gemischten Darstellung macht `ReadOnlySequence<T>` Indizes als `SequencePosition` anstelle einer Ganzzahl verfügbar. Für eine `SequencePosition` gilt:

- Es handelt sich um einen nicht transparenten Wert, der einen Index für das `ReadOnlySequence<T>`-Element darstellt, aus dem der Wert stammt.
- Sie besteht aus zwei Teilen: einer Ganzzahl und einem Objekt. Die Darstellung dieser beiden Werte ist an die Implementierung von `ReadOnlySequence<T>` gebunden.

### <a name="access-data"></a>Zugriff auf Daten

`ReadOnlySequence<T>` macht Daten als aufzählbares Element von `ReadOnlyMemory<T>` verfügbar. Die Aufzählung jedes der Segmente kann mithilfe eines einfachen foreach-Vorgangs durchgeführt werden:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

Die oben genannte Methode durchsucht jedes Segment nach einem bestimmten Byte. Wenn Sie die `SequencePosition` jedes Segments nachverfolgen müssen, ist <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> besser geeignet. Das nächste Beispiel ändert den oben stehenden Code so, dass anstelle einer Ganzzahl eine `SequencePosition` zurückgegeben wird. Die Rückgabe einer `SequencePosition` bietet den Vorteil, dass die aufrufende Funktion keine zweite Überprüfung durchführen muss, um die Daten an einer bestimmten Indexposition abzurufen.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

Die Kombination aus `SequencePosition` und `TryGet` fungiert wie ein Enumerator. Das Positionsfeld wird beim Start jeder Iteration so geändert, dass es als Start jedes Segments innerhalb des `ReadOnlySequence<T>`-Elements dient.

Die oben beschriebene Methode ist als Erweiterungsmethode in `ReadOnlySequence<T>` vorhanden. <xref:System.Buffers.BuffersExtensions.PositionOf%2A> kann zur Vereinfachung des vorherigen Codes verwendet werden:

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a>Verarbeiten eines ReadOnlySequence\<T\>-Elements

Die Verarbeitung eines `ReadOnlySequence<T>`-Elements kann schwierig sein, weil Daten möglicherweise auf mehrere Segmente innerhalb der Sequenz aufgeteilt sind. Um die bestmögliche Leistung zu erzielen, teilen Sie den Code in zwei Pfade auf:

- Ein schneller Pfad, der den Fall eines einzelnen Segments verarbeitet.
- Ein langsamer Pfad, der auf Segmente aufgeteilte Daten verarbeitet.

Zur Verarbeitung von Daten in Sequenzen mit mehreren Segmenten können verschiedene Ansätze verwendet werden:

- Verwenden Sie das [`SequenceReader<T>`](#sequencereadert)-Element.
- Analysieren Sie Daten segmentweise, und verfolgen Sie die `SequencePosition` und den Index innerhalb des analysierten Segments nach. Dieses Vorgehen vermeidet unnötige Zuteilungen, ist aber insbesondere für kleine Puffer möglicherweise ineffizient.
- Kopieren Sie das `ReadOnlySequence<T>`-Element in ein zusammenhängendes Array, und behandeln Sie es wie einen einzelnen Puffer:
  - Wenn das `ReadOnlySequence<T>`-Element klein ist, kann es sinnvoll sein, die Daten mithilfe des [stackalloc](../../csharp/language-reference/operators/stackalloc.md)-Operators in einen Puffer mit Stapelzuordnung zu kopieren.
  - Kopieren Sie das `ReadOnlySequence<T>`-Element mithilfe von <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType> in ein in einem Pool zusammengefasstes Array.
  - Verwenden Sie [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A). Dies ist im langsamsten Pfad nicht empfehlenswert, da dadurch ein neues `T[]`-Element im Heap zugewiesen wird.

Die folgenden Beispiele veranschaulichen einige gängige Fälle für die Verarbeitung von `ReadOnlySequence<byte>`:

##### <a name="process-binary-data"></a>Verarbeiten von Binärdaten

Das folgende Beispiel analysiert eine 4 Byte lange Big-Endian-Ganzzahl ab dem Start des `ReadOnlySequence<byte>`-Elements.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

##### <a name="process-text-data"></a>Verarbeiten von Textdaten

Im Beispiel unten geschieht Folgendes:

- Die erste neue Zeile (`\r\n`) in `ReadOnlySequence<byte>` wird gefunden und über den Ausgabeparameter „line“ zurückgegeben.
- Diese Zeile wird abgeschnitten, dabei wird die Zeichenfolge `\r\n` aus dem Eingabepuffer ausgeschlossen.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a>Leere Segmente

Es ist möglich, leere Segmente in einem `ReadOnlySequence<T>`-Element zu speichern. Leere Segmente können beim expliziten Aufzählen von Segmenten auftreten:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

Der oben stehende Code erstellt ein `ReadOnlySequence<byte>`-Element mit leeren Segmenten und zeigt, wie sich diese leeren Segmente auf die verschiedenen APIs auswirken:

- `ReadOnlySequence<T>.Slice` mit einer `SequencePosition`, die auf ein leeres Segment zeigt, behält dieses Segment bei.
- `ReadOnlySequence<T>.Slice` mit einem int-Wert überspringt die leeren Segmente.
- Beim Aufzählen des `ReadOnlySequence<T>`-Elements werden die leeren Segmente aufgezählt.

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a>Potenzielle Probleme mit ReadOnlySequence\<T> und SequencePosition

Beim Verarbeiten von `ReadOnlySequence<T>`/`SequencePosition` gibt es im Vergleich zu einer normalen `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int`-Verarbeitung verschiedene ungewöhnliche Ergebnisse:

- `SequencePosition` ist eine Positionsmarkierung für ein bestimmtes `ReadOnlySequence<T>`-Element, keine absolute Position. Da diese Markierung relativ zu einem bestimmten `ReadOnlySequence<T>`-Element ist, hat sie außerhalb des `ReadOnlySequence<T>`-Elements, aus dem sie stammt, keine Bedeutung.
- In der `SequencePosition` können ohne das `ReadOnlySequence<T>`-Element keine arithmetischen Berechnungen ausgeführt werden. Das bedeutet, dass einfache Vorgänge wie `position++` als `ReadOnlySequence<T>.GetPosition(position, 1)` geschrieben werden.
- `GetPosition(long)` unterstützt **keine** negativen Indizes. Das bedeutet, dass es unmöglich ist, das vorletzte Zeichen abzurufen, ohne alle Segmente zu durchlaufen.
- Zwei `SequencePosition`-Elemente können nicht miteinander verglichen werden, sodass folgende Vorgänge schwierig sind:
  - Ermitteln, ob eine Position größer oder kleiner ist als eine andere Position.
  - Schreiben einiger Analysealgorithmen.
- `ReadOnlySequence<T>` ist größer als ein Objektverweis und sollte nach Möglichkeit durch [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) oder [ref](../../csharp/language-reference/keywords/ref.md) übergeben werden. Durch Übergeben von `ReadOnlySequence<T>` durch `in` oder `ref` werden weniger Kopien der [Struktur](../../csharp/language-reference/keywords/struct.md) erstellt.
- Für leere Segmente gilt:
  - Sie sind innerhalb eines `ReadOnlySequence<T>`-Elements gültig.
  - Sie können beim Durchlaufen mithilfe der `ReadOnlySequence<T>.TryGet`-Methode angezeigt werden.
  - Sie können beim Aufteilen der Sequenz in Slices mithilfe der `ReadOnlySequence<T>.Slice()`-Methode mit `SequencePosition`-Objekten angezeigt werden.

## <a name="sequencereadert"></a>SequenceReader\<T\>

<xref:System.Buffers.SequenceReader%601>:

- Es handelt sich um einen neuen Typ, der in .NET Core 3.0 eingeführt wurde, um die Verarbeitung eines `ReadOnlySequence<T>`-Elements zu vereinfachen.
- Durch den Typ entfallen die Unterschiede zwischen einem `ReadOnlySequence<T>`-Element mit einem Segment und einem `ReadOnlySequence<T>`-Element mit mehreren Segmenten.
- Der Typ stellt Hilfsfunktionen für das Lesen von Binär- und Textdaten bereit (`byte` und `char`), die möglicherweise auf mehrere Segmente aufgeteilt sind.

Es gibt integrierte Methoden für die Verarbeitung sowohl von binären Daten als auch von Daten mit Trennzeichen. Der folgende Abschnitt veranschaulicht, wie diese Methoden mit dem `SequenceReader<T>`-Element aussehen:

### <a name="access-data"></a>Zugriff auf Daten

`SequenceReader<T>` verfügt über Methoden zum Aufzählen von Daten direkt im `ReadOnlySequence<T>`-Element. Der folgende Code ist ein Beispiel für die Verarbeitung jeweils eines `ReadOnlySequence<byte>`-Elements pro `byte`:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

`CurrentSpan` macht das `Span`-Element des aktuellen Segments verfügbar – dies entspricht der manuellen Ausführung des Vorgangs in der Methode.

### <a name="use-position"></a>Verwenden der Position

Der folgende Code ist eine Beispielimplementierung von `FindIndexOf` unter Verwendung des `SequenceReader<T>`-Elements:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a>Verarbeiten von Binärdaten

Das folgende Beispiel analysiert eine 4 Byte lange Big-Endian-Ganzzahl ab dem Start des `ReadOnlySequence<byte>`-Elements.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a>Verarbeiten von Textdaten

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a>Häufige SequenceReader\<T\>-Probleme

- Da `SequenceReader<T>` eine änderbare Struktur ist, sollte das Element immer durch [Verweis](../../csharp/language-reference/keywords/ref.md) übergeben werden.
- `SequenceReader<T>` ist eine [ref-Struktur](../../csharp/language-reference/keywords/ref.md#ref-struct-types) und kann daher nur in synchronen Methoden verwendet und nicht in Feldern gespeichert werden. Weitere Informationen finden Sie unter [Schreiben von sicherem und effizientem C#-Code](../../csharp/write-safe-efficient-code.md).
- `SequenceReader<T>` ist für die Verwendung als Vorwärtslesefunktion optimiert. `Rewind` ist für Sicherungen mit geringem Umfang vorgesehen, die nicht über andere `Read`-, `Peek`- oder `IsNext`-APIs verarbeitet werden können.
