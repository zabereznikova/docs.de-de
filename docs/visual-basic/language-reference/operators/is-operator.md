---
title: Is-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: a59ff4c956724c614342f0ee4c0622a67f1c25e7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817070"
---
# <a name="is-operator-visual-basic"></a>Is-Operator (Visual Basic)
Vergleicht zwei Objektverweisvariablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` Wert.  
  
 `object1`  
 Erforderlich. Alle `Object` Name.  
  
 `object2`  
 Erforderlich. Alle `Object` Name.  
  
## <a name="remarks"></a>Hinweise  
 Die `Is` -Operator ermittelt, ob zwei Objektverweise auf dasselbe Objekt verweisen. Er führt jedoch keine vergleichen. Wenn `object1` und `object2` beide verweisen auf genau dieselbe Objektinstanz, `result` ist `True`; Wenn dies nicht der Fall `result` ist `False`.  
  
 `Is` kann auch verwendet werden, mit der `TypeOf` Schlüsselwort, um die stellen eine `TypeOf`... `Is` Ausdruck, der testet, ob es sich bei eine Objektvariablen mit dem Datentyp kompatibel ist.  
  
> [!NOTE]
>  Die `Is` -Schlüsselwort wird auch verwendet, der [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Is` Operator, um Paare von Objektverweisen zu vergleichen. Die Ergebnisse zugewiesen sind eine `Boolean` darstellt, ob die beiden Objekte identisch sind.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Wie im vorherige Beispiel wird veranschaulicht, können Sie die `Is` Operator, um sowohl eine frühe Bindung und spät gebundene Objekte.  
  
## <a name="see-also"></a>Siehe auch

- [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
