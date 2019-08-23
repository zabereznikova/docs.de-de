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
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917221"
---
# <a name="is-operator-visual-basic"></a>Is-Operator (Visual Basic)
Vergleicht zwei Objekt Verweis Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Ein `Boolean` beliebiger Wert.  
  
 `object1`  
 Erforderlich. Ein `Object` beliebiger Name.  
  
 `object2`  
 Erforderlich. Ein `Object` beliebiger Name.  
  
## <a name="remarks"></a>Hinweise  
 Der `Is` -Operator bestimmt, ob zwei Objekt Verweise auf das gleiche Objekt verweisen. Es werden jedoch keine Wert Vergleiche durchgeführt. Wenn `object1` `result` und `result` `False`beide auf genau`True`dieselbe Objektinstanz verweisen, ist. andernfalls ist der Wert. `object2`  
  
 `Is`kann auch mit dem `TypeOf` -Schlüsselwort verwendet werden, um eine `TypeOf`zu erstellen... `Is` Ausdruck, der testet, ob eine Objekt Variable mit einem Datentyp kompatibel ist.  
  
> [!NOTE]
> Das `Is` Schlüsselwort wird auch im [SELECT... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `Is` -Operator verwendet, um Paare von Objekt verweisen zu vergleichen. Die Ergebnisse werden einem `Boolean` Wert zugewiesen, der angibt, ob die beiden-Objekte identisch sind.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Wie das vorherige Beispiel zeigt, können Sie den `Is` -Operator verwenden, um früh gebundene und spät gebundene Objekte zu testen.  
  
## <a name="see-also"></a>Siehe auch

- [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Vergleichs Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
