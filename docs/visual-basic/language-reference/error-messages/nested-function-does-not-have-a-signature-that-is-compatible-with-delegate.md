---
title: Die geschachtelte Funktion verfügt über keine Signatur, die mit dem Delegaten '<delegatename>' kompatibel ist
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 28d07f01c0fd467cb68d73749988273eee95edf4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409425"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>Die geschachtelte Funktion verfügt über keine Signatur, die mit dem Delegaten '\<delegatename>' kompatibel ist

Ein Lambda-Ausdruck wurde einem Delegaten zugewiesen, der über eine inkompatible Signatur verfügt. Im folgenden Code verfügt der Delegat beispielsweise `Del` über zwei ganzzahlige Parameter.

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

Der Fehler wird ausgelöst, wenn ein Lambda-Ausdruck mit einem Argument als Typ deklariert wird `Del` :

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

**Fehler-ID:** BC36532

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Passen Sie entweder die Delegatdefinition oder den zugewiesenen Lambda-Ausdruck so an, dass die Signaturen kompatibel sind.

## <a name="see-also"></a>Weitere Informationen

- [Gelockerte Delegatenkonvertierung](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md)
