---
title: "\"Is\" erfordert Operanden, die Verweistypen haben. Dieser Operand hat jedoch den Werttyp \"<typename>\"."
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 5c9f156272cd0c3cbaeadbc0e162129f41619cc6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163349"
---
# <a name="bc30020-is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a>BC30020: "is" erfordert Operanden, die Verweis Typen haben. dieser Operand hat jedoch den Werttyp " \<typename> ".

Der `Is` Vergleichs Operator bestimmt, ob zwei Objektvariablen auf dieselbe Instanz verweisen. Dieser Vergleich ist für Werttypen nicht definiert.

 **Fehler-ID:** BC30020

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Verwenden Sie den entsprechenden arithmetischen Vergleichs Operator oder den- `Like` Operator, um zwei Werttypen zu vergleichen.

## <a name="see-also"></a>Siehe auch

- [Is-Operator](../operators/is-operator.md)
- [Like-Operator](../operators/like-operator.md)
- [Comparison Operators (Vergleichsoperatoren)](../operators/comparison-operators.md)
