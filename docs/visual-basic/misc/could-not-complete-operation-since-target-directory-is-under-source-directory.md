---
title: Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 253e7ff1d457827a2e1cb9f64eae4bfa971a3798
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645872"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="2ed59-102">Der Vorgang konnte nicht abgeschlossen werden, da sich das Zielverzeichnis unterhalb des Quellverzeichnisses befindet.</span><span class="sxs-lookup"><span data-stu-id="2ed59-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="2ed59-103">Ein zyklischer Vorgang ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="2ed59-103">A cyclic operation has failed.</span></span> <span data-ttu-id="2ed59-104">Ein zyklischer Vorgang wird zyklisch ausgeführt und kann daher nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2ed59-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="2ed59-105">Beispielsweise könnte Objekt A versuchen, von Objekt B zu erben, das wiederum versucht, von Objekt A zu erben.</span><span class="sxs-lookup"><span data-stu-id="2ed59-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ed59-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2ed59-106">To correct this error</span></span>  
  
-   <span data-ttu-id="2ed59-107">Wenn geerbt wird, müssen Sie sicherstellen, dass keine zyklischen Verweise vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2ed59-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed59-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ed59-108">See also</span></span>
- [<span data-ttu-id="2ed59-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="2ed59-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="2ed59-110">Debuggrundlagen: Haltepunkte</span><span class="sxs-lookup"><span data-stu-id="2ed59-110">Debugging Basics: Breakpoints</span></span>](https://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
