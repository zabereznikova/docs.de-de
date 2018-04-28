---
title: 'Rekursive Funktionen: Das rec-Schlüsselwort (F#)'
description: Erfahren Sie, wie das f#-Schlüsselwort "Rec" mit dem Schlüsselwort "let" verwendet wird, um eine rekursive Funktion zu definieren.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1f5302c125605d2186deab0bbeaf2e84cc51edc3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="recursive-functions-the-rec-keyword"></a>Rekursive Funktionen: Das rec-Schlüsselwort

Die `rec` -Schlüsselwort wird verwendet, zusammen mit den `let` Schlüsselwort, um eine rekursive Funktion definieren.


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
Rekursive Funktionen, Funktionen, die selbst aufrufen, werden in der Programmiersprache f# explizit identifiziert. Dadurch wird den Bezeichner, der definiert wird im Gültigkeitsbereich der Funktion verfügbar.

Das folgende Codebeispiel veranschaulicht eine rekursive Funktion, die berechnet die *n*te Fibonacci-Zahl.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
In der Praxis ist wie oben angegeben Codes gehen zu Lasten der Arbeitsspeicher und Prozessorzeit, da hierbei die neuberechnung der zuvor berechnete Werte.


Methoden sind implizit rekursiv innerhalb des Typs. besteht keine Notwendigkeit zum Hinzufügen der `rec` Schlüsselwort. Let-Bindungen in Klassen sind nicht implizit rekursiv.


## <a name="mutually-recursive-functions"></a>Wechselseitig rekursive Funktionen
In einigen Fällen Funktionen sind *wechselseitig rekursive*, was bedeutet, dass Aufrufe einen Kreis bilden, in denen eine bestimmte Funktion aufruft anderen, die ihrerseits die erste Seite mit einer beliebigen Anzahl von Aufrufen zwischen. Müssen Sie solche Funktionen zusammen in einem definieren `let` Bindungen, mit dem `and` Schlüsselwort, um sie miteinander verknüpfen.

Das folgende Beispiel zeigt zwei wechselseitig rekursive Funktionen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Siehe auch
[Funktionen](index.md)
