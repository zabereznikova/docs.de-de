---
title: Verzögerte Berechnungen (F#)
description: Erfahren Sie, wie die Leistung Ihrer apps und Bibliotheken von f# verzögerte Berechnungen verbessert werden können.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 72dc5a14a845b52ae2512314d730516ca0cf4b9d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="lazy-computations"></a>Verzögerte Berechnungen

*Verzögerte Berechnungen* sind Berechnungen, die nicht sofort ausgewertet werden, sondern werden stattdessen ausgewertet, wenn das Ergebnis benötigt wird. Dadurch können um die Leistung des Codes zu verbessern.

## <a name="syntax"></a>Syntax

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Ausdruck* ist Code, der ausgewertet wird, nur, wenn ein Ergebnis erforderlich ist und *Bezeichner* ist ein Wert, der das Ergebnis speichert. Der Wert ist vom Typ [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in dem die tatsächlichen eingeben, die verwendet wird, für `'T` wird über das Ergebnis des Ausdrucks bestimmt.

Verzögerte Berechnungen ermöglichen es Ihnen, Verbessern der Leistung durch Einschränken der Ausführung einer Berechnung auf nur die Fälle, in denen ein Ergebnis benötigt wird.

Um die Berechnung ausgeführt werden zu erzwingen, rufen Sie die Methode `Force`. `Force` bewirkt, dass die Ausführung nur einmal ausgeführt werden. Nachfolgende Aufrufe `Force` zurückgeben identisch zu, wobei jedoch keinen Code nicht ausgeführt.

Der folgende Code veranschaulicht die Verwendung der verzögerten Berechnung und die Verwendung von `Force`. In diesem Code wird der Typ des `result` ist `Lazy<int>`, und die `Force` Methode gibt ein `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Verzögerte Auswertung jedoch nicht die `Lazy` eingeben, wird auch für Sequenzen verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md).

## <a name="see-also"></a>Siehe auch

[F#-Sprachreferenz](index.md)

[LazyExtensions-Modul](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
