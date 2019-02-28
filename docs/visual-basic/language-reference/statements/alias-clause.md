---
title: Alias-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 3b1a66ecfd3c023a12ac62191ca3671a195b45a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978227"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="81de1-102">Alias-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81de1-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="81de1-103">Gibt an, dass eine externe Prozedur einen anderen Namen in der entsprechenden DLL aufweist.</span><span class="sxs-lookup"><span data-stu-id="81de1-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81de1-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81de1-104">Remarks</span></span>  
 <span data-ttu-id="81de1-105">Die `Alias` -Schlüsselwort kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="81de1-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="81de1-106">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="81de1-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="81de1-107">Im folgenden Beispiel die `Alias` Schlüsselwort wird verwendet, um den Namen der Funktion in advapi32.dll, `GetUserNameA`, `getUserName` wird anstelle des in diesem Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="81de1-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="81de1-108">Funktion `getUserName` unter Sub "lautet" `getUser`, wird angezeigt, die den Namen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="81de1-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="81de1-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81de1-109">See also</span></span>
- [<span data-ttu-id="81de1-110">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="81de1-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
