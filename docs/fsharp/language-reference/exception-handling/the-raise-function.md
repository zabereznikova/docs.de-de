---
title: 'Ausnahmen: Die raise-Funktion (F#)'
description: Erfahren Sie, wie die f# "Auslösen" Funktion verwendet wird, um anzugeben, dass ein Fehler oder Ausnahmebedingung aufgetreten ist.
ms.date: 05/16/2016
ms.openlocfilehash: bad18bfbccd738a12e16a0e026ade22e96d4cfcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-the-raise-function"></a>Ausnahmen: Die raise-Funktion

Die `raise` Funktion wird verwendet, um anzugeben, dass ein Fehler oder Ausnahmebedingung aufgetreten ist. Informationen zum Fehler, die in einem Ausnahmeobjekt aufgezeichnet wird.


## <a name="syntax"></a>Syntax

```fsharp
raise (expression)
```

## <a name="remarks"></a>Hinweise
Die `raise` Funktion generiert ein Exception-Objekt und eine stapelentladung Prozess initiiert. Des Entladungsprozesses Stapel wird von der common Language Runtime (CLR) verwaltet, sodass das Verhalten dieses Vorgangs identisch ist, wie in jeder anderen. Der Stapel Entladungsprozesses wird eine Suche nach einem Ausnahmehandler, der die generierte Ausnahme entspricht. Die Suche beginnt in der aktuellen `try...with` Ausdruck, sofern vorhanden. Jedes Muster in den `with` Block aktiviert ist, in der Reihenfolge. Wenn ein passender Ausnahmehandler gefunden wird, wird die Ausnahme als behandelt. Andernfalls wird der Stapel entladen und `with` Blöcke der Aufrufkette werden überprüft, bis ein entsprechender Handler gefunden wird. Alle `finally` Blöcke, die in der Aufrufkette aufgetreten sind werden ebenfalls nacheinander ausgeführt, da beim Entladen des Stapels.

Die `raise` Funktion entspricht der `throw` in c# oder C++. Verwendung `reraise` in einem Catch-Handler die gleiche Ausnahme der Aufrufkette weitergegeben.

Die folgenden Codebeispiele veranschaulichen die Verwendung der `raise` Funktion eine Ausnahme generiert.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

Die `raise` Funktion kann auch zum Auslösen von Ausnahmen von .NET verwendet werden, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a>Siehe auch
[Ausnahmebehandlung](index.md)

[Ausnahmetypen](exception-types.md)

[Ausnahmen: Der `try...with`-Ausdruck](the-try-with-expression.md)

[Ausnahmen: Der `try...finally`-Ausdruck](the-try-finally-expression.md)

[Ausnahmen: Die `failwith`-Funktion](the-failwith-function.md)

[Ausnahmen: Die `invalidArg`-Funktion](the-invalidArg-function.md)
