---
title: 'Schleifen: for...to-Ausdruck (F#)'
description: Finden Sie unter wie der F#-for..-Ausdruck wird verwendet, um einen Bereich der Werte einer Schleifenvariablen in einer Schleife zu durchlaufen.
ms.date: 05/16/2016
ms.openlocfilehash: 8160fd30c4f3afe8bb6b58f468802ef1c0ef32ee
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43800468"
---
# <a name="loops-forto-expression"></a>Schleifen: for...to-Ausdruck

Die `for...to` Ausdruck wird verwendet, um einen Bereich der Werte einer Schleifenvariablen in einer Schleife zu durchlaufen.

## <a name="syntax"></a>Syntax

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Hinweise

Der Typ des Bezeichners wird abgeleitet, vom Typ des der *starten* und *Fertig stellen* Ausdrücke. Typen, die für diese Ausdrücke müssen es sich um 32-Bit-Ganzzahlen sein.

Obwohl technisch gesehen ist ein Ausdruck, `for...to` eher wie eine herkömmliche Anweisung in einem imperativen Programmiersprache. Der Rückgabetyp für die *Body-Ausdruck* muss `unit`. Die folgenden Beispiele zeigen verschiedene Verwendungsmöglichkeiten der der `for...to` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Der obige Code gibt Folgendes aus.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Schleifen: `for...in`-Ausdruck](loops-for-in-expression.md)
- [Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)
