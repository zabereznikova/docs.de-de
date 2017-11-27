---
title: 'Ausnahmen: Die invalidArg-Funktion (F#)'
description: Erfahren Sie, wie 'InvalidArg'-Funktion [F#] eine Argumentausnahme generiert.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d375b704-6b27-493e-bd1d-ee217a53c4b5
ms.openlocfilehash: 107bef361a6bd034e3d6a2227e18cf64b1b04576
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
