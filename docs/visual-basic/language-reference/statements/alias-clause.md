---
title: Alias-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 84c8f39e632eebbe5382492669820910b38bc360
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053352"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="fec09-102">Alias-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fec09-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="fec09-103">Gibt an, dass eine externe Prozedur einen anderen Namen in der entsprechenden DLL aufweist.</span><span class="sxs-lookup"><span data-stu-id="fec09-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fec09-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fec09-104">Remarks</span></span>  
 <span data-ttu-id="fec09-105">Die `Alias` -Schlüsselwort kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="fec09-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="fec09-106">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fec09-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="fec09-107">Im folgenden Beispiel die `Alias` Schlüsselwort wird verwendet, um den Namen der Funktion in advapi32.dll, `GetUserNameA`, `getUserName` wird anstelle des in diesem Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="fec09-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="fec09-108">Funktion `getUserName` unter Sub "lautet" `getUser`, wird angezeigt, die den Namen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="fec09-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="fec09-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fec09-109">See also</span></span>

- [<span data-ttu-id="fec09-110">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fec09-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
