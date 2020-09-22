---
title: Alias-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 77d4685f242864842e5a84b3a3de3ba1793e9aa4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866686"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="ab82a-102">Alias-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab82a-102">Alias Clause (Visual Basic)</span></span>

<span data-ttu-id="ab82a-103">Gibt an, dass eine externe Prozedur in der dll einen anderen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="ab82a-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab82a-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ab82a-104">Remarks</span></span>  

 <span data-ttu-id="ab82a-105">Das `Alias` Schlüsselwort kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ab82a-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="ab82a-106">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="ab82a-106">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="ab82a-107">Im folgenden Beispiel wird das- `Alias` Schlüsselwort verwendet, um den Namen der Funktion in advapi32.dll anzugeben, der `GetUserNameA` `getUserName` anstelle von in diesem Beispiel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab82a-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="ab82a-108">Die Funktion `getUserName` wird in Sub aufgerufen `getUser` , das den Namen des aktuellen Benutzers anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ab82a-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="ab82a-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab82a-109">See also</span></span>

- [<span data-ttu-id="ab82a-110">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ab82a-110">Keywords</span></span>](../keywords/index.md)
