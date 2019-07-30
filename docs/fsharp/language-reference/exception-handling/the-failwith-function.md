---
title: 'Ausnahmen: Die failwith-Funktion'
description: Erfahren Sie, wie die Funktion "Failwith" F#-Ausnahme generiert.
ms.date: 05/16/2016
ms.openlocfilehash: f2c86362d5bdde7bab55751f019965a5f4ca6236
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630328"
---
# <a name="exceptions-the-failwith-function"></a>Ausnahmen: Die failwith-Funktion

Die `failwith` Funktion generiert eine F# Ausnahme.

## <a name="syntax"></a>Syntax

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Hinweise

Der *Fehler-Message-String* in der vorherigen Syntax ist eine Literalzeichenfolge oder ein `string`Wert des Typs. Sie wird `Message` zur-Eigenschaft der Ausnahme.

Eine Ausnahme `failwith` , die von generiert wird, ist eine `System.Exception` -Ausnahme, bei der es sich um einen F# Verweis mit dem Namen `Failure` im Code handelt. Der folgende Code veranschaulicht die Verwendung von `failwith` , um eine Ausnahme auszulösen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Der `try...with` Ausdruck](the-try-with-expression.md)
- [Ausnahmen: Der `try...finally` Ausdruck](the-try-finally-expression.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
