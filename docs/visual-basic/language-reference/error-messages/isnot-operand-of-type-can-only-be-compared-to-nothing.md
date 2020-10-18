---
title: Ein IsNot-Operand vom Typ „Typname“ kann nur mit „Nothing“ verglichen werden, da „Typname“ ein Typ ist, der NULL-Werte zulässt
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 084978c1e047eebd60149af63c0ec9a1135225be
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163336"
---
# <a name="bc32128-isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a>BC32128: Ein IsNot-Operand vom Typ "Typname" kann nur mit "Nothing" verglichen werden, da "Typname" ein Typ ist, der NULL-Werte zulässt.

Eine Variable, die als Werte zulässt-Werttyp deklariert wurde, wurde mit einem anderen Ausdruck als `Nothing` mit dem- `IsNot` Operator verglichen.

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

- [Auf NULL festlegbare Werttypen](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [IsNot-Operator](../operators/isnot-operator.md)
