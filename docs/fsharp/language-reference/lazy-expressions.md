---
title: Lazy-Ausdrücke
description: Erfahren Sie, wie F# lazy Ausdrücken können die Leistung Ihrer apps und Bibliotheken verbessern.
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904110"
---
# <a name="lazy-expressions"></a>Lazy-Ausdrücke

*Verzögerte Ausdrücke* sind Ausdrücke, die nicht sofort ausgewertet, aber stattdessen ausgewertet, wenn das Ergebnis benötigt wird. Dies kann helfen, um die Leistung Ihres Codes zu verbessern.

## <a name="syntax"></a>Syntax

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Ausdruck* ist Code, der ausgewertet wird, nur, wenn das Ergebnis erforderlich ist, und *Bezeichner* ist ein Wert, der das Ergebnis speichert. Der Wert ist vom Typ [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in dem Typ, der tatsächlich dient zur `'T` wird aus dem Ergebnis des Ausdrucks bestimmt.

Verzögerte Ausdrücken können Sie zur Verbesserung der Leistung durch Einschränken der Ausführung von einem Ausdrücke, die nur den Situationen, in dem ein Ergebnis benötigt wird.

Um die Ausdrücke, die ausgeführt werden zu erzwingen, rufen Sie die Methode `Force`. `Force` bewirkt, dass die Ausführung nur einmal ausgeführt werden. Nachfolgende Aufrufe von `Force` zurückgegeben werden, dieselben dazu führen, jedoch keinen Code nicht ausgeführt.

Der folgende Code veranschaulicht die Verwendung von verzögerten Ausdrücken und die Verwendung von `Force`. In diesem Code wird der Typ des `result` ist `Lazy<int>`, und die `Force` Methode gibt ein `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Verzögerte Auswertung, aber nicht die `Lazy` eingeben, wird auch für Sequenzen verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [LazyExtensions-Modul](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
