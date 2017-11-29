---
title: IsNot-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.isnot
helpviewer_keywords: IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
 Erforderlich. Alle `Object` Variable oder ein Ausdruck.  
  
 `object2`  
 Erforderlich. Alle `Object` Variable oder ein Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Die `IsNot` -Operator ermittelt, ob zwei Objektverweise auf unterschiedliche Objekte verweisen. Er führt jedoch keine Wertvergleiche. Wenn `object1` und `object2` beide verweisen auf genau dieselbe Objektinstanz, `result` ist `False`; Wenn sie keinen `result` ist `True`.  
  
 `IsNot`ist das Gegenteil von der `Is` Operator. Der Vorteil der `IsNot` ist, dass Sie vermeiden können, umständliche Syntax mit `Not` und `Is`, die schwer zu lesen sein können.  
  
 Sie können die `Is` und `IsNot` Operatoren, um früh gebundene und spät gebundene Objekte zu testen.  
  
> [!NOTE]
>  Die `IsNot` Operator kann nicht verwendet werden, um das Vergleichen von Ausdrücken, die zurückgegeben werden, aus der `TypeOf` Operator. Stattdessen müssen Sie verwenden die `Not` und `Is` Operatoren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel verwendet die `Is` Operator und die `IsNot` Operator, um denselben Vergleich zu erreichen.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)  
 [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Gewusst wie: Überprüfen, ob zwei Objekte identisch sind](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
