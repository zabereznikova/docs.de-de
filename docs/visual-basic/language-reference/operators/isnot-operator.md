---
title: IsNot-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ea978f8874cee20fb3a005189fd846f7564da777
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811040"
---
# <a name="isnot-operator-visual-basic"></a>IsNot-Operator (Visual Basic)

Vergleicht zwei Objekt Verweis Variablen.

## <a name="syntax"></a>Syntax

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Bestandteile

- `result`

  Erforderlich. Ein `Boolean`-Wert.

- `object1`

  Erforderlich. Eine beliebige `Object` Variable oder ein Ausdruck.

- `object2`

  Erforderlich. Eine beliebige `Object` Variable oder ein Ausdruck.

## <a name="remarks"></a>Hinweise

Der- `IsNot` Operator bestimmt, ob zwei Objekt Verweise auf unterschiedliche Objekte verweisen. Es werden jedoch keine Wert Vergleiche durchgeführt. Wenn `object1` und `object2` beide auf genau dieselbe Objektinstanz verweisen, ist `result` . wenn dies nicht der Fall ist `False` , `result` ist `True` .

`IsNot` ist das Gegenteil des- `Is` Operators. Der Vorteil von `IsNot` besteht darin, dass Sie eine umständliche Syntax mit und vermeiden können `Not` `Is` , was schwierig zu lesen ist.

 Sie können die `Is` `IsNot` Operatoren und verwenden, um früh gebundene und spät gebundene Objekte zu testen.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird der `Is` -Operator und der `IsNot` -Operator verwendet, um denselben Vergleich durchzuführen.

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a>Typeof-Operator mit IsNot-Operator verwenden

Ab Visual Basic 14 können Sie den- `TypeOf` Operator mit dem-Operator verwenden, `IsNot` um zu testen, ob ein Objekt *nicht* mit einem-Datentyp kompatibel ist. Beispiel:

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a>Siehe auch

- [Is-Operator](is-operator.md)
- [Typeof-Operator](typeof-operator.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Vorgehensweise: Überprüfen, ob zwei Objekte identisch sind](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
