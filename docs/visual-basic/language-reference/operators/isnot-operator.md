---
title: IsNot-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336064"
---
# <a name="isnot-operator-visual-basic"></a>IsNot-Operator (Visual Basic)

Vergleicht zwei Objekt Verweis Variablen.

## <a name="syntax"></a>Syntax

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>-Komponenten
 `result` ist erforderlich. Ein `Boolean`-Wert.

 `object1` ist erforderlich. Beliebige `Object` Variable oder Ausdruck.

 `object2` ist erforderlich. Beliebige `Object` Variable oder Ausdruck.

## <a name="remarks"></a>Hinweise
 Der `IsNot`-Operator bestimmt, ob zwei Objekt Verweise auf unterschiedliche Objekte verweisen. Es werden jedoch keine Wert Vergleiche durchgeführt. Wenn `object1` und `object2` beide auf genau dieselbe Objektinstanz verweisen, ist `result` `False`. Wenn dies nicht der Fall ist, wird `result` `True`.

 `IsNot` ist das Gegenteil des `Is`-Operators. Der Vorteil von `IsNot` besteht darin, dass Sie eine umständliche Syntax mit `Not` und `Is`vermeiden können, was schwierig zu lesen ist.

 Mit den Operatoren `Is` und `IsNot` können Sie sowohl früh gebundene als auch spät gebundene Objekte testen.

## <a name="example"></a>Beispiel
 Im folgenden Codebeispiel werden sowohl der `Is`-Operator als auch der `IsNot`-Operator verwendet, um denselben Vergleich durchzuführen.

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>Siehe auch

- [Is-Operator](is-operator.md)
- [TypeOf-Operator](typeof-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](operator-precedence.md)
- [Gewusst wie: Überprüfen, ob zwei Objekte identisch sind](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
