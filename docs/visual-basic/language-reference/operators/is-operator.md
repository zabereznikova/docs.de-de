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
ms.openlocfilehash: 0351d224d9bf08a8f3ca74090de7b9c51c2c61bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701364"
---
# <a name="is-operator-visual-basic"></a>Is-Operator (Visual Basic)
Vergleicht zwei Objekt Verweis Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean`-Werte.  
  
 `object1`  
 Erforderlich. Alle `Object`-Namen.  
  
 `object2`  
 Erforderlich. Alle `Object`-Namen.  
  
## <a name="remarks"></a>Hinweise  
 Der `Is`-Operator bestimmt, ob zwei Objekt Verweise auf das gleiche Objekt verweisen. Es werden jedoch keine Wert Vergleiche durchgeführt. Wenn `object1` und `object2` auf genau dieselbe Objektinstanz verweisen, `result` `True`; Wenn dies nicht der Fall ist, ist `result` `False`.  
  
 `Is` kann auch mit dem Schlüsselwort `TypeOf` verwendet werden, um einen `TypeOf`... `Is`-Ausdruck zu erstellen, der testet, ob eine Objekt Variable mit einem Datentyp kompatibel ist.  
  
> [!NOTE]
> Das Schlüsselwort "`Is`" wird auch im [SELECT... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `Is`-Operator verwendet, um Paare von Objekt verweisen zu vergleichen. Die Ergebnisse werden einem `Boolean`-Wert zugewiesen, der angibt, ob die beiden-Objekte identisch sind.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Wie das vorherige Beispiel zeigt, können Sie den `Is`-Operator verwenden, um früh gebundene und spät gebundene Objekte zu testen.  
  
## <a name="see-also"></a>Siehe auch

- [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Vergleichs Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
