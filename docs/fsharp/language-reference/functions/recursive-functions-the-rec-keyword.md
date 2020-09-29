---
title: 'Rekursive Funktionen: Das rec-Schlüsselwort'
description: "Erfahren Sie, wie das F #-Schlüsselwort ' REC ' mit dem ' Let '-Schlüsselwort verwendet wird, um eine rekursive Funktion zu definieren."
ms.date: 08/12/2020
ms.openlocfilehash: 1ab00ff9400129e531fd7320861b3d9625cad08c
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438079"
---
# <a name="recursive-functions-the-rec-keyword"></a>Rekursive Funktionen: Das rec-Schlüsselwort

Das `rec` Schlüsselwort wird in Verbindung mit dem- `let` Schlüsselwort verwendet, um eine rekursive Funktion zu definieren.

## <a name="syntax"></a>Syntax

```fsharp
// Recursive function:
let rec function-nameparameter-list =
    function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
    function1-body

and function2-nameparameter-list =
    function2-body
...
```

## <a name="remarks"></a>Bemerkungen

Rekursive Funktionen: Funktionen, die sich selbst anrufen, werden explizit in der Sprache F # mit dem- `rec` Schlüsselwort identifiziert. Mit dem- `rec` Schlüsselwort wird der Name der `let` Bindung im Textkörper verfügbar.

Das folgende Beispiel zeigt eine rekursive Funktion, die die *n*<sup>th</sup> -te-Datei "mebonacci" mit der mathematischen Definition berechnet.

```fsharp
let rec fib n =
    match n with
    | 0 | 1 -> 1
    | n -> fib (n-1) + fib (n-2)
```

> [!NOTE]
> In der Praxis ist Code wie das vorherige Beispiel nicht ideal, da er bereits berechnete Werte nicht mehr berechnet. Dies liegt daran, dass es sich nicht um einen endrekursiven handelt, was in diesem Artikel ausführlicher erläutert wird.

Methoden sind implizit rekursiv innerhalb des Typs, in dem Sie definiert sind, d. h. es ist nicht erforderlich, das- `rec` Schlüsselwort hinzuzufügen. Beispiel:

```fsharp
type MyClass() =
    member this.Fib(n) =
        match n with
        | 0 | 1 -> 1
        | n -> this.Fib(n-1) + this.Fib(n-2)
```

Let-Bindungen in Klassen sind jedoch nicht implizit rekursiv. Für alle `let` gebundenen Funktionen ist das- `rec` Schlüsselwort erforderlich.

## <a name="tail-recursion"></a>Endrekursion

Für einige rekursive Funktionen ist es erforderlich, eine "reine" Definition in eine "Pure"-Definition zu umgestalten, die [endrekursiv](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion)ist. Dies verhindert unnötige Neuberechnungen. Beispielsweise kann der vorherige "fbonacci Number"-Generator wie folgt umgeschrieben werden:

```fsharp
let fib n =
    let rec loop acc1 acc2 n =
        match n with
        | 0 -> acc1
        | 1 -> acc2
        | _ ->
            loop acc2 (acc1 + acc2) (n - 1)
    loop 0 1 n
```

Dies ist eine kompliziertere Implementierung. Das Erstellen einer "fbonacci"-Nummer ist ein gutes Beispiel für einen "naive" Algorithmus, der mathematisch rein, aber in der Praxis ineffizient ist. Einige Aspekte machen es in F # effizient und bleiben weiterhin rekursiv definiert:

* Eine rekursive innere Funktion namens `loop` , bei der es sich um ein idiomatische F #-Muster handelt.
* Zwei akkumulatorparameter, die Akkumulations Werte an rekursive Aufrufe übergeben.
* Eine Prüfung auf den Wert von `n` , um eine bestimmte Kumulierung zurückzugeben.

Wenn dieses Beispiel iterativ mit einer Schleife geschrieben wurde, sieht der Code mit zwei unterschiedlichen Werten ähnlich aus, bis eine bestimmte Bedingung erfüllt ist.

Der Grund dafür ist, dass dies endrekursiv ist, da der rekursive Aufruf keine Werte in der Aufruf Stapel speichern muss. Alle Zwischenwerte, die berechnet werden, werden über Eingaben in die innere Funktion akkumuliert. Dies ermöglicht es dem F #-Compiler auch, den Code so schnell wie möglich zu optimieren, wenn Sie etwas ähnliches wie eine-Schleife geschrieben hätten `while` .

Es ist üblich, F #-Code zu schreiben, der rekursiv etwas mit einer inneren und äußeren Funktion verarbeitet, wie im vorherigen Beispiel gezeigt. Die innere Funktion verwendet die Endrekursion, während die äußere Funktion über eine bessere Schnittstelle für Aufrufer verfügt.

## <a name="mutually-recursive-functions"></a>Gegenseitig rekursive Funktionen

Manchmal sind Funktionen *gegenseitig rekursiv*. Dies bedeutet, dass Aufrufe einen Kreis bilden, wobei eine Funktion eine andere aufruft, die wiederum den ersten aufruft, wobei eine beliebige Anzahl von Aufrufen dazwischen ist. Sie müssen diese Funktionen in der eine Bindung zusammen definieren `let` , indem Sie das- `and` Schlüsselwort verwenden, um Sie miteinander zu verknüpfen.

Das folgende Beispiel zeigt zwei gegenseitig rekursive Funktionen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="recursive-values"></a>Rekursive Werte

Sie können auch einen `let` gebundenen Wert definieren, um rekursiv zu sein. Dies erfolgt manchmal für die Protokollierung. Mit F # 5 und der- `nameof` Funktion können Sie Folgendes tun:

```fsharp
let rec nameDoubles = nameof nameDoubles + nameof nameDoubles
```

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
