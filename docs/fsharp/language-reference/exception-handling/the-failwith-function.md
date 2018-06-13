---
title: 'Ausnahmen: Die failwith-Funktion (F#)'
description: Erfahren Sie, wie die Funktion "Failwith" f#-Ausnahme generiert.
ms.date: 05/16/2016
ms.openlocfilehash: 59f7129faf38668dd7390790e22d25f37c129750
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563327"
---
# <a name="exceptions-the-failwith-function"></a>Ausnahmen: Die failwith-Funktion

Die `failwith` Funktion generiert eine f#-Ausnahme.


## <a name="syntax"></a>Syntax

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Hinweise
Die *Fehlermeldungszeichenfolge* in der vorherigen Syntax ist eine Literalzeichenfolge oder ein Wert vom Typ `string`. Es wird die `Message` -Eigenschaft der Ausnahme.

Die Ausnahme, die vom generierten `failwith` ist ein `System.Exception` Ausnahme aus, die ein Verweis ist mit dem Namen `Failure` in f#-Code. Der folgende Code veranschaulicht die Verwendung von `failwith` eine Ausnahme auslöst.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]
    
## <a name="see-also"></a>Siehe auch
[Ausnahmebehandlung](index.md)

[Ausnahmetypen](exception-types.md)

[Ausnahmen: Der `try...with`-Ausdruck](the-try-with-expression.md)

[Ausnahmen: Der `try...finally`-Ausdruck](the-try-finally-expression.md)

[Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
