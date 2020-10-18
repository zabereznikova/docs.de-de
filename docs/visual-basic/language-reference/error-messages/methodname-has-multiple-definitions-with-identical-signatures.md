---
title: <methodname> hat mehrere Definitionen mit identischen Signaturen.
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 663b22421d1a0e401cfb3c135c99bd097163a78b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160365"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="6b2d3-102">BC30269: " \<methodname> " hat mehrere Definitionen mit identischen Signaturen.</span><span class="sxs-lookup"><span data-stu-id="6b2d3-102">BC30269: '\<methodname>' has multiple definitions with identical signatures</span></span>

<span data-ttu-id="6b2d3-103">Eine- `Function` oder- `Sub` Prozedur Deklaration verwendet den identischen Prozedur Namen und die gleiche Argumentliste als vorherige Deklaration.</span><span class="sxs-lookup"><span data-stu-id="6b2d3-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="6b2d3-104">Eine mögliche Ursache ist ein Versuch, die ursprüngliche Prozedur zu überladen.</span><span class="sxs-lookup"><span data-stu-id="6b2d3-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="6b2d3-105">Überladene Prozeduren müssen verschiedene Argumentlisten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6b2d3-105">Overloaded procedures must have different argument lists.</span></span>

 <span data-ttu-id="6b2d3-106">**Fehler-ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="6b2d3-106">**Error ID:** BC30269</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6b2d3-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6b2d3-107">To correct this error</span></span>

- <span data-ttu-id="6b2d3-108">Ändern Sie den Namen der Prozedur oder die Argumentliste, oder entfernen Sie die doppelte Deklaration.</span><span class="sxs-lookup"><span data-stu-id="6b2d3-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b2d3-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b2d3-109">See also</span></span>

- [<span data-ttu-id="6b2d3-110">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="6b2d3-110">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="6b2d3-111">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="6b2d3-111">Considerations in Overloading Procedures</span></span>](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
