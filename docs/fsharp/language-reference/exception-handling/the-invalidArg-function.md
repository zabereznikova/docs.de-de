---
title: 'Ausnahmen: Die invalidArg-Funktion'
description: Erfahren Sie, F# wie die InvalidArg-Funktion eine Argument Ausnahme generiert.
ms.date: 05/16/2016
ms.openlocfilehash: 6b1c5fdb5a541da336977d3a67d471302edb36b6
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083013"
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

```console
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
