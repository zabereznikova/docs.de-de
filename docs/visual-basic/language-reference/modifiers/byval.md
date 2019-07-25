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
ms.openlocfilehash: abfe1489cb7e0d06b03c308e0704ce6f69ee55da
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433803"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="16f49-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16f49-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="16f49-103">Gibt an, dass ein Argument als [Wert](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)übermittelt wird, sodass die aufgerufene Prozedur oder Eigenschaft den Wert einer Variablen, die dem Argument im aufrufenden Code zugrunde liegt, nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="16f49-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="16f49-104">Wenn kein Modifizierer angegeben wird, ist ByVal der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="16f49-104">If no modifier is specified, ByVal is the default.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="16f49-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16f49-105">Remarks</span></span>  
 <span data-ttu-id="16f49-106">Der `ByVal`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="16f49-106">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="16f49-107">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16f49-107">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="16f49-108">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16f49-108">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="16f49-109">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16f49-109">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="16f49-110">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16f49-110">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="16f49-111">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16f49-111">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="16f49-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16f49-112">Example</span></span>  
 <span data-ttu-id="16f49-113">Im folgenden Beispiel wird die Verwendung des `ByVal` Parameters Übergabe Mechanismus mit einem Verweistyp Argument veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="16f49-113">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="16f49-114">Im Beispiel ist `c1`das-Argument, eine Instanz der-Klasse `Class1`.</span><span class="sxs-lookup"><span data-stu-id="16f49-114">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="16f49-115">`ByVal`verhindert, dass der Code in den Prozeduren den zugrunde liegenden Wert des Verweis `c1`Arguments () ändert, nicht jedoch die zugänglichen Felder und `c1`Eigenschaften von.</span><span class="sxs-lookup"><span data-stu-id="16f49-115">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="16f49-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16f49-116">See also</span></span>

- [<span data-ttu-id="16f49-117">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="16f49-117">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="16f49-118">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="16f49-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
