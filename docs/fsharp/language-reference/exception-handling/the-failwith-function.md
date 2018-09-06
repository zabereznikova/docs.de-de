---
title: 'Ausnahmen: Die failwith-Funktion (F#)'
description: Erfahren Sie, wie die Funktion "Failwith" f#-Ausnahme generiert.
ms.date: 05/16/2016
ms.openlocfilehash: 69a2eb69e0157d3bde8cb8884cb0ae960634dddc
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784412"
---
# <a name="exceptions-the-failwith-function"></a>Ausnahmen: Die failwith-Funktion

Die `failwith` Funktion generiert eine F#-Ausnahme.

## <a name="syntax"></a>Syntax

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Hinweise

Die *Fehlermeldungszeichenfolge* in der vorherigen Syntax ist ein Zeichenfolgenliteral oder ein Wert vom Typ `string`. Es wird die `Message` -Eigenschaft der Ausnahme.

Die Ausnahme, die vom generierten `failwith` ist eine `System.Exception` Ausnahme aus, die ein Verweis ist mit dem Namen `Failure` in F#-Code. Der folgende Code veranschaulicht die Verwendung von `failwith` eine Ausnahme ausgelöst.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Der `try...with`-Ausdruck](the-try-with-expression.md)
- [Ausnahmen: Der `try...finally`-Ausdruck](the-try-finally-expression.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
