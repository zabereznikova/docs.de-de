---
title: "&#39; IsNot &#39; der Operand vom Typ &#39; Typename &#39; nur verglichen werden können, um &#39; ' Nothing ' &#39; da &#39; Typename &#39; ist ein NULL-Werte zulässt"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords: BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec0ae1561bfbee998e7c65f6023012c0f982a8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39; IsNot &#39; der Operand vom Typ &#39; Typename &#39; nur verglichen werden können, um &#39; ' Nothing ' &#39; da &#39; Typename &#39; ist ein NULL-Werte zulässt
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
