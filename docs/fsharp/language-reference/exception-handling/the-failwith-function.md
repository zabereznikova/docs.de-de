---
title: 'Ausnahmen: Die failwith-Funktion (F#)'
description: Erfahren Sie, wie die Funktion "Failwith" f#-Ausnahme generiert.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2e0c1f28-cc6c-4ecd-bb93-3816c4dd7cd3
ms.openlocfilehash: 295a4d754e0df015ba67daa9cf80d7df5b40199c
ms.sourcegitcommit: ffb9aa26cd5211dc6d96ebb42968d8357048880e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2017
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
