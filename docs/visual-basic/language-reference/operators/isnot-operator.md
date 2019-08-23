---
title: IsNot-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966927"
---
# <a name="isnot-operator-visual-basic"></a>IsNot-Operator (Visual Basic)
Vergleicht zwei Objekt Verweis Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Ein `Boolean`-Wert.  
  
 `object1`  
 Erforderlich. Eine `Object` beliebige Variable oder ein Ausdruck.  
  
 `object2`  
 Erforderlich. Eine `Object` beliebige Variable oder ein Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Der `IsNot` -Operator bestimmt, ob zwei Objekt Verweise auf unterschiedliche Objekte verweisen. Es werden jedoch keine Wert Vergleiche durchgeführt. Wenn `object1` `result` und `result` `True`beide auf genau`False`dieselbe Objektinstanz verweisen, ist. andernfalls ist der Wert. `object2`  
  
 `IsNot`ist das Gegenteil des `Is` -Operators. Der Vorteil von `IsNot` besteht darin, dass Sie eine umständliche `Not` Syntax `Is`mit und vermeiden können, was schwierig zu lesen ist.  
  
 Sie können die `Is` Operatoren `IsNot` und verwenden, um früh gebundene und spät gebundene Objekte zu testen.  
  
> [!NOTE]
> Der `IsNot` Operator kann nicht zum Vergleichen von Ausdrücken verwendet werden, `TypeOf` die vom Operator zurückgegeben werden. Stattdessen müssen Sie die `Not` Operatoren und `Is` verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird der `Is` `IsNot` -Operator und der-Operator verwendet, um denselben Vergleich durchzuführen.  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>Siehe auch

- [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)
- [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Vorgehensweise: Testen, ob zwei Objekte identisch sind](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
