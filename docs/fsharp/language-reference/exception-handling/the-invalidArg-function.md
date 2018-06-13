---
title: 'Ausnahmen: Die invalidArg-Funktion (F#)'
description: Erfahren Sie, wie 'InvalidArg'-Funktion [F#] eine Argumentausnahme generiert.
ms.date: 05/16/2016
ms.openlocfilehash: 43e1b6f3f36774ac50aeff147f75f133d6e3e5dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564507"
---
# <a name="exceptions-the-invalidarg-function"></a>Ausnahmen: Die invalidArg-Funktion

Die `invalidArg` generiert die Funktion eine Argumentausnahme.


## <a name="syntax"></a>Syntax

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Hinweise
Der Parametername in der vorherigen Syntax ist eine Zeichenfolge mit dem Namen des Parameters, deren Argument ungültig war. Die *Fehlermeldungszeichenfolge* ist eine Literalzeichenfolge oder ein Wert vom Typ `string`. Es wird die `Message` -Eigenschaft des Ausnahmeobjekts.

Die Ausnahme abrufen, indem Sie `invalidArg` ist eine `System.ArgumentException` Ausnahme. Der folgende Code veranschaulicht die Verwendung von `invalidArg` eine Ausnahme auslöst.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

Die Ausgabe lautet wie folgt, gefolgt durch eine stapelüberwachung (nicht dargestellt).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Siehe auch
[Ausnahmebehandlung](index.md)

[Ausnahmetypen](exception-types.md)

[Ausnahmen: Der `try...with`-Ausdruck](the-try-with-expression.md)

[Ausnahmen: Der `try...finally`-Ausdruck](the-try-finally-expression.md)

[Ausnahmen: Die `raise`-Funktion](the-raise-function.md)

[Ausnahmen: Die `failwith`-Funktion](the-failwith-function.md)
