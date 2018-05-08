---
title: '&#39;IsNot&#39; -Operand vom Typ &#39;Typename&#39; nur verglichen werden können, um &#39;nichts&#39;, da &#39;Typename&#39; ist ein NULL-Werte zulässt'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 44cc17c73b476e5e322b9b58b021bc7bcd63167f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39;IsNot&#39; -Operand vom Typ &#39;Typename&#39; nur verglichen werden können, um &#39;nichts&#39;, da &#39;Typename&#39; ist ein NULL-Werte zulässt
Eine Variable, die als auf NULL festlegbar deklariert wurde wurde im Vergleich zu einem Ausdruck außer `Nothing` mithilfe der `IsNot` Operator.  
  
 **Fehler-ID:** BC32128  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Außer den nullable-Typ in einen Ausdruck vergleichen `Nothing` mithilfe der `IsNot` -Operator, rufen die `GetType` Methode für die nullable-Typ und vergleichen das Ergebnis mit dem Ausdruck, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
