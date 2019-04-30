---
title: 'Rekursive Funktionen: Das Rec-Schlüsselwort'
description: Erfahren Sie, wie die F# 'Rec'-Schlüsselwort wird mit dem Schlüsselwort "let" verwendet, um eine rekursive Funktion zu definieren.
ms.date: 05/16/2016
ms.openlocfilehash: 9f9c7e1a4468de9551b3852d0e7b4381025b2699
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941004"
---
# <a name="recursive-functions-the-rec-keyword"></a>Rekursive Funktionen: Das Rec-Schlüsselwort

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

Rekursive Funktionen, Funktionen, die selbst aufrufen, werden in der Sprache F# explizit identifiziert. Dadurch wird den Bezeichner, der definiert wird im Rahmen der Funktion verfügbar.

Der folgende Code zeigt eine rekursive Funktion, die berechnet die *n*<sup>th</sup> Fibonacci-Zahl.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> Genauso wie der obige Code ist in der Praxis gehen zu Lasten der Arbeitsspeicher und Prozessorzeit, da hierbei die neuberechnung der zuvor berechnete Werte.

Methoden sind implizit rekursiv innerhalb des Typs. besteht keine Notwendigkeit zum Hinzufügen der `rec` Schlüsselwort. Let-Bindungen in Klassen sind nicht implizit rekursiv.

## <a name="mutually-recursive-functions"></a>Wechselseitig rekursive Funktionen

Funktionen in einigen Fällen sind *wechselseitig rekursive*, was bedeutet, dass Aufrufe einen Kreis zu bilden, in dem eine Funktion aufruft, eine andere der aufruft, die erste, wiederum mit einer beliebigen Anzahl von Aufrufen zwischen. Müssen Sie solche Funktionen zusammen definieren, die `let` binden, unter Verwendung der `and` Schlüsselwort, um sie miteinander verknüpfen.

Das folgende Beispiel zeigt zwei sich gegenseitig rekursiver Funktionen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)