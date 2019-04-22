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
ms.openlocfilehash: 5e534eac2300327d4c54c5ce93d8b2c6c538e794
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832493"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="7112d-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7112d-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="7112d-103">Gibt an, dass ein Argument so übergeben wird, dass die aufgerufene Prozedur oder Eigenschaft den Wert einer Variablen mit dem zugrunde liegenden Arguments im aufrufenden Code nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="7112d-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7112d-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7112d-104">Remarks</span></span>  
 <span data-ttu-id="7112d-105">Der `ByVal`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="7112d-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="7112d-106">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7112d-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="7112d-107">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7112d-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="7112d-108">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7112d-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="7112d-109">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7112d-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="7112d-110">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7112d-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="7112d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7112d-111">Example</span></span>  
 <span data-ttu-id="7112d-112">Das folgende Beispiel zeigt die Verwendung der `ByVal` Mechanismus, mit einem Verweis Typargument übergeben von Parametern.</span><span class="sxs-lookup"><span data-stu-id="7112d-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="7112d-113">Im Beispiel ist das Argument ist `c1`, eine Instanz der Klasse `Class1`.</span><span class="sxs-lookup"><span data-stu-id="7112d-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="7112d-114">`ByVal` verhindert, dass den Code in den Verfahren ändern den zugrunde liegenden Wert des Arguments Verweis `c1`, aber nicht die verfügbare Felder und Eigenschaften der schützt `c1`.</span><span class="sxs-lookup"><span data-stu-id="7112d-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="7112d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7112d-115">See also</span></span>

- [<span data-ttu-id="7112d-116">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7112d-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="7112d-117">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="7112d-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
