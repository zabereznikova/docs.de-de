---
title: Ein IsNot-Operand vom Typ „Typname“ kann nur mit „Nothing“ verglichen werden, da „Typname“ ein Typ ist, der NULL-Werte zulässt
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 1660971e2a1a11d7a2d14f222cd149edf4aa4c7b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249512"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a>Ein IsNot-Operand vom Typ „Typname“ kann nur mit „Nothing“ verglichen werden, da „Typname“ ein Typ ist, der NULL-Werte zulässt

Eine Variable, die als NULL-Werttyp deklariert wurde, wurde mit einem anderen Ausdruck als `Nothing` der Verwendung des `IsNot` Operators verglichen.

**Fehler-ID:** BC32128

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Um einen Typ, der NULL zulässt, mithilfe des `Nothing` -Operators mit einem anderen Ausdruck als `IsNot` zu vergleichen, rufen Sie die `GetType` -Methode für den Typ, der NULL zulässt, auf und vergleichen das Ergebnis mit dem Ausdruck, wie im folgenden Beispiel gezeigt.

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a>Siehe auch

- [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
