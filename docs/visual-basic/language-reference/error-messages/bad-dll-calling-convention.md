---
title: Fehlerhafte DLL-Aufrufkonvention
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: f7b0c3a6edbe0b950195306fa66287ff9b209bfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935277"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="d74ad-102">Fehlerhafte DLL-Aufrufkonvention</span><span class="sxs-lookup"><span data-stu-id="d74ad-102">Bad DLL calling convention</span></span>
<span data-ttu-id="d74ad-103">Argumente, die an eine Dynamic Link Library (DLL) müssen genau mit den erwarteten, von der Routine übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d74ad-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="d74ad-104">Aufrufkonventionen befassen sich mit Anzahl, Typ und Reihenfolge der Argumente.</span><span class="sxs-lookup"><span data-stu-id="d74ad-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="d74ad-105">Das Programm kann eine Routine in einer DLL aufrufen, der den falschen Typ oder die Anzahl von Argumenten übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d74ad-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d74ad-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d74ad-106">To correct this error</span></span>  
  
1. <span data-ttu-id="d74ad-107">Stellen Sie sicher, dass alle Argumenttypen akzeptieren, mit denen angegeben wird, in der Deklaration der Routine, die Sie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d74ad-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2. <span data-ttu-id="d74ad-108">Stellen Sie sicher, dass Sie die gleiche Anzahl von Argumenten angegeben werden, in der Deklaration der Routine, die Sie aufrufen übergeben.</span><span class="sxs-lookup"><span data-stu-id="d74ad-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3. <span data-ttu-id="d74ad-109">Wenn die DLL-Routine Argumente als Wert erwartet, stellen Sie sicher, dass `ByVal` für diese Argumente in der Deklaration für die Routine angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d74ad-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74ad-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d74ad-110">See also</span></span>

- [<span data-ttu-id="d74ad-111">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="d74ad-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="d74ad-112">Call-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d74ad-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)
- [<span data-ttu-id="d74ad-113">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d74ad-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
