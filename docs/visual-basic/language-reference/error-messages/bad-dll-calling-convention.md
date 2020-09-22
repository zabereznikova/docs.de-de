---
title: Fehlerhafte DLL-Aufrufkonvention
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: 0481bd5e4dfe7a24dff454d0754b519509fa967f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875733"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="c6643-102">Fehlerhafte DLL-Aufrufkonvention</span><span class="sxs-lookup"><span data-stu-id="c6643-102">Bad DLL calling convention</span></span>

<span data-ttu-id="c6643-103">Argumente, die an eine Dynamic Link Library (dll) übergeben werden, müssen exakt mit den von der Routine erwarteten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c6643-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="c6643-104">Aufruf Konventionen behandeln die Anzahl, den Typ und die Reihenfolge der Argumente.</span><span class="sxs-lookup"><span data-stu-id="c6643-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="c6643-105">Das Programm ruft möglicherweise eine Routine in einer DLL auf, der der falsche Typ oder die falsche Anzahl von Argumenten übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c6643-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6643-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c6643-106">To correct this error</span></span>  
  
1. <span data-ttu-id="c6643-107">Stellen Sie sicher, dass alle Argument Typen mit denen übereinstimmen, die in der Deklaration der Routine, die Sie aufrufen, angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c6643-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2. <span data-ttu-id="c6643-108">Stellen Sie sicher, dass Sie die gleiche Anzahl von Argumenten übergeben, die in der Deklaration der Routine angegeben sind, die Sie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c6643-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3. <span data-ttu-id="c6643-109">Wenn die DLL-Routine Argumente als Wert erwartet, stellen Sie sicher, `ByVal` dass für diese Argumente in der Deklaration der Routine angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c6643-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6643-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6643-110">See also</span></span>

- [<span data-ttu-id="c6643-111">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="c6643-111">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="c6643-112">Call-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c6643-112">Call Statement</span></span>](../statements/call-statement.md)
- [<span data-ttu-id="c6643-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="c6643-113">Declare Statement</span></span>](../statements/declare-statement.md)
