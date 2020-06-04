---
title: Verwaltete Klassen, die von einer COM-Klasse abgeleitet werden, können nicht als spät gebunden aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: 401cb5d7194cbef616c87d59e5b1ed7f923fe6f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402121"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a><span data-ttu-id="ce9ad-102">Verwaltete Klassen, die von einer COM-Klasse abgeleitet werden, können nicht als spät gebunden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ce9ad-102">Managed classes derived from a COM class cannot be called late-bound.</span></span>

<span data-ttu-id="ce9ad-103">Sie haben versucht, eine verwaltete Klasse, die von einer COM-Klasse abgeleitet wird, als spät gebunden aufzurufen; solche Aufrufe werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ce9ad-103">You attempted to make a late-bound call to a managed class derived from a COM Class; such calls are not supported.</span></span>

## <a name="to-correct-the-problem"></a><span data-ttu-id="ce9ad-104">So beheben Sie das Problem</span><span class="sxs-lookup"><span data-stu-id="ce9ad-104">To correct the problem</span></span>

<span data-ttu-id="ce9ad-105">Ändern Sie den Aufruf in früh gebunden.</span><span class="sxs-lookup"><span data-stu-id="ce9ad-105">Make the call early bound.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce9ad-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce9ad-106">See also</span></span>

- [<span data-ttu-id="ce9ad-107">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="ce9ad-107">Error Types</span></span>](../programming-guide/language-features/error-types.md)
