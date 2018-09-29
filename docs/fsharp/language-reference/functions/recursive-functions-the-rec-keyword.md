---
title: 'Rekursive Funktionen: Das rec-Schlüsselwort (F#)'
description: Erfahren Sie, wie das F#-'Rec'-Schlüsselwort mit dem Schlüsselwort "let" verwendet wird, um eine rekursive Funktion zu definieren.
ms.date: 05/16/2016
ms.openlocfilehash: 5aab6ed8ab0fc3c0f0bcfc93c3ce6518ec53254f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2018
ms.locfileid: "47456102"
---
# <a name="recursive-functions-the-rec-keyword"></a>Rekursive Funktionen: Das rec-Schlüsselwort

Die `rec` -Schlüsselwort wird verwendet, zusammen mit den `let` Schlüsselwort, um eine rekursive Funktion zu definieren.

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

Rekursive Funktionen, Funktionen, die selbst aufrufen, werden in der Sprache f# explizit identifiziert. Dadurch wird den Bezeichner, der definiert wird im Rahmen der Funktion verfügbar.

Der folgende Code zeigt eine rekursive Funktion, die berechnet die *n*<sup>th</sup> Fibonacci-Zahl.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
Genauso wie der obige Code ist in der Praxis gehen zu Lasten der Arbeitsspeicher und Prozessorzeit, da hierbei die neuberechnung der zuvor berechnete Werte.

Methoden sind implizit rekursiv innerhalb des Typs. besteht keine Notwendigkeit zum Hinzufügen der `rec` Schlüsselwort. Let-Bindungen in Klassen sind nicht implizit rekursiv.

## <a name="mutually-recursive-functions"></a>Wechselseitig rekursive Funktionen

Funktionen in einigen Fällen sind *wechselseitig rekursive*, was bedeutet, dass Aufrufe einen Kreis zu bilden, in dem eine Funktion aufruft, eine andere der aufruft, die erste, wiederum mit einer beliebigen Anzahl von Aufrufen zwischen. Müssen Sie solche Funktionen zusammen definieren, die `let` binden, unter Verwendung der `and` Schlüsselwort, um sie miteinander verknüpfen.

Das folgende Beispiel zeigt zwei sich gegenseitig rekursiver Funktionen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
