---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c192cdb4ac43ad614fbfb663079c03ddc6c358c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="byval-visual-basic"></a><span data-ttu-id="997c0-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="997c0-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="997c0-103">Gibt an, dass ein Argument so übergeben wird, dass die aufgerufene Prozedur oder Eigenschaft den Wert einer Variablen, die das Argument im aufrufenden Code zugrunde liegt, ändern kann.</span><span class="sxs-lookup"><span data-stu-id="997c0-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="997c0-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="997c0-104">Remarks</span></span>  
 <span data-ttu-id="997c0-105">Der `ByVal`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="997c0-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="997c0-106">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="997c0-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="997c0-107">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="997c0-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="997c0-108">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="997c0-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="997c0-109">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="997c0-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="997c0-110">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="997c0-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="997c0-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="997c0-111">Example</span></span>  
 <span data-ttu-id="997c0-112">Das folgende Beispiel veranschaulicht die Verwendung von der `ByVal` Parameterübergabe Mechanismus, mit einem Verweisargument-Typ.</span><span class="sxs-lookup"><span data-stu-id="997c0-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="997c0-113">Im Beispiel wird das Argument `c1`, eine Instanz der Klasse `Class1`.</span><span class="sxs-lookup"><span data-stu-id="997c0-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="997c0-114">`ByVal`verhindert, dass den Code in den Verfahren ändern den zugrunde liegenden Wert des Arguments Verweis `c1`, aber nicht die verfügbare Felder und Eigenschaften der schützt `c1`.</span><span class="sxs-lookup"><span data-stu-id="997c0-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="997c0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="997c0-115">See Also</span></span>  
 [<span data-ttu-id="997c0-116">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="997c0-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="997c0-117">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="997c0-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
