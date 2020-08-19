---
title: Nicht strikte Ausdrücke
description: 'Erfahren Sie, wie Sie mit F # Lazy Expressions die Leistung Ihrer Apps und Bibliotheken verbessern können.'
ms.date: 08/15/2020
ms.openlocfilehash: 71c466ca3b74c9e92b81a3c268e07438ec944905
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558087"
---
# <a name="lazy-expressions"></a>Nicht strikte Ausdrücke

Verzögerte *Ausdrücke* sind Ausdrücke, die nicht sofort ausgewertet werden, sondern stattdessen ausgewertet werden, wenn das Ergebnis benötigt wird. Dies kann helfen, die Leistung Ihres Codes zu verbessern.

## <a name="syntax"></a>Syntax

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Bemerkungen

In der vorherigen Syntax handelt es sich bei *Expression* um Code, der nur ausgewertet wird, wenn ein Ergebnis erforderlich ist, und der *Bezeichner* ist ein Wert, der das Ergebnis speichert. Der Wert ist vom Typ [`Lazy<'T>`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazy-1-0.html) , wobei der tatsächliche Typ, der für verwendet wird, `'T` vom Ergebnis des Ausdrucks bestimmt wird.

Mithilfe von Lazy Expressions können Sie die Leistung verbessern, indem Sie die Ausführung von Ausdrücken auf die Situationen beschränken, in denen ein Ergebnis erforderlich ist.

Um die Ausführung der Ausdrücke zu erzwingen, wird die-Methode aufgerufen `Force` . `Force` bewirkt, dass die Ausführung nur einmal ausgeführt wird. Nachfolgende Aufrufe von `Force` geben das gleiche Ergebnis zurück, führen jedoch keinen Code aus.

Der folgende Code veranschaulicht die Verwendung von Lazy Expressions und die Verwendung von `Force` . In diesem Code ist der Typ von `result` `Lazy<int>` , und die- `Force` Methode gibt einen zurück `int` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Die verzögerte Auswertung, aber nicht der- `Lazy` Typ, wird auch für Sequenzen verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md).

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [LazyExtensions-Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazyextensions.html)
