---
title: Verwaltete Klassen, die von einer COM-Klasse abgeleitet werden, können nicht als spät gebunden aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: c18f2b6e1751d39ceb81c190f70ee161ca716bc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054183"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a><span data-ttu-id="f3315-102">Verwaltete Klassen, die von einer COM-Klasse abgeleitet werden, können nicht als spät gebunden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f3315-102">Managed classes derived from a COM class cannot be called late-bound.</span></span>

<span data-ttu-id="f3315-103">Sie haben versucht, eine verwaltete Klasse, die von einer COM-Klasse abgeleitet wird, als spät gebunden aufzurufen; solche Aufrufe werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f3315-103">You attempted to make a late-bound call to a managed class derived from a COM Class; such calls are not supported.</span></span>

## <a name="to-correct-the-problem"></a><span data-ttu-id="f3315-104">So beheben Sie das Problem</span><span class="sxs-lookup"><span data-stu-id="f3315-104">To correct the problem</span></span>

<span data-ttu-id="f3315-105">Ändern Sie den Aufruf in früh gebunden.</span><span class="sxs-lookup"><span data-stu-id="f3315-105">Make the call early bound.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3315-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3315-106">See also</span></span>

- [<span data-ttu-id="f3315-107">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="f3315-107">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
