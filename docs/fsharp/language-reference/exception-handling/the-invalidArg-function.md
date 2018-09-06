---
title: 'Ausnahmen: Die invalidArg-Funktion (F#)'
description: Erfahren Sie, wie die F#-Funktion "InvalidArg" eine Argumentausnahme generiert.
ms.date: 05/16/2016
ms.openlocfilehash: 8bf65fae9392a88205e3cdec8b7d7a3ff42f8416
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43798177"
---
# <a name="exceptions-the-invalidarg-function"></a>Ausnahmen: Die invalidArg-Funktion

Die `invalidArg` Funktion generiert einen Argument-Ausnahmefehler.

## <a name="syntax"></a>Syntax

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Hinweise

Der Parametername in der vorherigen Syntax ist eine Zeichenfolge mit dem Namen des Parameters, deren Argument ungültig war. Die *Fehlermeldungszeichenfolge* ist eine Literalzeichenfolge oder ein Wert vom Typ `string`. Es wird die `Message` -Eigenschaft des Ausnahmeobjekts.

Die Ausnahme abrufen, indem `invalidArg` ist eine `System.ArgumentException` Ausnahme. Der folgende Code veranschaulicht die Verwendung von `invalidArg` eine Ausnahme ausgelöst.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

Die Ausgabe ist Folgendes ein, gefolgt von einer stapelverfolgung (nicht dargestellt).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Der `try...with`-Ausdruck](the-try-with-expression.md)
- [Ausnahmen: Der `try...finally`-Ausdruck](the-try-finally-expression.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
- [Ausnahmen: Die `failwith`-Funktion](the-failwith-function.md)
