---
title: '&#39;IsNot&#39; -Operand vom Typ &#39;Typename&#39; kann nur mit der verglichen werden &#39;nichts&#39;, da &#39;Typename&#39; ist ein NULL-Werte zulässt'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 65b04c85bccd169bbb2eea847d7b8af96c1a292f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505717"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39;IsNot&#39; -Operand vom Typ &#39;Typename&#39; kann nur mit der verglichen werden &#39;nichts&#39;, da &#39;Typename&#39; ist ein NULL-Werte zulässt
Eine Variable, die als auf NULL festlegbar deklariert wurde nicht auf einen Ausdruck verglichen wurde `Nothing` mithilfe der `IsNot` Operator.  
  
 **Fehler-ID:** BC32128  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Um einen Typ, der NULL zulässt, mithilfe des `Nothing` -Operators mit einem anderen Ausdruck als `IsNot` zu vergleichen, rufen Sie die `GetType` -Methode für den Typ, der NULL zulässt, auf und vergleichen das Ergebnis mit dem Ausdruck, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>Siehe auch
- [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
