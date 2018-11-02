---
title: Verzögerte Berechnungen (F#)
description: Erfahren Sie, wie F# verzögerte Berechnungen auf die Leistung Ihrer apps und Bibliotheken verbessern können.
ms.date: 05/16/2016
ms.openlocfilehash: 8afe815f26978de96291a52973d54a9dbcc5eaf2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45698207"
---
# <a name="lazy-computations"></a>Verzögerte Berechnungen

*Verzögerte Berechnungen* sind Berechnungen, die nicht sofort ausgewertet, aber stattdessen ausgewertet, wenn das Ergebnis benötigt wird. Dies kann helfen, um die Leistung Ihres Codes zu verbessern.

## <a name="syntax"></a>Syntax

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Ausdruck* ist Code, der ausgewertet wird, nur, wenn das Ergebnis erforderlich ist, und *Bezeichner* ist ein Wert, der das Ergebnis speichert. Der Wert ist vom Typ [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in dem Typ, der tatsächlich dient zur `'T` wird aus dem Ergebnis des Ausdrucks bestimmt.

Verzögerte Berechnungen können Sie zur Verbesserung der Leistung durch Einschränken der Ausführung einer Berechnung auf nur die Fälle, in denen ein Ergebnis benötigt wird.

Um die Berechnung ausgeführt werden zu erzwingen, rufen Sie die Methode `Force`. `Force` bewirkt, dass die Ausführung nur einmal ausgeführt werden. Nachfolgende Aufrufe von `Force` zurückgegeben werden, dieselben dazu führen, jedoch keinen Code nicht ausgeführt.

Der folgende Code veranschaulicht die Verwendung von verzögerten Berechnungen und die Verwendung von `Force`. In diesem Code wird der Typ des `result` ist `Lazy<int>`, und die `Force` Methode gibt ein `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Verzögerte Auswertung, aber nicht die `Lazy` eingeben, wird auch für Sequenzen verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [LazyExtensions-Modul](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
