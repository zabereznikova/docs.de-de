---
title: 'Schleifen: for...to-Ausdruck'
description: Siehe How F# for... to-Ausdruck wird zum Durchlaufen einer Schleife über einen Wertebereich einer Schleifen Variablen verwendet.
ms.date: 05/16/2016
ms.openlocfilehash: 910c04aa4ea6b2c637dcad147347c1c317b5e0c0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626629"
---
# <a name="loops-forto-expression"></a>Schleifen: for...to-Ausdruck

Der `for...to` Ausdruck wird zum Durchlaufen einer Schleife über einen Wertebereich einer Schleifen Variablen verwendet.

## <a name="syntax"></a>Syntax

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Hinweise

Der Typ des Bezeichners wird vom Typ der Ausdrücke zum *starten* und *Beenden* abgeleitet. Typen für diese Ausdrücke müssen 32-Bit-Ganzzahlen sein.

Obwohl es sich technisch gesehen `for...to` um einen Ausdruck handelt, ähnelt dies einer herkömmlichen Anweisung in einer imperativen Programmiersprache. Der Rückgabetyp für den *Text Ausdruck* muss `unit`lauten. In den folgenden Beispielen werden verschiedene Verwendungen `for...to` des-Ausdrucks veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Der obige Code gibt Folgendes aus.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Loops `for...in`Begriff](loops-for-in-expression.md)
- [Loops `while...do`Begriff](loops-while-do-expression.md)
