---
title: 'Ausnahmen: Die failwith-Funktion'
description: Erfahren Sie, wie die Funktion "Failwith" F#-Ausnahme generiert.
ms.date: 05/16/2016
ms.openlocfilehash: 08107966ddc2f55625347deb92d224b286df7761
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641947"
---
# <a name="exceptions-the-failwith-function"></a>Ausnahmen: Die failwith-Funktion

Die `failwith` -Funktion generiert eine F# Ausnahme.

## <a name="syntax"></a>Syntax

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Hinweise

Die *Fehlermeldungszeichenfolge* in der vorherigen Syntax ist ein Zeichenfolgenliteral oder ein Wert vom Typ `string`. Es wird die `Message` -Eigenschaft der Ausnahme.

Die Ausnahme, die vom generierten `failwith` ist eine `System.Exception` Ausnahme aus, die ein Verweis ist mit dem Namen `Failure` in F# Code. Der folgende Code veranschaulicht die Verwendung von `failwith` eine Ausnahme ausgelöst.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Die `try...with` Ausdruck](the-try-with-expression.md)
- [Ausnahmen: Die `try...finally` Ausdruck](the-try-finally-expression.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
