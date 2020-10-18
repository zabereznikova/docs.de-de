---
title: Die geschachtelte Funktion verfügt über keine Signatur, die mit dem Delegaten '<delegatename>' kompatibel ist
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 0dde340164f1ba80d0e1d9fbb5d17ba6da0a5bc4
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160053"
---
# <a name="bc36532-nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>BC36532: die in der Funktion "" unterstützt keine Signatur, die mit dem Delegaten "" kompatibel ist. \<delegatename>

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

## <a name="see-also"></a>Siehe auch

- [Gelockerte Delegatenkonvertierung](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md)
