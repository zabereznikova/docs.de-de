---
title: "Verzögerte Berechnungen (F#)"
description: "Erfahren Sie, wie die Leistung Ihrer apps und Bibliotheken von f# verzögerte Berechnungen verbessert werden können."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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

Um die Berechnung ausgeführt werden zu erzwingen, rufen Sie die Methode `Force`. `Force`bewirkt, dass die Ausführung nur einmal ausgeführt werden. Nachfolgende Aufrufe `Force` zurückgeben identisch zu, wobei jedoch keinen Code nicht ausgeführt.

Der folgende Code veranschaulicht die Verwendung der verzögerten Berechnung und die Verwendung von `Force`. In diesem Code wird der Typ des `result` ist `Lazy<int>`, und die `Force` Methode gibt ein `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

Verzögerte Auswertung jedoch nicht die `Lazy` eingeben, wird auch für Sequenzen verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md).

## <a name="see-also"></a>Siehe auch

[F#-Sprachreferenz](index.md)

[LazyExtensions-Modul](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
