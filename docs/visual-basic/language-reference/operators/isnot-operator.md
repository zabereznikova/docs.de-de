---
title: IsNot-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: e07a775eec003a3e488f6909181aed3f742b4b91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768346"
---
# <a name="isnot-operator-visual-basic"></a>IsNot-Operator (Visual Basic)
Vergleicht zwei Objektverweisvariablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Ein `Boolean`-Wert.  
  
 `object1`  
 Erforderlich. Alle `Object` Variable oder einen Ausdruck.  
  
 `object2`  
 Erforderlich. Alle `Object` Variable oder einen Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Die `IsNot` -Operator ermittelt, ob zwei Objektverweise auf unterschiedliche Objekte verweisen. Er führt jedoch keine vergleichen. Wenn `object1` und `object2` beide verweisen auf genau dieselbe Objektinstanz, `result` ist `False`; Wenn dies nicht der Fall `result` ist `True`.  
  
 `IsNot` ist das Gegenteil von dem `Is` Operator. Der Vorteil der `IsNot` besteht darin, dass Sie das umständlich Syntax mit vermeiden können `Not` und `Is`, die schwierig zu lesen sein können.  
  
 Sie können die `Is` und `IsNot` Abfrageoperatoren, um sowohl früh gebundenen und spät gebundenen Objekte zu testen.  
  
> [!NOTE]
>  Die `IsNot` Operator kann nicht verwendet werden, zum Vergleich von Ausdrücken, die zurückgegeben werden, aus der `TypeOf` Operator. Sie müssen stattdessen die `Not` und `Is` Operatoren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel verwendet die `Is` Operator und die `IsNot` Operator, um denselben Vergleich.  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>Siehe auch

- [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)
- [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Vorgehensweise: Überprüfen Sie, ob zwei Objekte gleich sind.](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
