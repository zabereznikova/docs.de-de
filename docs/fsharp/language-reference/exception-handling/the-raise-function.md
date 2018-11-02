---
title: 'Ausnahmen: Die raise-Funktion (F#)'
description: Erfahren Sie, wie die F#-'raise'-Funktion verwendet wird, um anzugeben, dass ein Fehler oder Ausnahmebedingung aufgetreten ist.
ms.date: 05/16/2016
ms.openlocfilehash: 537d274659d29404380bfdd56310ac267372bb98
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43778258"
---
# <a name="exceptions-the-raise-function"></a>Ausnahmen: Die raise-Funktion

Die `raise` Funktion wird verwendet, um anzugeben, dass ein Fehler oder Ausnahmebedingung aufgetreten ist. Informationen zu dem Fehler wird in einem Ausnahmeobjekt erfasst.

## <a name="syntax"></a>Syntax

```fsharp
raise (expression)
```

## <a name="remarks"></a>Hinweise

Die `raise` Funktion generiert ein Exception-Objekt und eine stapelentladung Prozess initiiert. Des Entladens Stapel wird durch die common Language Runtime (CLR), verwaltet, sodass das Verhalten dieses Prozesses identisch ist, da es in einer beliebigen anderen .NET-Sprache ist. Der Stapel entladen Prozess ist eine Suche nach einem Ausnahmehandler, der die generierte Ausnahme entspricht. Die Suche beginnt in der aktuellen `try...with` Ausdruck, sofern vorhanden. Jedes Muster in den `with` Block aktiviert ist, in der Reihenfolge. Wenn ein passender Ausnahmehandler gefunden wird, wird die Ausnahme als behandelt. Andernfalls wird der Stapel entladen und `with` -Blöcke in der Aufrufkette werden überprüft, bis ein entsprechender Handler gefunden wird. Alle `finally` zunehmender Abarbeitung des Stapels werden ebenfalls blockiert, die in der Aufrufkette gefunden werden nacheinander ausgeführt.

Die `raise` Funktion entspricht der `throw` in c# oder C++. Verwendung `reraise` in einem Catch-Handler die gleiche Ausnahme der Aufrufkette weitergegeben werden.

Die folgenden Codebeispiele veranschaulichen die Verwendung der `raise` Funktion eine Ausnahme generiert.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

Die `raise` Funktion kann auch zum Auslösen von Ausnahmen .NET verwendet werden, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Der `try...with`-Ausdruck](the-try-with-expression.md)
- [Ausnahmen: Der `try...finally`-Ausdruck](the-try-finally-expression.md)
- [Ausnahmen: Die `failwith`-Funktion](the-failwith-function.md)
- [Ausnahmen: Die `invalidArg`-Funktion](the-invalidArg-function.md)
