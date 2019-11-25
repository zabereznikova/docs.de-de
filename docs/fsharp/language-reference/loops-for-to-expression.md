---
title: 'Schleifen: for...to-Ausdruck'
description: Siehe How F# for... to-Ausdruck wird zum Durchlaufen einer Schleife über einen Wertebereich einer Schleifen Variablen verwendet.
ms.date: 05/16/2016
ms.openlocfilehash: 882b6e48dd09efcb57f7ef2f419e68a6c43393a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283904"
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

Obwohl es sich technisch gesehen um einen Ausdruck handelt, ist `for...to` eher mit einer herkömmlichen Anweisung in einer imperativen Programmiersprache vergleichbar. Der Rückgabetyp für den *Text Ausdruck* muss `unit`werden. In den folgenden Beispielen werden verschiedene Verwendungen des `for...to` Ausdrucks veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Der obige Code gibt Folgendes aus.

```console
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Schleifen: `for...in`-Ausdruck](loops-for-in-expression.md)
- [Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)
