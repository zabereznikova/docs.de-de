---
title: Ein IsNot-Operand vom Typ „Typname“ kann nur mit „Nothing“ verglichen werden, da „Typname“ ein Typ ist, der NULL-Werte zulässt
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: caa009606825225dd4063780f9a22fb82f21cf4e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271288"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="c170c-102">Ein IsNot-Operand vom Typ „Typname“ kann nur mit „Nothing“ verglichen werden, da „Typname“ ein Typ ist, der NULL-Werte zulässt</span><span class="sxs-lookup"><span data-stu-id="c170c-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>
<span data-ttu-id="c170c-103">Eine Variable, die als auf NULL festlegbar deklariert wurde nicht auf einen Ausdruck verglichen wurde `Nothing` mithilfe der `IsNot` Operator.</span><span class="sxs-lookup"><span data-stu-id="c170c-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="c170c-104">**Fehler-ID:** BC32128</span><span class="sxs-lookup"><span data-stu-id="c170c-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c170c-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c170c-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="c170c-106">Um einen Typ, der NULL zulässt, mithilfe des `Nothing` -Operators mit einem anderen Ausdruck als `IsNot` zu vergleichen, rufen Sie die `GetType` -Methode für den Typ, der NULL zulässt, auf und vergleichen das Ergebnis mit dem Ausdruck, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c170c-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="c170c-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c170c-107">See also</span></span>
- [<span data-ttu-id="c170c-108">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="c170c-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="c170c-109">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="c170c-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
