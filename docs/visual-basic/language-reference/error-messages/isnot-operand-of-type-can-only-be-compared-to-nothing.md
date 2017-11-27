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
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="f709a-102">&#39; IsNot &#39; der Operand vom Typ &#39; Typename &#39; nur verglichen werden können, um &#39; ' Nothing ' &#39; da &#39; Typename &#39; ist ein NULL-Werte zulässt</span><span class="sxs-lookup"><span data-stu-id="f709a-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="f709a-103">Eine Variable, die als auf NULL festlegbar deklariert wurde wurde im Vergleich zu einem Ausdruck außer `Nothing` mithilfe der `IsNot` Operator.</span><span class="sxs-lookup"><span data-stu-id="f709a-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="f709a-104">**Fehler-ID:** BC32128</span><span class="sxs-lookup"><span data-stu-id="f709a-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f709a-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f709a-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="f709a-106">Außer den nullable-Typ in einen Ausdruck vergleichen `Nothing` mithilfe der `IsNot` -Operator, rufen die `GetType` Methode für die nullable-Typ und vergleichen das Ergebnis mit dem Ausdruck, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f709a-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="f709a-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f709a-107">See Also</span></span>  
 [<span data-ttu-id="f709a-108">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="f709a-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="f709a-109">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="f709a-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
