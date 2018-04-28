---
title: 'Ausnahmen: Die failwith-Funktion (F#)'
description: Erfahren Sie, wie die Funktion "Failwith" f#-Ausnahme generiert.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: af1e3b7dc96b3b822e2e19b7bac435940d15922f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
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
