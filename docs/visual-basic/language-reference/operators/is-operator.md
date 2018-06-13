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
ms.openlocfilehash: 8beca1dc8788514224f70cacc5b8ede0974f5230
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601949"
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
 Die `Is` -Operator ermittelt, ob zwei Objektverweise auf dasselbe Objekt verweisen. Er führt jedoch keine Wertvergleiche. Wenn `object1` und `object2` beide verweisen auf genau dieselbe Objektinstanz, `result` ist `True`; Wenn sie keinen `result` ist `False`.  
  
 `Is` kann auch verwendet werden, mit der `TypeOf` Schlüsselwort stellen eine `TypeOf`... `Is` Ausdruck, der testet, ob eine Objektvariable mit dem Datentyp kompatibel ist.  
  
> [!NOTE]
>  Die `Is` Schlüsselwort werden auch in der [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Is` Operator, um Paare von Objektverweisen zu vergleichen. Die Ergebnisse zugewiesen sind eine `Boolean` Wert darstellt, ob die beiden Objekte identisch sind.  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 Wie im vorherige Beispiel veranschaulicht, können Sie die `Is` Operator, um beide testen früh gebundener Aufruf und spät gebundene Objekte.  
  
## <a name="see-also"></a>Siehe auch  
 [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
