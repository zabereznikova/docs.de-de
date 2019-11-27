---
title: Is-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 52fbb39ab0a36c8b947b78f464fad26be05ce204
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349534"
---
# <a name="is-operator-visual-basic"></a>Is-Operator (Visual Basic)
Vergleicht zwei Objekt Verweis Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a>-Komponenten  
 `result`  
 Erforderlich Ein beliebiger `Boolean` Wert.  
  
 `object1`  
 Erforderlich Jeder `Object` Name.  
  
 `object2`  
 Erforderlich Jeder `Object` Name.  
  
## <a name="remarks"></a>Hinweise  
 Der `Is`-Operator bestimmt, ob zwei Objekt Verweise auf das gleiche Objekt verweisen. Es werden jedoch keine Wert Vergleiche durchgeführt. Wenn `object1` und `object2` beide auf genau dieselbe Objektinstanz verweisen, ist `result` `True`. Wenn dies nicht der Fall ist, wird `result` `False`.  
  
 `Is` können auch mit dem Schlüsselwort `TypeOf` verwendet werden, um einen `TypeOf`...`Is` Ausdruck zu erstellen, der testet, ob eine Objekt Variable mit einem Datentyp kompatibel ist.  
  
> [!NOTE]
> Das `Is`-Schlüsselwort wird auch im [SELECT... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `Is`-Operator verwendet, um Paare von Objekt verweisen zu vergleichen. Die Ergebnisse werden einem `Boolean` Wert zugewiesen, der angibt, ob die beiden-Objekte identisch sind.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Wie das vorherige Beispiel zeigt, können Sie den `Is`-Operator verwenden, um früh gebundene und spät gebundene Objekte zu testen.  
  
## <a name="see-also"></a>Siehe auch

- [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Vergleichs Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
