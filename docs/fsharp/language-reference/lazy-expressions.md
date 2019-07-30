---
title: Nicht strikte Ausdrücke
description: Erfahren Sie F# , wie verzögerte Ausdrücke die Leistung Ihrer Apps und Bibliotheken verbessern können.
ms.date: 03/13/2019
ms.openlocfilehash: 97429e9a4c3838cbaa2ead197db4443e0820e8b3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630747"
---
# <a name="lazy-expressions"></a>Nicht strikte Ausdrücke

Verzögerte *Ausdrücke* sind Ausdrücke, die nicht sofort ausgewertet werden, sondern stattdessen ausgewertet werden, wenn das Ergebnis benötigt wird. Dies kann helfen, die Leistung Ihres Codes zu verbessern.

## <a name="syntax"></a>Syntax

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax handelt es sich bei *Expression* um Code, der nur ausgewertet wird, wenn ein Ergebnis erforderlich ist, und der Bezeichner ist ein Wert, der das Ergebnis speichert. Der Wert ist vom Typ [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), wobei der tatsächliche Typ, der für `'T` verwendet wird, vom Ergebnis des Ausdrucks bestimmt wird.

Mithilfe von Lazy Expressions können Sie die Leistung verbessern, indem Sie die Ausführung von Ausdrücken auf die Situationen beschränken, in denen ein Ergebnis erforderlich ist.

Um die Ausführung der Ausdrücke zu erzwingen, wird die-Methode `Force`aufgerufen. `Force`bewirkt, dass die Ausführung nur einmal ausgeführt wird. Nachfolgende Aufrufe `Force` von geben das gleiche Ergebnis zurück, führen jedoch keinen Code aus.

Der folgende Code veranschaulicht die Verwendung von Lazy Expressions und die Verwendung von `Force`. `result` In diesem Code ist `Lazy<int>`der Typ von, und die `Force` -Methode gibt einen `int`zurück.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Die verzögerte Auswertung, aber nicht `Lazy` der-Typ, wird auch für Sequenzen verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [LazyExtensions-Modul](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
