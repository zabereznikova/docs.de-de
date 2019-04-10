---
title: Ungültige Musterzeichenfolge
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 7390b9b32eea248969813b52f8d9799798718de0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298681"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="0eeaf-102">Ungültige Musterzeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0eeaf-102">Invalid pattern string</span></span>
<span data-ttu-id="0eeaf-103">Die angegebene Musterzeichenfolge in der `Like` -Operation einer Suche ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="0eeaf-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0eeaf-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0eeaf-104">To correct this error</span></span>  
  
1. <span data-ttu-id="0eeaf-105">Überprüfen Sie die zulässigen Zeichen für Listenausdrücke.</span><span class="sxs-lookup"><span data-stu-id="0eeaf-105">Review the valid characters for list expressions.</span></span>  
  
2. <span data-ttu-id="0eeaf-106">Stellen Sie im Musterbereich sicher, dass das Zeichen für den Startbereich kleiner als das Zeichen für den Endbereich ist, wie in `[a-z]`.</span><span class="sxs-lookup"><span data-stu-id="0eeaf-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3. <span data-ttu-id="0eeaf-107">Stellen Sie im Musterbereich sicher, dass nicht mehrere Bindestriche nebeneinander verwendet werden, wie in `[a--z]`.</span><span class="sxs-lookup"><span data-stu-id="0eeaf-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4. <span data-ttu-id="0eeaf-108">Beenden Sie die Musterbereiche mit einer schließenden eckigen Klammer.</span><span class="sxs-lookup"><span data-stu-id="0eeaf-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eeaf-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0eeaf-109">See also</span></span>

- [<span data-ttu-id="0eeaf-110">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="0eeaf-110">Like Operator</span></span>](../../visual-basic/language-reference/operators/like-operator.md)
