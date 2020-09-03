---
title: Asynchroner Dateizugriff (C#)
description: Informationen zur Verwendung des Async-Features für den Zugriff auf Dateien in C# Sie können asynchrone Methoden aufrufen, ohne Rückrufe verwenden oder den Code methodenübergreifend aufteilen zu müssen.
ms.date: 08/19/2020
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: 9a8db6004e8fff2cb39f0c350b403b56ea619e54
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812041"
---
# <a name="asynchronous-file-access-c"></a>Asynchroner Dateizugriff (C#)

Sie können die Async-Funktion verwenden, um auf Dateien zuzugreifen. Mithilfe der Async-Funktion können Sie asynchrone Methoden aufrufen, ohne Rückrufe zu verwenden oder den Code über mehrere Methoden oder Lambdaausdrücke teilen zu müssen. Um synchronen Code asynchron auszuführen, rufen Sie einfach eine asynchrone Methode anstelle einer synchronen Methode auf und fügen Sie dem Code einige Schlüsselwörter hinzu.

Sie sollten die folgenden Gründe für das Hinzufügen von Asynchronie zu Dateizugriffsaufrufen in Betracht ziehen:

> [!div class="checklist"]
>
> - Durch Asynchronie kann die Reaktionsfähigkeit von UI-Anwendungen verbessert werden, da der UI-Thread, der den Vorgang startet, andere Aufgaben durchführen kann. Wenn der UI-Thread Code ausführt, der viel Zeit benötigt (z.B. mehr als 50 Millisekunden), kann die UI einfrieren, bis der E/A-Vorgang abgeschlossen ist und der UI-Thread wieder Tastatur- und Mauseingaben und andere Ereignisse verarbeiten kann.
> - Asynchronie verbessert die Skalierbarkeit von ASP.NET und anderen serverbasierten Anwendungen, indem die Notwendigkeit von Threads reduziert wird. Wenn die Anwendung einen dedizierten Thread pro Antwort verwendet und tausend Anforderungen gleichzeitig behandelt werden, werden auch tausend Threads benötigt. Asynchrone Vorgänge benötigen während der Wartezeit oft keinen Thread. Sie verwenden den vorhandenen E/A-Abschlussthread kurz am Ende.
> - Die Latenz von Dateizugriffsvorgängen kann unter bestimmten Umständen sehr niedrig sein, aber sie kann in Zukunft stark ansteigen. Eine Datei kann z.B. auf einen Server auf der anderen Seite der Erde verschoben werden.
> - Der zusätzliche Mehraufwand durch Verwendung der Async-Funktion ist gering.
> - Asynchrone Aufgaben können problemlos parallel ausgeführt werden.

## <a name="use-appropriate-classes"></a>Verwenden geeigneter Klassen

Die in diesem Thema gezeigten einfachen Beispiele veranschaulichen <xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> und <xref:System.IO.File.ReadAllTextAsync%2A?displayProperty=nameWithType>. Für begrenzte Kontrolle über die E/A-Vorgänge der Datei verwenden Sie die <xref:System.IO.FileStream>-Klasse, die über eine Option verfügt, die asynchrone E/A-Vorgänge auf Betriebssystemebene auslöst. Mit dieser Option können Sie das Blockieren eines ThreadPool-Threads in vielen Fällen vermeiden. Geben Sie zum Aktivieren dieser Option das Argument `useAsync=true` oder `options=FileOptions.Asynchronous` im Konstruktoraufruf an.

Sie können diese Option nicht mit <xref:System.IO.StreamReader> und <xref:System.IO.StreamWriter> verwenden, wenn Sie sie direkt öffnen, indem Sie einen Dateipfad angeben. Allerdings können Sie diese Option verwenden, wenn Sie ihnen ein <xref:System.IO.Stream> geben, das die <xref:System.IO.FileStream>-Klasse geöffnet hat. Asynchrone Aufrufe in Anwendungsbenutzeroberflächen sind schneller, selbst wenn ein ThreadPool-Thread blockiert wird, da der UI-Thread während der Wartezeit nicht blockiert wird.

## <a name="write-text"></a>Schreiben von Text

In den folgenden Beispielen wird Text in eine Datei geschrieben. Bei jeder await-Anweisung wird die Methode sofort beendet. Wenn die Datei-E/A abgeschlossen ist, wird die Methode bei der Anweisung hinter der await-Anweisung fortgesetzt. Der async-Modifizierer befindet sich in der Definition der Methoden, die die await-Anweisung verwenden.

### <a name="simple-example"></a>Einfaches Beispiel

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleWrite":::

### <a name="finite-control-example"></a>Beispiel für begrenzte Kontrolle

:::code language="csharp" source="snippets/file-access/Program.cs" id="WriteText":::

Das ursprüngliche Beispiel verfügt über die Anweisung `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, bei der es sich um eine Kontraktion der folgenden zwei Anweisungen handelt:

```csharp
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);
await theTask;
```

Die erste Anweisung gibt eine Aufgabe zurück und löst die Dateiverarbeitung aus. Die zweite await-Anweisung führt dazu, dass die Methode sofort beendet wird und eine andere Aufgabe zurückgibt. Wenn die Dateiverarbeitung später abgeschlossen wird, wird die Ausführung bei der Anweisung fortgesetzt, die auf die „await“-Anweisung folgt.

## <a name="read-text"></a>Lesen von Text

In den folgenden Beispielen wird Text aus einer Datei gelesen.

### <a name="simple-example"></a>Einfaches Beispiel

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleRead":::

### <a name="finite-control-example"></a>Beispiel für begrenzte Kontrolle

Der Text wird gepuffert und in diesem Fall in <xref:System.Text.StringBuilder> abgelegt. Anders als im vorherigen Beispiel generiert die Auswertung von „await“ einen Wert. Die Methode <xref:System.IO.Stream.ReadAsync%2A> gibt ein <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>-Element zurück, sodass die Auswertung der await-Anweisung einen `Int32`-Wert von Typ `numRead` erzeugt, nachdem der Vorgang abgeschlossen wurde. Weitere Informationen finden Sie unter [Async Return Types (C#) (Asynchrone Rückgabetypen (C#))](async-return-types.md).

:::code language="csharp" source="snippets/file-access/Program.cs" id="ReadText":::

## <a name="parallel-asynchronous-io"></a>Parallele und asynchrone E/A-Vorgänge

In den folgenden Beispielen wird die parallele Verarbeitung durch Schreiben von zehn Textdateien veranschaulicht.

### <a name="simple-example"></a>Einfaches Beispiel

:::code language="csharp" source="snippets/file-access/Program.cs" id="SimpleParallelWrite":::

### <a name="finite-control-example"></a>Beispiel für begrenzte Kontrolle

Die Methode <xref:System.IO.Stream.WriteAsync%2A> gibt für jede Datei eine Aufgabe zurück, die anschließend zu einer Liste von Aufgaben hinzugefügt wird. Die `await Task.WhenAll(tasks);`-Anweisung beendet die Methode und wird innerhalb der Methode fortgesetzt, wenn die Dateiverarbeitung für alle Aufgaben abgeschlossen ist.

Im Beispiel werden alle <xref:System.IO.FileStream>-Instanzen in einem `finally`-Block geschlossen, nachdem die Aufgaben abgeschlossen sind. Wenn jeder `FileStream` stattdessen in einer `using`-Anweisung erstellt wurde, kann `FileStream` verworfen werden, bevor die Aufgabe abgeschlossen ist.

Jegliche Leistungsverbesserungen stammen nahezu ausschließlich von der parallelen Verarbeitung und nicht von der asynchronen Verarbeitung. Die Vorteile der asynchronen Vorgänge bestehen darin, dass nicht mehrere Threads und nicht der Benutzeroberflächenthread gebunden werden.

:::code language="csharp" source="snippets/file-access/Program.cs" id="ParallelWriteText":::

Bei Verwendung der Methoden <xref:System.IO.Stream.WriteAsync%2A> und <xref:System.IO.Stream.ReadAsync%2A> können Sie einen <xref:System.Threading.CancellationToken> angeben, mit dem Sie den Vorgang in der Mitte des Streams beenden können. Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../../../../standard/threading/cancellation-in-managed-threads.md).

## <a name="see-also"></a>Weitere Informationen

- [Asynchrone Programmierung mit Async und Await (C#)](index.md)
- [Asynchrone Rückgabetypen (C#)](async-return-types.md)
