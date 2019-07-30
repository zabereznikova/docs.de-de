---
title: 'Ausnahmen: Die invalidArg-Funktion'
description: Erfahren Sie, F# wie die InvalidArg-Funktion eine Argument Ausnahme generiert.
ms.date: 05/16/2016
ms.openlocfilehash: 010dbfe313f539093b4ee7a19984ef54500b072d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630303"
---
# <a name="exceptions-the-invalidarg-function"></a>Ausnahmen: Die invalidArg-Funktion

Die `invalidArg` Funktion generiert eine Argument Ausnahme.

## <a name="syntax"></a>Syntax

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Hinweise

Der Parameter Name in der vorherigen Syntax ist eine Zeichenfolge mit dem Namen des Parameters, dessen Argument ungültig war. *Error-Message-String* ist eine Literalzeichenfolge oder ein Wert `string`vom Typ. Sie wird `Message` zur-Eigenschaft des Ausnahme Objekts.

Die von `invalidArg` generierte Ausnahme ist eine `System.ArgumentException` -Ausnahme. Der folgende Code veranschaulicht die Verwendung von `invalidArg` , um eine Ausnahme auszulösen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

Die Ausgabe ist wie folgt, gefolgt von einer Stapel Überwachung (nicht dargestellt).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Der `try...with` Ausdruck](the-try-with-expression.md)
- [Ausnahmen: Der `try...finally` Ausdruck](the-try-finally-expression.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
- [Ausnahmen: Die `failwith` -Funktion](the-failwith-function.md)
