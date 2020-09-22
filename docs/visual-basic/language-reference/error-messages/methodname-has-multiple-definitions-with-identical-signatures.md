---
title: <methodname> hat mehrere Definitionen mit identischen Signaturen.
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 2934a5666c55e1ca57b91ab86585261e6d71a2d3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873732"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="6e287-102">\<methodname> hat mehrere Definitionen mit identischen Signaturen.</span><span class="sxs-lookup"><span data-stu-id="6e287-102">'\<methodname>' has multiple definitions with identical signatures</span></span>

<span data-ttu-id="6e287-103">Eine- `Function` oder- `Sub` Prozedur Deklaration verwendet den identischen Prozedur Namen und die gleiche Argumentliste als vorherige Deklaration.</span><span class="sxs-lookup"><span data-stu-id="6e287-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="6e287-104">Eine mögliche Ursache ist ein Versuch, die ursprüngliche Prozedur zu überladen.</span><span class="sxs-lookup"><span data-stu-id="6e287-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="6e287-105">Überladene Prozeduren müssen verschiedene Argumentlisten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6e287-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="6e287-106">**Fehler-ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="6e287-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6e287-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6e287-107">To correct this error</span></span>  
  
- <span data-ttu-id="6e287-108">Ändern Sie den Namen der Prozedur oder die Argumentliste, oder entfernen Sie die doppelte Deklaration.</span><span class="sxs-lookup"><span data-stu-id="6e287-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e287-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e287-109">See also</span></span>

- [<span data-ttu-id="6e287-110">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="6e287-110">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="6e287-111">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="6e287-111">Considerations in Overloading Procedures</span></span>](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
