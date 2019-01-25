---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 6fa87db4fbab961dd1aa526e2ac8ff15b031005b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650079"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="e3314-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3314-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="e3314-103">Gibt an, dass ein Argument so übergeben wird, dass die aufgerufene Prozedur oder Eigenschaft den Wert einer Variablen mit dem zugrunde liegenden Arguments im aufrufenden Code nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="e3314-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3314-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3314-104">Remarks</span></span>  
 <span data-ttu-id="e3314-105">Der `ByVal`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e3314-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e3314-106">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e3314-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="e3314-107">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e3314-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e3314-108">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e3314-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="e3314-109">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e3314-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e3314-110">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e3314-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="e3314-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3314-111">Example</span></span>  
 <span data-ttu-id="e3314-112">Das folgende Beispiel zeigt die Verwendung der `ByVal` Mechanismus, mit einem Verweis Typargument übergeben von Parametern.</span><span class="sxs-lookup"><span data-stu-id="e3314-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="e3314-113">Im Beispiel ist das Argument ist `c1`, eine Instanz der Klasse `Class1`.</span><span class="sxs-lookup"><span data-stu-id="e3314-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="e3314-114">`ByVal` verhindert, dass den Code in den Verfahren ändern den zugrunde liegenden Wert des Arguments Verweis `c1`, aber nicht die verfügbare Felder und Eigenschaften der schützt `c1`.</span><span class="sxs-lookup"><span data-stu-id="e3314-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e3314-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3314-115">See also</span></span>
- [<span data-ttu-id="e3314-116">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e3314-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="e3314-117">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="e3314-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
