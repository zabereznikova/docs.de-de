---
title: 'Schleifen: for...to-Ausdruck (F#)'
description: Finden Sie unter wie die f#-for... in Ausdruck verwendet, um einen Wertebereich einer Schleifenvariablen in einer Schleife zu durchlaufen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 95a8960d71c82c01118d2e71479fc0ec5298a02b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forto-expression"></a>Schleifen: for...to-Ausdruck

Die `for...to` Ausdruck wird verwendet, um einen Wertebereich einer Schleifenvariablen in einer Schleife zu durchlaufen.


## <a name="syntax"></a>Syntax

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Hinweise
Der Typ des Bezeichners wird abgeleitet, von dem Typ des der *starten* und *Fertig stellen* Ausdrücke. Typen, die für diese Ausdrücke müssen 32-Bit-Ganzzahlen sein.

Obwohl technisch gesehen ist ein Ausdruck, `for...to` ist eher wie eine herkömmliche Anweisung in einem imperativen Programmiersprache ab. Der Rückgabetyp für die *Text-Ausdruck* muss `unit`. Die folgenden Beispiele zeigen verschiedene Verwendungsmöglichkeiten der der `for...to` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Der obige Code gibt Folgendes aus.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Schleifen: `for...in`-Ausdruck](loops-for-in-expression.md)

[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)
