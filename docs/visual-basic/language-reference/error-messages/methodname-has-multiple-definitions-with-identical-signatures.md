---
title: <methodname> hat mehrere Definitionen mit identischen Signaturen.
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 3b397711cc2fb1fd0c1dfd76899b162ab5fc1542
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397232"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="82a67-102">\<methodname> hat mehrere Definitionen mit identischen Signaturen.</span><span class="sxs-lookup"><span data-stu-id="82a67-102">'\<methodname>' has multiple definitions with identical signatures</span></span>
<span data-ttu-id="82a67-103">Eine- `Function` oder- `Sub` Prozedur Deklaration verwendet den identischen Prozedur Namen und die gleiche Argumentliste als vorherige Deklaration.</span><span class="sxs-lookup"><span data-stu-id="82a67-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="82a67-104">Eine mögliche Ursache ist ein Versuch, die ursprüngliche Prozedur zu überladen.</span><span class="sxs-lookup"><span data-stu-id="82a67-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="82a67-105">Überladene Prozeduren müssen verschiedene Argumentlisten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="82a67-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="82a67-106">**Fehler-ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="82a67-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="82a67-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="82a67-107">To correct this error</span></span>  
  
- <span data-ttu-id="82a67-108">Ändern Sie den Namen der Prozedur oder die Argumentliste, oder entfernen Sie die doppelte Deklaration.</span><span class="sxs-lookup"><span data-stu-id="82a67-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a67-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82a67-109">See also</span></span>

- [<span data-ttu-id="82a67-110">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="82a67-110">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="82a67-111">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="82a67-111">Considerations in Overloading Procedures</span></span>](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
