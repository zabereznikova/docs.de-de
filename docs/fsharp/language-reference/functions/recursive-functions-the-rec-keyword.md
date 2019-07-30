---
title: 'Rekursive Funktionen: Das Rec-Schlüsselwort'
description: Erfahren Sie, F# wie das Schlüsselwort "Rec" mit dem Schlüsselwort "Let" verwendet wird, um eine rekursive Funktion zu definieren.
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630650"
---
# <a name="recursive-functions-the-rec-keyword"></a>Rekursive Funktionen: Das Rec-Schlüsselwort

Das `rec` Schlüsselwort wird in Verbindung mit `let` dem-Schlüsselwort verwendet, um eine rekursive Funktion zu definieren.

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

## <a name="remarks"></a>Hinweise

Rekursive Funktionen, Funktionen, die selbst aufrufen, werden in der Sprache F# explizit identifiziert. Dadurch ist der zu definierenden identierer im Gültigkeitsbereich der Funktion verfügbar.

Der folgende Code veranschaulicht eine rekursive Funktion, die die *n*<sup></sup> -te "fbonacci"-Zahl berechnet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> In der Praxis ist der oben genannte Code verschwenderisch für Arbeitsspeicher und Prozessorzeit, da er die Neuberechnung der zuvor berechneten Werte einschließt.

Methoden sind implizit rekursiv innerhalb des Typs. Es ist nicht erforderlich, das `rec` -Schlüsselwort hinzuzufügen. Let-Bindungen in Klassen sind nicht implizit rekursiv.

## <a name="mutually-recursive-functions"></a>Gegenseitig rekursive Funktionen

Manchmal sind Funktionen *gegenseitig rekursiv*. Dies bedeutet, dass Aufrufe einen Kreis bilden, wobei eine Funktion eine andere aufruft, die wiederum den ersten aufruft, wobei eine beliebige Anzahl von Aufrufen dazwischen ist. Sie müssen diese Funktionen in der eine `let` Bindung zusammen definieren, indem Sie das `and` -Schlüsselwort verwenden, um Sie miteinander zu verknüpfen.

Das folgende Beispiel zeigt zwei gegenseitig rekursive Funktionen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
