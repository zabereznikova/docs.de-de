---
title: Alias-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: c28e931a376b20b2058a7187551405cd9523d4fe
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408470"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="cb5da-102">Alias-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb5da-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="cb5da-103">Gibt an, dass eine externe Prozedur in der dll einen anderen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="cb5da-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb5da-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cb5da-104">Remarks</span></span>  
 <span data-ttu-id="cb5da-105">Das `Alias` Schlüsselwort kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="cb5da-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="cb5da-106">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="cb5da-106">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="cb5da-107">Im folgenden Beispiel wird das- `Alias` Schlüsselwort verwendet, um den Namen der Funktion in advapi32. dll,, anzugeben, der `GetUserNameA` `getUserName` anstelle von in diesem Beispiel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cb5da-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="cb5da-108">Die Funktion `getUserName` wird in Sub aufgerufen `getUser` , das den Namen des aktuellen Benutzers anzeigt.</span><span class="sxs-lookup"><span data-stu-id="cb5da-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="cb5da-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb5da-109">See also</span></span>

- [<span data-ttu-id="cb5da-110">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="cb5da-110">Keywords</span></span>](../keywords/index.md)
